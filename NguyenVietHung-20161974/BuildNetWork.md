# Build Your first network

## 1. Cài đặt môi trường
- Phần mềm cURL
  - sudo apt-get install curl
- Cài đặt Docker và Docker Compose
  - Để kiểm tra đã cài đặt thành công hay chưa:
    - docker --version
    - docker-compose --version
- Cài đặt ngôn ngữ lập trình Go
  - Kiểm tra: go version
  - Cài đặt biến môi trường GOPATH để chỉ đến Go workspace:
    - export GOPATH=$HOME/go
    - export PATH=$PATH:$GOPATH/bin
- Cài đặt Node.js và npm
- Tải về Fabric Samples: 
  - curl -sSL http://bit.ly/2ysbOFE | bash -s 1.2.1 1.2.1 0.4.10

## Build Network
- Mở thư mục first-network đã tải về:
	- cd fabric-samples/first-network
- Trong thư mục này có một file script byfn.sh dùng images Docker để tạo nhanh mạng lưới Hyperledger Fabric gồm 4 peer đại diện cho hai tổ chức khác nhau và một order node.
- Nó cũng chạy một container để thực thi một script để join các peer vào channel, deploy và khởi động chaincode, điều kiển thực hiện các giao dịch.
### 1. Tạo ra các thành phần mạng (Generate Network Artifacts)
./byfn.sh generate

- Nó sẽ tạo ra tất cả các chứng chỉ và keys cho các thực thể trong mạng, tạo ra genesis block ,...
### 2. Triển khai mạng (Bring up the Network)
./byfn.sh up

=> complie GO chaincode images và spin up các container tương ứng.

### 3. Bring down the Network
Kill các container, xóa bỏ các crypto material và 4 thành phần, xóa chaincode images ở Docker Registry:
./byfn.sh down

## 2. Tìm hiểu thêm một số công cụ cơ bản

**Xây dựng mạng Hyperledger đầy đủ chức năng (fully-functional)**

Cài đặt trong file docker-compose-cli.yaml trong thư mục first-network, đặt giá trị:	CORE_LOGGING_LEVEL=DEBUG

### 1. Crypto Generator
Sử dụng **cryptogen tool** để tạo ra x509 keys cho các thực thể trong mạng, các chứng chỉ này đại diện cho các thực thể, cho phép họ có thể ký, xác minh giao dịch để giao tiếp và giao dịch.
#### Nó hoạt động như thế nào?
- Cryptogen nằm ở trong file crypto-config.yaml, nó chứa cấu hình mạng và cho phép tạo ra tập các chứng chỉ và keys cho cả tổ chức và các thành phần của tổ chức.
- Mỗi tổ chức được cung cấp một root certificate duy nhất liên kết các thành phần cụ thể trong mạng (peer và orderer) với tổ chức đó.
- Các giao dịch và giao tiếp được ký bởi private key của thực thể và xác minh bằng public key.
- Biến *count* để chỉ ra số peer trong một tổ chức (2).
- Sau khi chạy *cryptogen tool* các chứng chỉ được sinh ra và keys được lưu vào một thư mục *crypto-config*

### 2. Cấu hình Transaction Generator
- *configtxgen tool* sử dụng để tạo ra 4 cấu hính sau:
  - orderer genesis block
  - channel configuration transaction
  - 2 anchor peer transaction cho 2 peer Org.
- orderer block là Gensis Block cho việc order, file giao dịch cấu hình kênh được quảng bá cho order tại thời điểm kênh được tạo ra.

#### Nó hoạt động như thế nào?

- *configtxgen* ở file *configtx.yaml* nó chứa các định nghĩa cho mạng.
- Có 3 thành viên: một Orderer Org và hai Peer Org mỗi cái quản lý và duy trì hai peer nodes
- File *SampleConsortium* chỉ định một tập đoàn, bao gồm 2 peer Orgs. Phần Profile đầu tiên dành cho orderer genesis block và phần Profile thứ hai dành cho 2 channel.

### 3. Run the tools

#### Tạo thủ công các thành phần của mạng

- Chạy *cryptogen tool*, cung cấp đường dẫn đến tool:

  - ../bin/cryptogen generate --config=./crypto-config.yaml
  - Ta sẽ thu được kết quả:
    org1.example.com
    org2.example.com
  - Chứng chỉ và keys sẽ được dưa ra file *crypto-config* trong folder fisrt-network.
- Thêm đường dẫn cho file *configtxgen* đến file *configtx.yaml*:

  - export FABRIC_CFG_PATH=$PWD
- Triển khai *configgen tool* để tạo orderer genesis block:
  - ../bin/configtxgen -profile TwoOrgsOrdererGenesis -outputBlock ./channel-artifacts/genesis.block
- Khối genesis block và các thành phần con được tạo và đưa vào file *channel-artifacts*
#### Tạo giao dịch cấu hình kênh

- Tạo channel: 
  - export CHANNEL_NAME=hungchannel  && ../bin/configtxgen -profile TwoOrgsChannel -outputCreateChannelTx ./channel-artifacts/channel.tx -channelID $CHANNEL_NAME
- Định nghĩa anchor peer cho Org1 trên channel đã tạo:
  - ../bin/configtxgen -profile TwoOrgsChannel -outputAnchorPeersUpdate ./channel-artifacts/Org1MSPanchors.tx -channelID $CHANNEL_NAME -asOrg Org1MSP
- Định nghĩa anchor peer cho Org2:
  - ../bin/configtxgen -profile TwoOrgsChannel -outputAnchorPeersUpdate ./channel-artifacts/Org2MSPanchors.tx -channelID $CHANNEL_NAME -asOrg Org2MSP
#### Start the network
- docker-compose -f docker-compose-cli.yaml up -d
#### Biến môi trường
- 4 biến môi truòng cho peero.org1.example.com:

CORE_PEER_MSPCONFIGPATH=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.example.com/users/Admin@org1.example.com/msp
CORE_PEER_ADDRESS=peer0.org1.example.com:7051
CORE_PEER_LOCALMSPID="Org1MSP"
CORE_PEER_TLS_ROOTCERT_FILE=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.example.com/peers/peer0.org1.example.com/tls/ca.crt

#### Tạo và tham gia vào channel
- Có thể tạo giao dịch cấu hình kênh thêm bằng cách lặp lại các bước ở trên
- Nhập vào CLI bằng cách sử dụng *docker exec* command:
  - docker exec -it cli bash
-  Nếu không muốn chạy CLI command trên kênh mặc định peer0.org1.example.com, thay giá trị của peer0 hoặc org1 ở 4 biến môi trường và chạy lệnh: 

export CORE_PEER_MSPCONFIGPATH=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.example.com/users/Admin@org1.example.com/msp
export CORE_PEER_ADDRESS=peer0.org1.example.com:7051
export CORE_PEER_LOCALMSPID="Org1MSP"
export CORE_PEER_TLS_ROOTCERT_FILE=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.example.com/peers/peer0.org1.example.com/tls/ca.crt

- Tạo các artifact giao dịch cấu hình kênh cho orderer
- Tên channel: -c
- Giao dịch cấu hình kênh: -f
- Tên kênh phải ít hơn 250 ký tự và phải phù hợp với regular expression [a-z][a-z0-9.-]*
- export CHANNEL_NAME=hungchannel 
- peer channel create -o orderer.example.com:7050 -c $CHANNEL_NAME -f ./channel-artifacts/channel.tx --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem
- Lệnh trên trả về một genesis block để join vào channel, nó gồm thông tin cấu hình trong file channel.tx
- Lệnh --cafile đường truyền vào là đường dẫn đến chứng chỉ root của orderer, cho phép bắt tay TLS
- Đưa peer *peer0.org1.example.com* vào kênh: 
  - peer channel join -b hungchannel.block
- Ta có thể đưa các peer khác tham gia vào kênh nếu cần thiết bằng cách thya đổi 4 biến môi trường ở trên.
- Thay vì join vào tất cả các peer, ta chỉ join vào *peer0.org2.example.com* và có thể update anchor peer của kênh:

CORE_PEER_MSPCONFIGPATH=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org2.example.com/users/Admin@org2.example.com/msp CORE_PEER_ADDRESS=peer0.org2.example.com:7051 CORE_PEER_LOCALMSPID="Org2MSP" CORE_PEER_TLS_ROOTCERT_FILE=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org2.example.com/peers/peer0.org2.example.com/tls/ca.crt peer channel join -b hungchannel.block

#### Update anchor peer

- Về bản chất là update thêm thông tin cấu hình lên trên của genesis block của kênh (việc này không phải sửa đổi khối genesis mà là thêm deltas vào chuỗi mà ta định nghĩa anchor peer).
- Update định nghĩa kênh để để định nghĩa anchor peer cho Org1 là *peer0.org1.example.com*: 
  - peer channel update -o orderer.example.com:7050 -c $CHANNEL_NAME -f ./channel-artifacts/Org1MSPanchors.tx --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem
- Update định nghĩa kênh để để định nghĩa anchor peer cho Org2 là *peer0.org2.example.com*:
  -  Ta phải đặt các biến môi trường trước đó:
  - CORE_PEER_MSPCONFIGPATH=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org2.example.com/users/Admin@org2.example.com/msp CORE_PEER_ADDRESS=peer0.org2.example.com:7051 CORE_PEER_LOCALMSPID="Org2MSP" CORE_PEER_TLS_ROOTCERT_FILE=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org2.example.com/peers/peer0.org2.example.com/tls/ca.crt peer channel update -o orderer.example.com:7050 -c $CHANNEL_NAME -f ./channel-artifacts/Org2MSPanchors.tx --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem

#### Cài đặt và khởi tạo chaincode

- Chỉ có thể cài đặt một version của source code trên một tên chaincode và version.
- Sử dụng Golang:

  - peer chaincode install -n mycc -v 1.0 -p github.com/chaincode/chaincode_example02/go/
- Câu lệnh dưới : -P "AND ('Org1MSP.peer','Org2MSP.peer')" => Cần 2 xác thực từ peer thuộc về Org1 **và** Org2, **OR** => chỉ cần một xác thực.
- peer chaincode instantiate -o orderer.example.com:7050 --tls --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n mycc -v 1.0 -c '{"Args":["init","a", "100", "b","200"]}' -P "AND ('Org1MSP.peer','Org2MSP.peer')"

- Nếu muốn thên peers tương tác với ledger, cần join chúng vào channel, cài đặt cùng tên, version và ngôn ngữ của chaincode trên filesystem của peer.

#### Query

Query giá trị **a**:

- peer chaincode query -C $CHANNEL_NAME -n mycc -c '{"Args":["query","a"]}'

#### Invoke

- Move 10 from a to b:

  - peer chaincode invoke -o orderer.example.com:7050 --tls true --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem -C $CHANNEL_NAME -n mycc --peerAddresses peer0.org1.example.com:7051 --tlsRootCertFiles /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.example.com/peers/peer0.org1.example.com/tls/ca.crt --peerAddresses peer0.org2.example.com:7051 --tlsRootCertFiles /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org2.example.com/peers/peer0.org2.example.com/tls/ca.crt -c '{"Args":["invoke","a","b","10"]}'

  - **NOTE:** Nếu lỗi Error: could not assemble transaction: ProposalResponsePayloads do not match - proposal response

    -> Thử thay đổi biến môi trường của Org2: 

    CORE_PEER_MSPCONFIGPATH=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org2.example.com/users/Admin@org2.example.com/msp CORE_PEER_ADDRESS=peer0.org2.example.com:7051 CORE_PEER_LOCALMSPID="Org2MSP" CORE_PEER_TLS_ROOTCERT_FILE=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org2.example.com/peers/peer0.org2.example.com/tls/ca.crt peer chaincode install -n mycc -v 1.0 -p github.com/chaincode/chaincode_example02/go/

    - query kiểm tra lại a: 
      - peer chaincode query -C $CHANNEL_NAME -n mycc -c '{"Args":["query","a"]}'

### 4.  Sử dụng couchDB
- State database có thể chuyển từ mặc định (GolevelDB) sang CouchDB, để sử dụng CouchDB:
  - docker-compose -f docker-compose-cli.yaml -f docker-compose-couch.yaml up -d

## 3. Viết chaincode (sử dụng ngôn ngữ Go)
### Lưu trữ thông tin người dùng:
- ID
- Họ tên
- Ngày sinh
- Giới tính
- Email
### Các chức năng
- Xem, thêm, xóa thông tin người dùng
- Sửa thông tin người dùng: đang tìm hiểu












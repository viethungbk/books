# 1. Key Concepts

## 	1. Giới thiệu

## 	2. Chức năng của Hyperledger Fabric

Hyperledger Fabric là sự triển khai công nghệ sổ cái phân tán (DLT - Distributed ledger technology)  cung cấp cho doanh nghiệp mạng an toàn, có khả năng mở rộng, và hiệu suất dựa trên kiến trúc blockchain.

### 		1. Quản lý danh tính

+ Để có thể truy cập mạng, HF  cung cấp một dịch vụ nhận dạng thành viên, nó quản lý ID người dùng và xác thực tất cả các người tham gia trên mạng.

+ Dang sách điều khiển truy cập có thể sử dụng để cung cấp các lớp quyền bổ sung qua ủy quyền các hoạt động mạng cụ thể. Ví dụ, với một ID người dùng cụ thể có thể đươc phép gọi một chaincode (smart contract), nhưng không được phép triển khai chaincode mới.

###			2. Quyền riêng tư và bảo mật

+ HF có thể cạnh tranh lợi nhuận kinh doanh, và những nhóm yêu cầu riêng tư, bảo mật giao dịch để cùng tồn tại trên một mạng. 

+ Channels (Các kênh) riêng tư là các đường dẫn nhắn tin có thể sử dụng để cung cấp quyền riêng tư và bảo mật giao dịch cho các tập con của mạng tham gia. Tất cả dữ liệu bao gồm cả thông tin về giao dịch, kênh và các thành viên đều được ẩn đi và không thể truy cập nếu thành viên trong mạng không có quyền truy cập.

### 3. Hiệu quả xử lý

- HF gán vai trò mạng theo loại nút. 
- Để cung cấp song song đồng thời cho mạng, việc thực thi giao dịch được tách biệt với thứ tự giao dịch và cam kết. Thực hiện các giao dịch trước khi sắp xếp cho phép mỗi node ngang hàng xử lý đồng thời nhiều giao dịch.

### 4. Chức năng  Chaincode

+ Chaincode được gọi bởi các transaction riêng biệt trên channel.
+ Chaincode xác định thông số cho quyền sở hữu, đảm bảo tất cả các giao dịch chuyển quyền sở hữu đều tuân theo các quy tắc và yêu cầu.

+ System chaincode xác định chaincode cho toàn bộ kênh.
+ Vòng đời và cấu hình chaincode xác định quy tắc cho kênh, 

### 5. Thiết kết mô-đun 

+ HF thực hiện kiến trúc mô-đun để cung cấp  chức năng lựa chọn  cho việc thiết kế mạng.

## 3. Mô hình Hyperledger Fabric

### 1. Assets (Tài sản)

+ Định nghĩa tài sản cho phép trao đổi gần như tất cả những gì có giá trị trên mạng.

+ Tài sản có thể là hữu hình (bất động sản, phần cứng) hay vô hình (hợp đồng, sở hữu trí tuệ). HF có thể sửa đổi các tài sản bằng cách sử dụng giao dịch chaincode.

+ Tài sản được biểu diễn trong HF dưới dạng cặp Key-Value, với sự thay đổi được lưu bởi kênh sổ cái (Channel Ledger).
### 2. Chaincode

+ Chaincode là phần mềm xác định tài sản và các hướng dẫn giao dịch để thay đổi tài sản.
+ Chaincode thực thi các luật để đọc hoặc thay thế các cặp Key - Value hoặc trạng thái dữ liệu.
+ Chaincode thực thi dựa trên dữ liệu ở trạng thái sổ cái hiện tại và bắt đầu thông qua một đề xuất giao dịch. Kết quả thực thi chaincode code ở trong cặp Key-Value có thể được submit lên mạng và ghi vào sổ cái.
+ 

### 3.  Tính năng của Ledger (sổ cái)

+ Ledger là một chuỗi trình tự, chống giả mạo ghi lại tất cả các trạng thái giao dịch (là kết quả của việc thực hiện chaincode của các bên tham gia).
+ Ledger bao gồm một Blockchain để lưu trữ bản ghi bất biến, được sắp xếp theo khối, cũng như cơ sở dữ liệu dể duy trì trạng thái hiện tại.
+ Có một Ledger trong một Channel, mỗi Peer (điểm) duy trì một bản sao của Ledger của Channel của nó.

### 4. Bảo mật thông qua kênh (Channels)

+ HF sử dụng một sổ cái bất biến trên mỗi kênh, chaincode có thế thao tác và sửa đổi với trạng thái hiện tại của tài sản.

+ Ledger tốn tại trong phạm vi của một kênh, nó có thể được chia sẻ ra toàn bô mạng hoặc để riêng tư cho một số thành viên nhất định.

+ Người tham gia có thể tạo ra một kênh riêng, cô lập giao dịch của họ và sổ cái.

+ Để cân bằng giữa tính minh bạch và tính riêng tư, chaincode chỉ có thể được cài đặt ở peer mà cần truy cập đến trạng thấi của asset để đọc và ghi (Nếu chaincode không được cài đặt trên peer, nó không thể trao đổi  dữ liệu với Ledger).

+ Khi một tập hợp con của tổ chức trên channel cần bảo bật giao dịch của họ, tập hợp các dữ liệu giao dịch được lưu trữ tách biệt trên ledger của kênh, chỉ có thể được truy cập bởi các tập con của tổ chức được ủy quyền.

+ Các giá trị trong chaincode có thể được mã hóa một phần hoặc toàn bộ (sử dụng thuật toán mã hóa như là AES) trước khi giao dịch được gửi đến order mà thêm khối vào block trong ledger, nó chỉ có thể giải mã bởi người có khóa tương ứng.

+ Ledger tồn tại trong phạm vi một channel, nó có thể được chia sẻ trên toàn bộ mạng hoặc có thể cá nhân hóa cho một vài người riêng biệt.


### 5.  Dịch vụ bảo mật và tư cách thành viên

- Public key được sử dụng để tạo ra chứng chỉ mã hóa gắn với các tổ chức, các thành viên trong mạng, người dùng cuối hoặc ứng dụng khách.
- Việc kiểm soát truy cập có thể điều khiển và điều chỉnh trên mạng rộng hơn và trên các cấp channels.

### 6. Cơ chế đồng thuận (consensus)

- Sự đồng thuận là sự xác minh vòng tròn về tính chính xác của tập các giao dịch bao gồm trong một khối.
- Sự đồng thuận đạt được khi thứ tự và kết quả của các giao dịch của block đáp ứng được các kiểm tra chính sách minh bạch.

## 4. Mạng Hyperledger Fabric
###  Các thành phần của mạng
- Ledgers (một Channel cần một kênh, bao gồm blockchain và trạng thái dữ liệu)
- Smartcontract (chaincode)
- Peer nodes
- Ordering services
- Channels
- Fabric Certificate Authorities (CA)

#### Network Policies và danh tính
- CA cung cấp chứng chỉ cho tổ chức để xác thực với mạng, có thể có một hoặc nhiều CA trên mạng và các tổ chức có thể lựa chọn CA của họ.
- Các ứng dụng của khách hàng được tổ chức trong một công ty sử dụng chứng chỉ để xác thực đề xuất giao dịch, các peers dù chúng để xác nhận đề xuất và đưa giao dịch và ledger nếu nó hợp lệ.

### 1. Tạo mạng
- Mạng được tạo ra từ định nghĩa công ty bao gồm clients, peers, channels và ordering services.
- Ordering services là điểm quản lý mạng vì nó chứa cấu hình của các channels trong mạng.
- Cấu hình của kênh bao gồm chính sách cho channel và thông tin thành viên cho mỗi thành viên của chanel.
### 2. Định nghĩa consortium
- Một consotium bao gồm hai hay nhiều tổ chức trên mạng, các tổ chức này cần cần có nhu cầu giao dịch và phải đồng ý chính sách quản lý trên mạng.
### 3. Tạo channel
- Channel là phương tiện kết nối giữa các thành phần trong mạng và các thành viên ứng dụng.
- Channels được tạo ra bằng cách tạo khối cấu hình trên ordering services, đánh giá cấu hình hợp lệ của channel.
- Channels cho phép dữ liệu độc lập và bảo mật.
- Các tổ chức giao dịch phải được xác thực qua một kênh để tương tác với kênh đó và các kênh đươc điều chỉnh bởi chính sách mà chúng được cấu hình.
### 4. Peers và channels
- Peers tham gia vào channels bởi tổ chức sở hữu chúng, có thể có nhiều peers trên channels trong mạng.
- Peer có nhiều tác dụng:
	- Peer kiểm chứng: xác nhận bởi chính sách như các nodes cụ thể được thực thi bởi giao dịch smart contract và trả về một phản hồi kiểm chứng cho ứng dụng khách.
	- Peer commit: xác thực blocks của giao dịch order và commit các khối vào bản sao của ledger mà nó đang giữ.
### 5. Ứng dụng và Smart Contracts
- Smart contract chaincode phải được cài đặt và khời tạo trên peer để khách hàng có thể gọi.
- Ứng dụng được đặt ngoài mạng, nơi mà các giao dịch được tạo ra.
- Smart contract được gọi trên peer chứng thực, nó thực thi hợp đồng dựa trên bản copy ledger và gửi phản hồi proposal trở lại ứng dụng client, sau đó ứng dụng client lắp ráp những phản hồi này vào giao dịch và quảng bá nó đến ordering service
### 6. Phát triển mạng lưới


## 5. Danh tính
### 1.  Giới thiệu
- Danh tính để xác định quyền chính xác đối với tài nguyên và truy cập thông tin trong mạng blockchain.
- Principal gần giống như userIDs hay groupIDs, là các thuộc tính quyết định đến quyền.
- Với một danh tính để được xác minh, nó phải đến từ một cơ quan đáng tin cậy (Nhà cung cấp dịch vụ thành viên - MSP).
- MSN là một thành phần xác định quy tắc quản lý xác thực danh tính cho tổ chức.
- Việc triển khai MSP sử dụng chứng chỉ X.509, áp dụng mô hình phân cấp hạ tầng Public key truyền thống (PKI)

### 2. PKIs
- Cơ sở hạ tầng Public key (PKI - Public Key Infrastructure) là tập hợp các công nghệ Internet cung cấp để đảm bảo giao tiếp an toàn trên mạng.
- Một PKI gồm các tổ chức phát hành chứng chỉ kỹ thuật số cho các bên (CA).
- Dang sách chứng chỉ thu hồi của CA (Certificate Revocation List - CRL) tham chiếu đến các chứng chỉ không còn giá trị.
- Mạng blockchain dựa vào tiêu chuẩn để đảm bảo an toàn giao tiếp giữa những người tham gia mạng với nhau và đảm bảo cho các thông tin trên mạng này được xác thực chính xác.

*Có 4 ý chính cần nắm được ở PKI:*
#### 1. Digital Certificates : Chứng chỉ số
- Chứng chỉ số là tài liệu chứa tập các thuộc tính của người sở hữu chứng chỉ.
- Loại chứng chỉ phổ biến nhất là chứng chỉ theo tiêu chuẩn X.509, nó cho phép mã hóa các chi tiết danh tính của các bên tham gia trong cấu trúc của nó.
#### 2. Public key và private key
- Xác thực yêu cầu các bên trao đổi thông điệp phải đảm bảo danh tính.
- Một thông điệp phải đảm bảo tính toàn vẹn có nghĩa là không thể sửa đổi được trong quá trình truyền nó đi.
- Cơ chế xác thực truyền thống dựa vào chữ ký số, cho phép các bên ký điện tử vào thông điệp của họ, chữ ký số cũng đươc đảm bảo về tính toàn vẹn của thông điệp đã ký.
- Chữ ký số yêu cầu các bên phải giữ được hai khóa mã hóa: 
	- Public key hoạt động công khai và để xác thực.
	- Private key dùng để tạo chữ ký số lên trên thông điệp
- Người nhận có thể xác minh nguồn gốc và tính toàn vẹn của thông điệp nhận được bằng cách kiểm tra chữ ký đính kèm qua public key.
- Private key có thể tạo chữ ký trên thông điệp mà chỉ có public key tương ứng mới khớp và chỉ trên cùng một thông diệp.
#### 4. Certificate Authorities: tổ chứng phát hành chứng chỉ
- Một node có thể tham gia vào mạng blockchain qua một chứng chỉ số được cấp bởi một cơ quan đang tin cậy của hệ thống.
- Danh tính số được mã hóa theo tiêu chuẩn X.509 và phát hành bởi tổ chức CA.
- Chứng chỉ có thể được sử dụng rộng rãi vì nó không bao gồm pivate key.
- CA cung cấp chứng chỉ cho các bên khác nhau và kên kết với chúng qua Public key.
- Các CA cũng có chứng chỉ, giúp chùng có khả năng mở rộng. Điều này cho phép danh tính của người dùng được nhận dạng bằng cách kiểm tra chứng chỉ chỉ có thể tạo bởi chủ sở hữu của Private Key.
- CA chia thành hai loại: Root CAs và CAs trung gian:
- Do Root CAS phải cung cấp an toàn cho hàng trăm triệu người dùng nên nó phải chia sẻ cho CAs trung gian.
- Các CAs trung gian phải có chứng chỉ do root CAs cung cấp hoặc được CAs trung gian khác cung cấp, tạo thành một "chain of trust" cho các chứng chỉ.
- Chức năng này cho phép CAs mở rộng mà vẫn đảm bảo an toàn.
- Fabric CA là một root CA riêng tư có khả năng quản lý danh tính của những người tham gia.
#### 5. Certificate Revocation Lists - Các danh sách chứng chỉ thu hồi
- Khi một bên muốn kiểm tra danh tính của bên khác,  trước tiên nó phải kiển tra CRL của CA để đảm bảo rằng chứng chỉ bên đó chưa bị thu hồi.
- Chứng chỉ bị thu hồi khác với chứng chỉ hết hạn


## 6. Tư cách thành viên (Membership)

### 1.  Mapping MSPs to Organizations
- Một tổ chức được chia thành nhiều đơn vị tổ chức (OUs) có một nhiệm vụ riêng

### 2. Local và Channel MSPs
- MSPs xuất hiện trên 2 vị trí trong blockchain: 
	- Cấu hình kênh (channel MSPs)
	- Local MSP
- Local MSPs được xác định cho người dùng và các node, xác định quyền cho các node.
- Mọi node và người dùng phải có một local MSP xác định cho biết ai có quyền quản trị và có sự tham gia ở cập độ đó (quản trị peer không nhất thiết phải quản trị channel và ngược lại).
- Channel MSPs xác định quyền quản trị và tham gia ở mức độ kênh, Mọi tổ chức trong kênh phải có một MSP xác định.
- Sự khác nhau của channel và local MSP không phải ở chức năng mà ở  phạm vi của chúng:
	- Local MSPs chỉ xác định trên hệ thống tệp của node hoặc người dùng mà chúng áp dụng, do đó, có một local MSPs trên mỗi node hoặc user.
	- Channel MSPs có sẵn cho cả node và channel, chúng xác định trên cấu hình kênh. Một channel cũng được tạo trên hệ thông tệp của mọi nút trong kênh và đồng bộ hóa qua sự đồng thuận. Channerl MSP được lưu trên hệ thống tệp và được duy trì bơ một kênh hoặc mạng
### 3. Các mức MSP
- MSPs ở mức khác nhau có nhiệm vụ khác nhau: 
	- MSPs ở mức cao hơn để quản trị mạng
	- MSPs ở mức thấp hơn xử lý tài nguyên cá nhân
- Network MSP: cấu hính của mạng xác định ai là thành viên trong mạng bằng cách xác định MSP của các tổ chức tham gia, các thành viên nào được quản lý các tác vụ.
- Channel MSP: 
	- Cần duy trì riêng các MSPs của các thành viên
	- Kênh cho phép giao tiếp giữa các thành viên trong tổ chức có quyền điều khiển với nó. 
- Peer MSP: 
	- MSP local này được định nghĩa trên hệ thống tệp của mỗi peer và mỗi một MSP dành cho một peer.
- Orderer MSP như một peer MSP, orderer local MSP cũng được định nghĩa trên hệ thống file của node và chỉ áp dụng cho node đó. Orderer thuộc sở hữu của một tổ chức để liệt kê các bên mà nó tin tưởng.
### 4. Cấu trúc MSP
MSP được lưu trữ  trên hệ thống file với 9 thành phần: 
- Root CAs:  
  - Phải có ít nhất một Root CA X.509 trong thư mục này
  - Đây là thư mục quan trọng nhất vì nó chưa CA bắt nguồn cho cho các chứng chỉ khác.
- CA trung gian: 
  - Một CA trung gian đại diện cho khu vực tổ chức, 
  - Thư mục này định nghĩa các CA mà từ đó các chứng chỉ được cấp để được xét là thành viên của tổ chức.
- Đơn vị tổ chức (OUs)
- Adminitrastors
- Revoked Certificates: chứa chứng chỉ bị thu hồi
- Node identity
- KeyStore cho Private Key
- TLS Root CA
## 7.  Peers
- Mạng blockchain là tập hợp các peer node
- Peer là thành phần cơ bản của mạng vì chúng lưu trữ sổ cái và smart contracts.
- Peer có thể được tạo ra, bắt đầu, kết thúc, cấu hình lại hoặc xóa đi, chúng hiển thị tập hợp các API cho phép người quản trị và ứng dụng có thể tương tác với các dịch vụ nó cung cấp.

### 1. Sổ cái và chaincode
- Peer lưu trữ các thành phần của sổ cái và chaincode, admin và ứng dụng muốn sử dụng tài nguyên phải tương tác với peer. Do đó, peer được coi như là thành phần chính của mạng Hyperledger Fabric.
- Khi một peer được tạo ra, nó chưa có cả sổ cái và chaincode.
- Một peer có thể lưu trữ nhiều sổ cái, làm cho thiết kế hệ thống linh hoạt hơn,
- Một peer thường có ít nhất một chaincode để truy vấn và cập nhật sổ cái.
### 2. Ứng dụng và peer
- Ứng dụng tương tác với peer để truy cập sổ cái qua cuộc hội thoại ba bước giữa ứng dụng và peer.

- Tương tác cập nhật sổ cái cần thêm hai bước nữa.

- Ứng dụng luôn kết nối đến peer khi chúng cần truy cập sổ cái.

- Hyperledger Fabric SDK cung cấp các API cho phép ứng dụng có thể kết nối đến peer, thực hiện chaincode tạo ra giao dịch, đưa giao dịch lên mạng để order và commit lên sổ cái, nhận thông báo khi chúng được thực hiện xong.

- Peer kết nối đến các orderer, đảm bảo rằng sổ cái được cập nhật trên mọi peer.

- Các bước:
  - 1: Ứng dụng kết nối đến Peer 

  - 2: Thực hiện chaincode: 

     - Peer thực hiện chaincode để truy vấn hoặc cập nhật sổ cái
     - Chaincode được thực hiện tạo ra proposal trong đó có để nghị là truy vấn hoặc update sổ cái.

  - 3: Trả proposal về cho ứng dụng.

    Nếu chỉ truy vấn sổ cái, quá trình đến đây là hoàn thành, để update cần thêm những bước sau: 

  - 4: Ứng dụng tạo một giao dịch từ tất cả các phản hồi rồi gửi đến orderer

     - Orderer gom nhưng giao dịch này vào các block rồi phân phối đến tất cả các peers.
     - Peer xác thực giao dịch trước khi thêm các block vào sổ cái
     - Sổ cái được update, tạo ra một event.

  - 5: Event được gửi cho ứng dụng và kết thúc quá trình update.
### 3. Peer và channel

- Các peer node, orderer node, và các ứng dụng cùng than gia vào một channel, cùng đông ý hợp tác chia sẻ và quản lý bản ssao của sổ cái trên kênh.
- Peer là nơi để kiểm soát, truy cập và quản lý kênh.

### 4. Peer và tổ chức

- Mạng blockchain được quản lý  bởi một tập các tổ chức

### 5. Peer và danh tính

- Peer có danh tính và tham gia vào mạng thông qua chứng chỉ số được cấp bởi người quản trị sở hữu tổ chức đó.

### 6. Peer và orderer


## 8. Private data
### 1. Private data collection
- Private data collection  cho phép tạo ra một tập con các tổ chức trên kênh có thể xác thực, commit, truy vấn private data mà không cần phải tạo kênh riêng.
- Tập private data gồm hai thành phần:
	 1. Dữ liệu riêng thực tế: gửi peer-to-peer qua giao thức gossip (tin đồn) để chỉ tổ chức có quyền mới xem được dữ liệu. Dữ liệu được lưu trong cơ sở dữ liệu riêng tư trên peer (SideDB).
	 2. Mã hash của dữ liệu đó: được xác nhận, order, viết lên sổ cái trên mỗi peer của channel, là bằng chứng của giao dịch và được sử dụng để xác thực state và có thể dùng để kiểm toán.
#### Sử dụng collection trong channel và separate channel
- Dùng channel khi toàn bộ giao dịch và sổ cái phải giữ bí mật trong tổ chức
- Dùng collection khi chỉ tập cong của tổ chức được truy cập vào một vài hoặc tất cả dữ liệu trong giao dịch. Vì dữ liệu được phổ biến peer to peer mà không phải qua các khối, sử dụng collection khi dữ liệu giao dịch phải được giữ bí mật từ các node order

## 9. Ledger

### 1. A blockchain Ledger
- World state là cơ sở dữ liệu lưu giá trị hiên tại của tập các sổ cái hiện tại.

- Blockchain như là nhật ký giao dịch ghi lại tất cả các thay đổi, nó xác định world state.

- Giao dịch được thêm vào blockchain và ta có thể biết được lịch sử thay đổi của kết quả trong world state hiện tại.

### 2. World state
- World state rất hữu ích vì chương trình thường xuyên sử dụng trạng thái giá trị hiện tại và nó luôn có sẵn mà không cần duyệt qua toàn bộ blockchain và lấy ra giá trị hiện tại.ư
- Ledger state dùng để ghi lại thông tin ứng ụng  và chia sẻ qua blockchain, nó có một cặp giá trị là key và value, ứng dụng thực hiện chaincode và dễ dàng truy cập trạng thái qua các API, có thể lấy, đặt, xóa các giá trị bằng cách sử dụng state key.
- World state được triển khai như môt cơ sở dữ liệu, nó được cung cấp rất nhiều các toán tử để lưu trữ và truy cập state.
- Nếu giao dịch không được ký bởi đủ người xác nhận, kết quả sẽ không được update vào world state.
- State có các phiên bản, nó tăng lên mỗi lần state thay đổi, nó cũng được kiểm tra mỗi khi state update để đảm bảo rằng nó khớp với version khi giao dịch được tạo ra.
- Khi sổ cái mới được tạo, world state trống rỗng

### 3. Blockchain
- Blockchain được triển khai dưới dạng file
### 4. Blocks
Một block gồm: 
- Block Header: có 3 trường được tạo ra khi một block được tạo:
	- Chỉ sổ của block: là một sốn guyên bắt đầu từ 0 (là chỉ số của block khởi nguồn) và tăng một đơn vị mỗi khi có một block mới được thêm vào blockchain.
	- Mã hash của block hiện tại.
	- Mã hash của block trước: là môt bản sao của mã hash block trước
- Block data: chứa một danh sách cac giao dịch, nó được viết vào khi block được tạo ra
- Block metadata: chứa thời gian mà block được thêm vào, chứng chỉ, public key và chữ kí của người thêm block
### 5. Transaction
Transaction chứa các trường sau:
- Header: ghi lại những metadata quan trọng cho giao dịch: teen chaincode, phiên bản của nó...
- Signature: chứa chữ ký mã hóa, tạo ra bởi ứng dụng khách hàng. Dùng để kiểm tra giao dịch có bị giả mạo hay không, nó yêu cầu private key của ứng dụng sinh ra nó.
- Proposal: mã hóa đầu vào được cung cấp bởi ứng dụng vào chaincode, tạo ra đề xuất update sổ cái.
- Response: ghi lại giá trị trước và sau của world state, là Read Write set
- Endorsements (sự xác nhận)













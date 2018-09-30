# Chương 1: Giới thiệu

## 1. Bitcoin là gì ?

- Bitcoin là một tập hợp các khái niệm và công nghệ hình thành lên hệ sinh thái tiền kỹ thuật số.
- Bitcoin là một đơn vị tiền tệ được dùng để lưu trữ và truyền giá trị giữa những người tham gia mạng Bitcoin. Người sử dụng Bitcoin giao dịch với nhau bằng cách sử dụng giao thức chủ yếu của Bitcoin qua Internet mặc dù các truyền tải mạng khác có thể sử dụng.
- Giao thức Bitcoin là open source có thể chạy trên nhiều thiết bị, làm cho công nghệ này dễ dàng sử dụng. Người dùng có thể chuyển Bitcoin qua mang và sử dụng như đồng tiền thông thường.
- Công nghệ Bitcoin dựa trên mã hóa và chữ ký số để đảm bảo an toàn cho mạng lưới Bitoin. Bitcoin có thể được mua bán, trao đổi với các loại tiền tệ khác.
- Bitcoin như là một loại tiền hoàn hảo cho Internet vì nó nhanh, an toàn và không giới hạn.
- Người dùng bitcoin sở hữu key của mình để xác thực giao dịch của mình trên mạng blockchain. Những key này thường lưu trữ trên ví số của người dùng. Dùng key để mở khóa giao dịch là điều kiện tiên quyết để tiêu bitcoin.
- Bitcoin là một hệ thống hoàn toàn phân tán, hệ thống P2P.
- Bitcoin được tạo ra qua quá trình "mining" - đào - đòi hỏi phải giải quyết một bài toán khó. Người tham gia mạng lưới bitcoin  có thể trở thành miner, xử lý bài toán đó. Trung bình 10 phút là có người đào được và được nhân bitcoin mới.
- Giao thức bitcoin gồm các thuật toán gắn liền để điều chỉnh hàm mining qua mạng.
- Bitcoin giảm một nửa số bitcoin được tạo ra 4 năm một lần và giới hạn tổng số  bitcoin được tạo ra là 21 triệu coins (có thể đạt đến trước năm 2140). Vì việc giảm tạo ra bitcoin mới nên lạm phát được giảm.
- Bitcoin cũng là tên của một giao thức, một loại mạng, và một sự đổi mới tính toán phân tán.
- Bitcoin là kết quả nghiên cứu tiêu biểu trong lĩnh vực mã hóa và hệ thống phân tán gồm 4 cải tiến quan trọng. Bitcoin bao gồm: 
  - Một mạng không tập trung P2P (giao thức bitcoin).

  - Một sổ cái giao dịch công khai (blockchain).

  - Tính toán và phát hành tiền tệ (coins) không tập trung (khai thác phân tán).

  - Một hệ thống xác minh giao dịch phân tán (transaction script).

    ## 2. Lịch sử Bitcoin
- Bitcoin được Satoshi Nakamoto tạo ra năm 2008.
- Shatoshi Nakamoto kết hợp vài sáng chế như b-money và HashCash để tạo ra hệ thống tiền điện tử hoàn toàn phi tập trung mà không phụ thuộc vào trung tâm phát hành tiền tệ và xác thực giao dịch.
- Đổi mới quan trọng là nó sử dụng hệ thống tính toán phân tán (thuật toán Proof of Work - PoW) để tiến hành "bầu cử"  (election) toàn mạng mỗi 10 phút, cho phép mạng phân tán có thể cùng đồng thuận về trạng thái của giao dịch -> Nó giải quyết được vấn đề chi tiêu kép (trước đây, vấn đề chi tiêu kép là điểm yếu của tiền điện tử, nó được giải quyết bằng cách xóa bỏ giao dịch bằng trung tâm clearinghouse).
- Mạng Bitcoin bắt đầu vào năm 2009.
- Tổng giá trị Bitcoin trên thị trường ước tính 5 đến 10 tỷ đô la Mỹ, phụ thuộc vào tỷ giá hối đoái đô la - bitcoin.
- Giao dịch lớn nhất được xử lý bởi mạng là 150 triệu đô la Mỹ, được chuyển ngay lập tức và xử lý không cần bất kỳ khoản phí nào.
- Không ai kiểm soát hệ thống bitcoin, nó hoạt dộng dựa trên các nguyên tắc toán học hoàn toàn minh bạch.
-> Phát minh này là một bước đột phá và sinh ra ngành khoa học mới trong lĩnh vực tính toán phân tán, kinh tế học và kinh tế lượng.


# Chương 2: Bitcoin hoạt động như thế nào ?

## 1. Transactions, Blocks, Mining và Blockchain
### 	1. Giao dịch

- Hệ thống bitcoin không giống như ngân hàng truyền thống, nó dựa trên sự tin tưởng phân tán. Thay vì trung tâm ủy quyền, sự tin tưởng được tạo ra từ tương tác của những người tham gia.

- Có thể hiểu đơn giản, một giao dịch sẽ nói cho mạng biết rằng người này cho phép chuyển một số bitcoin của họ cho người khác, người đó có thể dùng số coin đó bằng cách tạo ra một giao dịch khác và chuyển cho người khác.

- Giao dịch giống như hai cột trong sổ cái:
  - Một cột chứa một hoặc nhiều "inputs" ghi nợ vào tài khoản bitcoin.
  - Một cột khác chứa một hoặc nhiều "outputs" cho nợ bitcoin
  - Tổng inputs và outputs không nhất thiết phải bằng nhau. Outputs sẽ nhỏ hơn inputs do phí giao dịch trả cho các thợ đào.

- Các loại giao dịch thông thường: 
  - Loại giao dịch đơn giản nhất là giao dịch đơn giản từ một địa chỉ đến một địa chỉ khác, nó thay đổi số bitcoin của chủ sở hữu ban đầu. Nó gồm 1 input và 2 outputs.
  - Loại giao dịch phổ biến khác là sự hợp nhất của một vài inputs thành một output.
  - Một loại giao dịch khác là phân phối từ một input tới nhiều outputs (nhiều người nhận). Loại giao dịch này thường được sử dụng bới doanh nghiệp để phân phối quỹ như trả lương cho nhiều nhân viên.

### 	2. Tạo một giao dịch

Ứng dụng ví chứa tất cả các inputs outputs để tạo một giao dịch. Ví có thể tạo một giao dịch mặc dù nó đang offline, nó chỉ phải gửi lên mạng cuối cùng để nó được thực thi.

#### Nhận đầu vào phù hợp (Getting right inputs)

- Như ta đã biết, một giao dịch sẽ nhận đầu vào từ đầu ra của giao dịch ngay trước đó, để có thể tạo một giao dịch mới, ví phải chứa đủ bitcoin từ một output unspent hoặc nó phải quét rồi tính tổng các unspent outputs nhỏ hơn để có được unspent output đủ cho giao dịch.

#### Tạo đầu ra (Creating the outputs)

- Khi giao dịch được tạo, chỉ người có chữ ký của khóa tương ứng với địa chỉ đích thì mới được nhận coin và ví sẽ bị tính thêm một ít tiền phí giao dịch.

#### Thêm giao dịch vào sổ cái (Ledger)

- Khi giao dịch gồm đủ tất cả những thông tin cần thiết, nó sẽ được đưa lên mạng. Mạng bitcoin là kết nối điểm điểm, mỗi bitcoin client tham gia bằng cách kết nối với các bitcoin client khác.
- Ứng dụng ví sẽ gửi giao dịch mới đến một vài node mà nó kết nối đến qua Internet (không cần kết nối trực tiếp đến ví bitcoin của người nhận), các node đó lại ngay lập tức gửi tiếp đến các node khác mà nó kết nối đến -> do đó giao dịch nhanh chóng được truyền khắp mạng. 
- Một quan niệm sai lầm về giao dịch bitcoin là họ phải đợi xác nhận 10 phút cho một block mới hoặc 60 phút cho 6 yêu cầu xác nhận. Khi các yêu cầu xác nhận này đã được gửi đi toàn bộ mạng thì sự delay này là không cần thiết với mặt hàng có giá trị thấp như một tách cafe. Người bán hàng có thể chấp nhận một giao dịch nhỏ không cần qua xác nhận.
###		3. Đào bitcoin (Bitcoin mining)
- Khi giao dịch đã được truyền trên toàn mạng, nó chưa nằm trong blockchain cho đến khi nó được xác nhận và thêm vào một block bằng cách "mining" - đào.
- Các giao dịch được đóng gói vào các khối, cần tính toán rất khó để giải quyết bài toán chứng minh nhưng rất dễ dàng để thấy được kết quả tính toán đó đúng.
- Quá trình đào có hai tác dụng: 
	- Tạo ra bitcoin mới ở mỗi block, cũng như việc ngân hàng in tiền mới. Tổng số bitcoin tạo ra ở mỗi block không đổi và giảm dần theo thời gian.
	- Việc đào tạo tin tưởng bằng cách đảm bảo rằng giao dịch chỉ được xác nhận nếu đủ năng lực tính toán dành cho khối chứa chúng. Càng nhiều khối thì càng tin cậy hơn.
###		4. Mining transactions in blocks
- Thợ đào thêm những giao dịch chưa được xác xinh vào một chỗ gọi là "pool" tạm thời. Khi thợ đào thêm block mới, họ thêm các giao dịch đó vào block mới và cố gắng giải bài toán PoW
- Khi giao dịch được thêm vào block, giao dịch có phí cao nhất sẽ được ưu tiên và có một số tiêu chí khác. Mỗi thợ đào sẽ bắt đầu đào block mới ngay khi họ nhận được block trước đó từ mạng. Họ ngay lập tức tạo ra một block mới, thêm vào đó các giao dịch và mã hash của giao dịch trước, sau đó tính toán PoW cho block mới.
- Mỗi thợ đào sẽ thêm vào block của họ một giao dịch đặc biệt là địa chỉ bitcoin của họ. Nếu họ giải được bài toán PoW, họ sẽ thêm được block vào blockchain là nhận được một phần thưởng là bitcoin vào địa chỉ bitcoin của họ.
- Các block được nối tiếp nhau trong blockchain. Một block đứng trước một block khác được gọi là một "xác nhận" cho giao dịch đó. Theo quy ước, một block có hơn 6 khối được coi là không thể thay đổi vì nó đòi hỏi sự tính toán khổng lồ để vô hiệu hóa và tính lại 6 khối trước đó.
### 	5. Spending the transaction
- Khi một giao dịch được thêm vào blockchain, nó có thể thấy được bởi tất cả các apps bitcoin.
- Tất cả khách hàng bitcoin có thể theo dõi nguốn coin từ thời điểm nó được tạo ra, từng giao dịch một, cho đến thời điểm hiên tại.
# Chương 3: The Bitcoin Client
## 1. Bitcoin core
- Bitcoin core giữ một bản sao đầy đủ của blockchain , với các giao dịch từ khi bitcoin vận hành (2009). 
## 2. Sử dụng JSON-RPC API của Bitcoin Core bằng command line
## 3. Alternative clients, libraries and toolkits

# Chương 4: Keys, Addresses, Wallets
## 	1. Giới thiệu
- Việc sở hữu bitcoin được hình thành qua khoá số, địa chỉ bitcoin và chữ ký số. 
- Các khóa sô không được lưu trữ thực sự trong mạng mà nó được tạo ra và lưu trữ bởi người dùng cuối trong một file hoặc một cơ sở dữ liệu đơn giản gọi là ví.
- Khóa ở ví của người dùng hoàn toàn độc lập với giao thức bitcoin và có thể được sinh ra và quản lý bởii phần mềm ví của người dùng mà không tham chiếu đến blockchain hay truy cập mạng.
- Keys có tác dụng: tin tưởng phi tập trung, điều khiển và kiểm soát quyền sở hữu và mô hình bảo mật mã hóa.
- Mỗi giao dịch cần phải có chữ ký hợp lệ để được thêm vào blockchain, nó có thể  sinh ra với khóa hợp lệ. Dó đó bất kỳ ai có có bản sao của khóa đó đều có quyền kiểm soát tài khoản bitcoin đó.
- Keys bao gồm: 
  - Public key (giống như số tài khoản ngân hàng)
  - Private key (giống như mã PIN hay chữ ký ở tấm séc)
- Người dùng hiếm khi nhìn thấy keys vì nó được lưu và quản lí trong phần mềm ví.
- Trong phần thanh toán của người dùng bitcoin, public key của người nhận được biễu diễn bằng chữ ký số, gọi là địa chỉ bitcoin (giống như tiên của người nhận trên tấm séc). Trong hầu hết các trường hợp, bitcoin address được tạo ra và tương ứng với public key.
### 	1. Mã hóa public key và tiền mã hóa
- Bitcoin sử dụng phép nhân đường cong elip làm cơ sở cho mã hóa public key, do đó, nó không thể tính theo chiều ngược lại.
- Bitcoin sử dụng mã hóa khóa công khai để tạo cặp khóa kiểm soát quyền truy cập vào bitcoin. Cặp khóa bao gồm: 
	- Public key (duy nhất, tạo ra từ Public key) dùng để nhận bitcoin
	- Private key dùng để ký các  giao dịch để sử dụng tiền bitcoin.
- Private key có thể sử dụng để tạo chữ ký lên giao dịch, chữ ký này có thể dễ dàng xác thực bằng public key mà không cần tiết lộ khóa riêng.
-  Mỗi khi tiêu bitcoin, họ phải đưa ra public key và chữ ký (mỗi lần là khác nhau nhưng được tạo từ cùng một private key), qua đó, mọi người trên mạng botcoin có thể xác minh và chấp nhận giao dịch đó là hợp lệ.
-  Trong hầu hết các ví, private key và public key được lưu trữ như là một cặp cho thuận tiện, Tuy nhiên, public key có thể được tính toán từ private key, vì vậy, có thể chỉ lưu trữ private key là đủ
### 	2. Private keys and public keys
- Từ private key (k), sử dụng phép nhân đường cong elip - một hàm mã hóa một chiều để tạo ra một public key (K).

- Từ public key, ta sử dụng hàm băm mật mã một chiều để tạo ra địa chi bitcoin (A)
   *private key (k) -----eliptic curve multiplication---> public key (K) -------hashing funtion----> Bitcoin Address (A)*

### 	3. Private keys
- Private key là một số, thường được chọn ngẫu nhiên.
- Quyền sở hữu và kiểm soát private key là của người dùng root với tất cả các tiền liên quan đến địa chỉ bitcoin tương ứng.
- Private key dùng để tạo ra chữ ký được yêu cầu khi chi tiêu bitcoin bằng cách chứng minh quyền sở hữu số tiền trong giao dịch.
- Private key phải luôn được giữ kín vì nếu bên thứ 3 biết được, họ hoàn toàn có quyền kiểm soát tài khoản bitcoin đó.
- Private key phải được sao lưu và bảo vệ khỏi những mất mát vì nếu bị mất nó thì không thể khôi phục và số tiền được bảo vệ bởi nó cũng mất vĩnh viễn.
#### Tạo private key từ một số ngẫu nhiên
- Việc đầu tiên quan trọng nhất để tạo keys là tìm một nguồn entropy an toàn hoặc ngẫu nhiên.
- Về cơ bản việc tạo bitcoin key cũng giống việc chọn một số trong đoạn 1 đến (2^256) - 1, phương pháp chính xác để tạo ra số đó không quan trọng, miễn là nó không thể dự đoán và không lặp lại được.
- Phần mềm của bitcoin sử dụng trình tạo số ngẫu nhiên của hệ điều hành để tạo ra 256 bit entropy. Về phương diện lập trình, ta có thể chọn một chuối lớn lấy từ nguồn mã hóa an toàn rồi dùng thuật toán băm SHA-256 tính kết quá, nếu kết quả nhỏ hơn n - 1 thì ta có một private key hợp lệ, nếu không thì ta có thể dễ dàng thử lại với một chuỗi ngẫu nhiên khác.
###  	4. Public keys
- Public key được tính từ private key qua phép nhân đường cong elip, thông thể tính ngược lại được: 
  ​				**K = k * G**

  ​	Trong đó: 
  ​	- K: Public key
  ​	- k: private key
  ​	- G: điểm hằng số - Điểm phát (Generator point)
## 	2. Địa chỉ bitcoin
- Bitcoin address là một mỗi các số và chữ có thể chia sẻ cho bất cứ ai muốn gửi tiền cho bạn.
- Các bitcoin addresses được tạo ra từ Public key bao gồm các một chuỗi các số và chữ, bắt đầu bằng số "1".
- Địa chỉ bitcoin xuất hiện phổ biến trong các giao dịch với tư cách là người nhận tiền.
- Bitcoin cũng là một công cụ thanh toán linh hoạt do địa chỉ bitcoin  có thể đại diện cho một cá nhân hoặc "kịch bản thanh toán" - payment script
- Địa chỉ bitcoin được tạo ra từ Public key qua hàm mã hóa một chiều - hàm băm (hashing algorithm). Hàm này tạo ra "dấu vân tay" (fingerprint) hay còn gọi là mã hash của đầu vào có kích thước tùy ý.
- Các hàm băm mã hóa được sử dụng rộng rãi trong bitcoin: bitcoin addresses, script address, trong việc đào PoW.
- Thuât toán sử dụng để tạo bitcoin address là SHA và RIPEMD, đặc biệt là SHA256 và RIPEMD160.
***Bitcoin address không giống với public key, bitcoin address được lấy từ khóa công khai bằng cách sử dụng hàm một chiều ***
-  Bticoin address hầu như luôn được hiển thị cho người dùng ở dạng mã hóa Base58Check, nó dùng 58 ký tự và kiểm tra để giúp dễ đọc, tránh nhầm lẫn, tránh lỗi trong quá trình ghi và nhập địa chỉ.
- Base58Check được sử dụng nhiều trong bitcoin, khi cần người dùng đọc và ghi chính xác các số (ví dụ địa chỉ bitcoin, private key, encrypted key, script hash).

***Public key ----HASH160---> Public key hash  ----Base58Check Encode---> Bitcoin Address***

### Key Formats

## 3. Wallets (ví)
- Ví chứa private keys, thường được tổ chức dưới dạng tệp tin hoặc cấu trúc dữ liệu đơn giản.
- Một phương pháp khác để tạo private key là sử dụng hàm băm một chiều từ private key trước đó, nối chúng lại thành một chuỗi. Khi đó ta chỉ cần key đầu tiên (còn được gọi là seed hay master key) có thể tạo lại chuỗi đó.
- Ví chứa các keys, không chứa coins. Coin đươc lưu trữ trên blockchain dưới dạng các outputs của giao dịch. 

**Các loại ví**
### 	1. Ví không xác định (Non-Deterministic)
- Là loại ví được sưu tập từ các private keys được tạo ngẫu nhiên.
- Bitcoin core client ban đầu có thể sinh ngẫu nhiên ra nhiều private keys và có thế tạo ra tiếp nếu cần thieestm mỗi key chỉ dùng một lần. Loại ví này được gọi là "Just a Bunch Of Keys - JBOK", nó đang bị thay thế dần bởi loại ví xác định vì nó rất cồng kềnh để quản lý, sao lưu và import.
- Điểm yếu của các khóa ngẫu nhiên là nếu tạo ra nhiều khóa, ta cần phải sao lưu tất cả chúng, ví phải đc sao lưu thường xuyên hơn nếu không sẽ dễ bị mất. Điều này xung đột trực tiếp với nguyên tắc tránh sử dụng lại địa chỉ, bằng cách sử dụng từng địa chỉ bitcoin cho một giao dịch duy nhất.
- Các nhà phát triển Bitcoin core không khuyến khích dùng ví loại này.
### 	2. Ví xác định (Deterministic - Seeded Wallets)
- Là loại ví chứa các private keys được tạo từ một seed, qua việc sử dụng hàm băm một chiều. Seed là một số được tạo ngẫu nhiên và kết hợp với các dữ liệu khác, ví dụ như "chain code" để lấy private keys.
- Seed có thể dùng để khôi phục các keys, vì vậy chỉ cần một bản sao lưu duy nhất tại thời điểm tạo, seed cũng dùng để import export, cho phép di chuyển dễ dàng tất cả các keys giữa các ví khác nhau.
### Mnemonic Code Words
- Mnemonic codes là chuỗi các từ tiếng anh (12-24 từ) đại diện cho một số ngẫu nhiên sử dụng như seed cho ví xác định.
- Chuỗi các từ này có thể tạo lại seed và tạo lại tất cả các keys trong ví.
- Mnemonic codes được định nghĩa bởi Bitcoin Improvement Proposal 39 (BIP0039) qua các bước: 
	- Tạo một chuỗi entropy ngẫy nhiên 128-256 bits
	- Tạo checksum cho chuỗi đó bằng cách lấy một vài bits đầu tiên của mã hash SHA256 của nó.
	- Thêm checksum vào cuối chuỗi này.
	- Chia chuỗi thành các phần 11 bits, sử dụng chỉ số từ điển của 2048 từ được xác đinh trước.
	- Đưa ra 12-24 từ đại diện cho mnemonic codes
### Hierachical Deterministic Wallets (BIP0032/BIP0044)
- HD wallet là một dạng cải tiến của ví xác định, nó theo chuẩn bip0032
- Nó chưa các keys ở dạng cây. Parent key có thể lấy được một chuỗi các khóa con, mỗi khóa con lại lấy đươc một chuỗi con cháu và có chiều sâu vô hạn.
- HD wallet có 2 ưu điểm hơn so với ví không xác định: 
	- Cấu trúc cây có thể thực hiện chức năng mở rộng cho tổ chức, ví dụ:
		- Một nhánh thực hiện chức năng nhận các thanh toán đến, một nhánh nhận các thanh toán đi.
		- Sử dụng trong môi trường doanh nghiệp cho các phòng ban, công ty con, các chức năng cụ thể khác.
	- Tạo public keys mà không cần truy cập vào private key tương ứng.

**Root seed ---HMAC-SHA512----> 512 bits output
**left 256 bits ---> Master Private Key (m) ---> Master Public key (M)
**right 256 bits ---> Master Chain Code

## 4. Advanced Keys and Addresses
### 	1. Encrypted Private Keys (BIP38)
### 	2. Pay to script hash (P2SH) và Multi-Sig Addresses
### 	3. Vanity Addresses
### 	4. Paper Wallets

# Chương 5: Các giao dịch
## 1. Giới thiệu
Giao dịch là một cấu trúc dữ liệu mã hóa vieejcc truyền giá trị giữa những người tham gia mạng lưới bitcoin.
## 2. Vòng đời giao dịch
Giao dịch được tạo ra ---> Giao dịch được ký ---> Quảng bá lên mạng ---> Lan truyền giữa các node trên mạng ---> Xác mình và đào bởi một node và thêm vào block  ---> Ghi vào blockchain.
### 	1. Tạo giao dịch
- Giao dịch có thể được tạo online hoặc offline.
- Người tạo giao dịch có thể không phải là người ký  giao dịch (được ủy quyền).
- Sau khi được tạo, giao dịch được ký bởi (các) người sở hữu tiền.
### 	2. Quảng bá giao dịch lên mạng bitcoin
- Giao dịch bitcoin có thể truyền qua các mạng không an toàn như wifi, bluetooth, NFC mã vạch, chirp hoặc bằng cách sao chép rồi dán vào web form. Trong trường hợp đặc biệt, nó có thể truyền qua sóng radio, vệ tinh, sóng ngắn hoặc mã hóa dưới dạng biểu tượng cảm xúc và đăng trong các diễn đàn công khai hoặc gửi dưới dạng tin nhắn
### 	3. Lan truyền giao dịch trên mạng bitcoin
- Giao dich  bitcoin được phê chuẩn bởi các node: 
	- Nếu hợp lệ, node đó sẽ lan truyền đến các node khác mà nó kết nối đến với thông điệp thành công.
	- Nếu không hợp lệ, node đó sẽ từ chối và gửi thông báo từ chối cho người gửi.
- Một giao dịch mới được thêm vào bất kỳ một node nào sẽ được gửi cho 3-4 node liền kề, mỗi node liền kề lại gửi cho 3-4 node liền kề khác và cứ như vậy.
- Để chống lại spam và các cuộc tấn công, mỗi node sẽ độc lập xác thực mọi giao dịch trước khi truyền bá nó sang node khác. Một giao dịch không hợp lệ sẽ không đi qua được hơn một node.

## 3. Cấu trúc một giao dịch
Transaction là một cấu trúc dữ liệu mã hóa việc truyền giao dịch từ nguồn tiền (inputs) đến đích (outputs), nó có các trường: 
- Version: chỉ định quy tắc cho giao dịch này
- Input Counter: có bao nhiêu input
- Inputs: các inptuts
- Output Counter: có bao nhiêu output
- Outputs: các outputs
- Locktime: Nhãn thời gian hoặc số block, ghi lại thời gian sớm nhất mà giao dich được thên vào blockchain
## 4. Input và output của giao dịch
- UTXO được ghi lại trên blockchain và là đơn vị tiền tệ của toàn bộ mạng.
- Số dư bitcoin của người dùng không được lưu trữ mà nó được tính toán bởi ví của người dùng bằng cách quét toàn bộ các UTXO của người đó.
- 1 bitcoin = 10^8 satoshis
### 	1. Outputs
- Transaction outputs gồm 2 phần: 
	- Tổng lượng bitocoin tính bằng đơn vị satoshis
	- Một locking script, còn gọi là "encumbrance": chỉ ra điều kiện để tiêu output.

### 	2. Inputs
- Inputs là con trỏ trỏ đến UTXO. Chúng trỏ đến UTXO tham chiếu đến hash của giao dịch và chuỗi số, nơi ghi UTXO trên blockchain. Để tiêu UTXO cần có script mở khóa, thường là chữ ký chứng minh quyền sở hữu bitcoin.
- Khi người dùng thanh toán, ví của họ sẽ tạo một giao dịch bằng cách chọn những UTXO sẵn có.
- Cấu trúc input: 
	- Transaction hash: trỏ đến giao dịch chứa UTXO để chi tiêu
	- Output Index: chỉ số của UTXO  được tiêu
	- Unlocking-Script Size tính theo bytes
	- Unlocking-Script: Điều kiện của UTXO locking-script
	- Sequence Number
### 	3. Fees
- Hầu hết các giao dịch có phí, phí này để trả cho các thợ đào để đảm bảo an toàn cho mạng.
- Tác dụng của phí: 
	- Khuyến khích giao dịch được thêm vào block tiếp theo
	- Làm giảm các giao dịch spam hoặc làm dụng hệ thống
- Phí giao dịch được tính dựa trên kích thước của giao dịch tính bằng kbs, khống phải giá trị của giao dịch. 
- Các giao dịch có đủ phí sẽ được ưu tiên xử lý
### 	4. Thêm phí vào giao dịch
- Cấu trúc dữ liệu của các giao dịch không có trường cho phí mà số tiền dư ra từ output so với input sẽ được thu bởi các người đào.
	Fees = Sum(Inputs) - Sum(Outputs)
## 5. Transaction Chainning và Orphan transactions
- Các giao dịch tạo một chuỗi, một giao dịch chi tiêu output của giao dịch trước đó (gọi là parent) và tạo output cho chuỗi giao dịch (gọi là child).
- Đôi khi cả chuỗi giao dịch phụ thuộc vào nhau, cả giao dịch parent, child, grandchild được tạo cùng lúc thì yêu cầu giao dịch child phải được ký trước parent. Khi đó, child được đưa vào pool đợi parent đến và lan truyền trên mạng.
- Giao dịch trong pool mà không có giao dịch parent gọi là giao dịch mồ côi (Orphan transactions).
- Số giao dịch mồ côi trong pool được giới hạn để ngăn chặn tấn công từ chối dịch vụ ở các node bitcoin. Khi số giao dịch trong pool quá số lượng giới hạn, một vài giao dịch ngẫu nhiên sẽ bị loại bỏ.
## 6. Transaction script và Ngôn ngữ script
- Bitcoin client xác thực giao dịch bằng cách thực hiện script.
- Cả locking script và unlocking script đều chứa chữ ký.
### 	1. Cấu trúc script (Lock và Unlock)
Công cụ xác minh giao dịch của bitcoin dựa trên 2 loại script: 
- Locking script: 
	- Đặt ở output của giao dịch
	- Nó yêu cầu các điều kiện cần có khi chi tiêu ở lần sau
	- Còn được gọi là scriptPubKey vì nó chứa public key hoặc bitcoin address.
- Unlocking script: 
	- Giải quyết các điều kiện của locking script, cho phép chi tiêu output
	- Là một phần của giao dịch, chứa chữ ký số.
	- Còn được gọi là scriptSig vì nó thường chứa chữ ký số.
- Hoạt động: 
	- Unlocking script được thực thi, sử dụng stack
	- Nếu nó không có lỗi, stack chính được sao chép và locking script được thực thi. Nếu kết quả thực thi locking scriptvaf dữ liệu stack được copy từ unlocking script là true thì unlocking script được giải quyết thành công, được ủy quyển để chi tiêu.
	- Nếu kết quả khác true thì không được quyền chi tiêu UTXO
### 	2. Ngôn ngữ script
### 	3. Turing Incompleteness
### 	4. Stateless Verification

## 7. Giao dịch chuẩn









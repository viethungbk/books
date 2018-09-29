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

# Chương 5: Các giao dịch



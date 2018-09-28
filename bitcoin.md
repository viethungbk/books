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

Như ta đã biết, một giao dịch sẽ nhận đầu vào từ đầu ra của giao dịch ngay trước đó, để có thể tạo một giao dịch mới, ví phải chứa đủ bitcoin từ một output unspent hoặc nó phải quét rồi tính tổng các unspent outputs nhỏ hơn để có được unspent output đủ cho giao dịch.

#### Tạo đầu ra (Creating the outputs)

Khi giao dịch được tạo, chỉ người có chữ ký của khóa tương ứng với địa chỉ đích thì mới được nhận coin và ví sẽ bị tính thêm một ít tiền phí giao dịch.

#### Thêm giao dịch vỏa sổ cái (Ledger)




# Chương 3: The Bitcoin Client

# Chương 4: Keys, Addresses, Wallets

# Chương 5: Các giao dịch



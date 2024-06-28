Processes vs Thread:
- Process (tiến trình): hệ điều hành có thể chạy nhiều chương trình cùng lúc, như mở trình duyệt, nghe nhạc ... Mỗi chương trình được gọi là một tiến trình đang được thực hiện. 
	- Có bộ nhớ riêng được chỉ định bởi hệ điều hành, không chia sẻ với các tiến trình khác.
- Thread (luồng): là các tác vụ phụ trong tiến trình, có thể chạy đồng thời trong tiến trình. Mỗi tiến trình kích hoạt ít nhất 1 luồng khi khởi động, gọi là main thread. Sau đó dựa vào nhu cầu cùa ctrình, các luồng bổ sung có thể được yêu cầu/ kết thúc. 
	- Multithreading (đa luồng) là việc chạy nhiều luồng trong 1 tiến trình.
	- Các luồng chia sẻ cùng một bộ nhớ được hệ điều hành gán cho tiến trình mẹ của chúng, giúp 2 luồng nói chuyện với nhau dễ dàng hơn.
	- Luồng thường nhẹ hơn tiến trình, tốn ít tài nguyên và tạo nhanh hơn.

Green thread (fiber): là một loại mô phỏng làm cho các chương trình đa luồng hoạt động trong các môi trường không cung cấp khả năng đó. Được tạo và quản lý nhanh hơn vì nó bỏ qua hệ điều hành.

Concurrency vs Parallelism
- Concurrency (tính đồng thời): _nhận thức_ về việc có các tác vụ chạy cùng 1 lúc
- True parallelism (tính song song thật sự): các tác vụ thật sự chạy cùng 1 lúc. Parallelism là tập con của Concurrency


Preemptive multitasking (đa nhiệm ưu tiên): 
preemption là khả năng làm gián đoạn 1 tác vụ, chuyển sang một tác vụ khác và sau đó tiếp tục tác vụ đầu tiên.

Data race - Race condition:
- Race condition: 2 hoặc nhiều luồng thực hiện công việc theo thứ tự không thể đoán trước được, đáng lý phải thực hiện theo trình tự thích hợp. (non-deterministic)
	- Root cause: preemp multitask cung cấp cho OS toàn quyền kiểm soát quản lý luồng.
- Data race: trong khi writer thread sửa đổi bộ nhớ, reader thread có thể đang đọc bộ nhớ đó. Nếu writer chưa xong việc thì reader sẽ nhận được data corrupt. 
	- Root cause: non-atomic operations


Concurrency control:
- Synchronization (đồng bộ hóa): đảm bảo tài nguyên chỉ được sử dụng bởi 1 luồng tại 1 thời điểm
- Atomic operations: chuyển các non-atomic thành atomic nhờ lệnh cung cấp bởi OS
- Immutable data (dữ liệu bất biến): dữ liệu dùng chung được đánh dấu là bất biến, không thể thay đổi được nó.



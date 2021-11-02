# Luuw-doof
## Cau 1:

	Ta có thể mở rộng vấn đề, không chỉ là 11 mà có thể là 100, 1000, 10000. Từ đó ta phải có 1 cách giải tổng quát hơn. Hãy bắt đầu từ con số 11, ta có :
	
		11 : 2 = 5 (dư 1)
		5  : 2 = 2 (dư 1)
		2  : 2 = 1 (dư 1)
		1  : 2 = 0 (dư 1)

	Ta có 5 phép nhân tối thiểu.
## Câu 4:

	Ta biến đổi dạng toán 1 chút cho thuận tiện: từ (-1)^n . (x^2n) = (-x^2)^n.
	
## Câu 5:
	
	Lần đầu nhìn mình có ý định dùng hàm đệ quy, nhưng vì chỉ được viết thuật toán cơ bản nên ý tưởng bài này sẽ đơn giản thôi:
		
		for (int i=1; i<= n5; i++)
			{
				so_hang5 *= x5;
				kq5 = sqrt (so_hang5 + kq5);
			}
		
	Như vậy ta không cần viết đệ quy cũng có thể lồng căn vào căn.

## Câu 6:
	
	Lần đầu đọc đề mình hiểu đề là làm tròn tới chữ số thập phân thứ 6 sau dấu "phẩy", mà không dùng hàm của thư viện thì phải viết ra hàm. Mình làm khá kỳ công theo các bước sau: (có thể skip phần này)
	
		1. Viết hàm cộng các phân số mà vẫn giữ nguyên dạng phân số (từ tư duy tạo toán tử)
		2. Từ kết quả 1, viết hàm lấy tử chia mẫu (như 1 học sinh lớp 5) và xuất ra 6 chữ số sau dấu "phẫy" thì dừng
	
	Đây là code của bước 2:
	
		//Tim 6 chu so thap phan cua phan so
		#include <iostream>
		using namespace std;

		const int maxn = 100;
		void tp (int tu, int mau){
			int flag (0), i (0), aTP [6];
	
			while (i <=6){
		
				if (tu < mau)
					{
			
					if (flag == 0)
			
						flag = 1;
				
					else 
						i++;
					tu *=10;
					}
				else{
					
					if (flag == 1){
				
						aTP [i] = tu / mau;
					}
			
				tu = tu % mau;
			
				}
				
			}
	
		for (int k=0; k<6; k++)
		cout <<" aTP ["<<k<<"]: "<< aTP[k] <<endl;
	
		}

		int main(){
			int tu (35), mau (101); // ví dụ kết quả từ bước 1 là 35/100
			tp (tu, mau);
	
	
			return 0;
		}
	
	Nhưng sau đó mình mới hiểu số chính xác là nó phải chính xác tới 1 con số luôn, tức tồn tại 1 epsilon e rất nhỏ sao cho e - 10^-6 > 0. Khi đó bài toán sẽ đơn giản hơn, khi n = 10 ^ 6 và 1/n = 10 ^ -6 thì dừng vòng lặp.

## Câu 8:

	Mình phải xét điều kiện không những kỹ càng mà còn phải làm bài mình tối ưu, ví dự xét điều kiện tam giác vuông trước hay tam giác cân trước thì bài làm sẽ gọn hơn, và mình thấy xét điều kiện tam giác vuông thì bài gọn hơn hướng kia.

## Câu 9:

	Có thể nói đây là câu khá gần gũi với người mới. Ta có 2 cách hiểu về số chính phương:
	
		1. 1 số nguyên bình phương lên bằng số được xét thì số được xét là số chính phương (hay nói cách khác số chính phương là bình phương của 1 số nguyên).
		2. số được xét căn xuống là 1 số nguyên thì số được xét là số chính phương.
	
	Từ 2 cách hiểu này ta có 2 hướng làm:
	
		1. Chạy 1 vòng lặp tịnh tiến số i sao cho bình phương của i so sánh với số được xét. Nếu bằng thì đó là số chính phương.
		2. Nếu được phép dùng hàm sqrt() thì có khá nhiều cách giải, 1 cách mà mình thấy khá đơn giản là là sqrt(số được xét) và ép kiểu nó thành int và lưu vào biến t. Nếu t^2 = số được xét thì số được xét là số chính phương.
		
## Câu 10:
	
	Có rất nhiều cách, có thể dùng hàm log nếu được phép. Tuy nhiên, mình có 1 cách đơn giản thế này:
	
	Chạy vòng lặp so sánh 5^m với số được xét, nếu 5^m > số được xét thì số được xét không có dạng 5^m và dừng vòng lặp, ngược lại thì so sánh 5^m có bằng số được xét không, nếu không thì 5^m nhân 5 và bắt đầu vòng lặp mới.
	Và đây là code minh họa:
		int main()
		{
			int n10, m (0), so_sanh(1);
		
			cout <<"Nhap n: "; cin >> n10;
			
			while (so_sanh <= n10){
				
				if (n10 == so_sanh)
				{
					cout << "n thoa man~ de bai\n";
					break; 
				}
				else 
					m++;
				
				so_sanh *= 5; 
				if (so_sanh > n10 )
					cout <<"n khong thoa man~\n";
			}
		}

















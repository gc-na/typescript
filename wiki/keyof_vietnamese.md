<!--
Meta Description: # Tìm Hiểu Về Từ Khóa "keyof" Trong TypeScript ## Tóm Tắt Từ khóa `keyof` trong TypeScript cho phép bạn lấy danh sách các khóa (keys) của một kiểu đối...
Meta Keywords: kiểu, các, một, keyof, khóa
-->

# Tìm Hiểu Về Từ Khóa "keyof" Trong TypeScript

## Tóm Tắt
Từ khóa `keyof` trong TypeScript cho phép bạn lấy danh sách các khóa (keys) của một kiểu đối tượng, tạo ra một kiểu mới là một tập hợp các tên thuộc tính của đối tượng đó. 

## Tài Liệu
Từ khóa `keyof` được sử dụng để tạo ra một kiểu mới từ các thuộc tính của một kiểu đối tượng đã định nghĩa. Điều này giúp tăng cường khả năng kiểm tra kiểu trong TypeScript, khiến cho mã nguồn an toàn hơn và dễ bảo trì hơn.

### Mục đích
- Tạo ra kiểu của danh sách các khóa từ một kiểu đối tượng.
- Hỗ trợ việc truy cập và thao tác với các thuộc tính của đối tượng một cách an toàn.

### Cách Sử Dụng
Cú pháp cơ bản của `keyof` là:

```typescript
keyof T
```

Trong đó `T` là kiểu đối tượng mà bạn muốn lấy các khóa. Kết quả trả về sẽ là một kiểu mới chứa tất cả các khóa của `T`.

### Ví dụ
Dưới đây là một vài ví dụ minh họa cho việc sử dụng từ khóa `keyof`:

```typescript
interface Person {
    name: string;
    age: number;
}

type PersonKeys = keyof Person; // Kết quả: "name" | "age"

const key: PersonKeys = "name"; // Hợp lệ
// const invalidKey: PersonKeys = "address"; // Không hợp lệ
```

Trong ví dụ trên, `PersonKeys` sẽ là một kiểu mới chỉ có thể nhận giá trị là `"name"` hoặc `"age"`.

## Giải Thích
Một số cạm bẫy và lưu ý khi sử dụng `keyof`:

- **Không sử dụng trên kiểu không phải đối tượng**: `keyof` chỉ hoạt động với các kiểu đối tượng. Nếu bạn cố gắng sử dụng với kiểu nguyên thủy như `string` hay `number`, TypeScript sẽ thông báo lỗi.
  
- **Tính kế thừa**: Nếu bạn có một kiểu đối tượng kế thừa từ một kiểu khác, `keyof` sẽ trả về tất cả các khóa từ cả hai kiểu.

- **Tương hợp với các loại generic**: `keyof` có thể kết hợp với các loại generic để tạo ra các kiểu linh hoạt hơn trong các hàm và lớp.

## Tóm Tắt Một Dòng
Từ khóa `keyof` trong TypeScript cho phép bạn lấy danh sách các khóa của một kiểu đối tượng, tạo ra kiểu mới từ các thuộc tính đó.
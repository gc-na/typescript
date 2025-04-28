<!--
Meta Description: # Sử Dụng "const" Trong TypeScript: Khóa Học Cơ Bản Và Ứng Dụng ## Tóm Tắt "const" là một từ khóa trong TypeScript (và JavaScript) được sử dụng để kha...
Meta Keywords: biến, const, thể, khai, báo
-->

# Sử Dụng "const" Trong TypeScript: Khóa Học Cơ Bản Và Ứng Dụng

## Tóm Tắt
"const" là một từ khóa trong TypeScript (và JavaScript) được sử dụng để khai báo biến với giá trị không thể thay đổi sau khi đã gán. Nó giúp đảm bảo rằng biến sẽ không bị thay đổi, tạo ra mã an toàn và dễ bảo trì hơn.

## Tài Liệu
### Mục Đích
Từ khóa "const" được sử dụng để khai báo biến hằng. Điều này có nghĩa là một khi biến đã được gán một giá trị, bạn không thể gán lại giá trị mới cho biến đó. "const" giúp ngăn chặn việc thay đổi giá trị của biến, từ đó giảm thiểu các lỗi không mong muốn trong quá trình lập trình.

### Cách Sử Dụng
Để sử dụng "const", bạn chỉ cần khai báo biến như sau:

```typescript
const tenBien = giaTri;
```

- "tenBien" là tên biến mà bạn muốn tạo.
- "giaTri" là giá trị mà bạn muốn gán cho biến đó.

Khi sử dụng "const", một số điều cần lưu ý:
- **Khác biệt với "let" và "var":** Biến được khai báo bằng "let" và "var" có thể được thay đổi giá trị, trong khi biến "const" không thể.
- **Phạm vi block:** Biến "const" có phạm vi block, nghĩa là nó chỉ có hiệu lực trong block mà nó được khai báo.

### Chi Tiết
Khi sử dụng "const", bạn có thể khai báo cả kiểu dữ liệu cho biến:

```typescript
const soNguyen: number = 10;
```

- Trong ví dụ này, biến "soNguyen" được khai báo với kiểu dữ liệu là số nguyên và giá trị là 10.

Lưu ý rằng với các kiểu dữ liệu phức tạp như mảng hay đối tượng, bạn vẫn có thể thay đổi nội dung bên trong, nhưng không thể gán lại biến:

```typescript
const mang: number[] = [1, 2, 3];
mang.push(4); // Hợp lệ
mang = [5, 6, 7]; // Không hợp lệ
```

## Ví Dụ
Dưới đây là một số ví dụ minh họa cho việc sử dụng "const":

### Ví dụ 1: Khai báo biến hằng
```typescript
const ten = "John Doe";
console.log(ten); // Kết quả: John Doe
```

### Ví dụ 2: Khai báo mảng
```typescript
const soThich: string[] = ["Đọc sách", "Chạy bộ", "Chơi nhạc"];
soThich.push("Du lịch"); // Hợp lệ
console.log(soThich); // Kết quả: ["Đọc sách", "Chạy bộ", "Chơi nhạc", "Du lịch"]
```

### Ví dụ 3: Khai báo đối tượng
```typescript
const nguoi = {
  ten: "Jane",
  tuoi: 28,
};
nguoi.tuoi = 29; // Hợp lệ
console.log(nguoi); // Kết quả: { ten: "Jane", tuoi: 29 }
```

## Giải Thích
Dưới đây là một số điểm cần lưu ý khi sử dụng "const":
- **Không thể gán lại giá trị:** Bạn không thể thay đổi giá trị của biến đã khai báo bằng "const", điều này có thể gây ra lỗi nếu bạn cố gắng thực hiện.
- **Phạm vi block:** Biến "const" chỉ có thể truy cập trong block mà nó được khai báo.
- **Chỉ áp dụng cho tham chiếu:** Đối với các kiểu dữ liệu phức tạp, bạn vẫn có thể thay đổi nội dung bên trong nhưng không thể thay đổi tham chiếu của biến.

## Tóm Tắt Một Dòng
"const" trong TypeScript được sử dụng để khai báo biến hằng, giúp đảm bảo rằng giá trị của biến không thể thay đổi sau khi đã được gán.
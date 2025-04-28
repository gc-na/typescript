<!--
Meta Description: # Enum trong TypeScript: Tìm Hiểu và Sử Dụng ## Tóm Tắt Enum (biến liệt kê) trong TypeScript cho phép lập trình viên định nghĩa một tập hợp các hằng s...
Meta Keywords: giá, trị, enum, typescript, dụng
-->

# Enum trong TypeScript: Tìm Hiểu và Sử Dụng

## Tóm Tắt
Enum (biến liệt kê) trong TypeScript cho phép lập trình viên định nghĩa một tập hợp các hằng số có tên, giúp làm cho mã nguồn trở nên dễ đọc và dễ bảo trì hơn.

## Tài Liệu
### Mục Đích
Enum trong TypeScript được sử dụng để định nghĩa một tập hợp các giá trị có thể, thường là các hằng số có liên quan. Điều này giúp mã nguồn trở nên rõ ràng hơn và giảm thiểu lỗi khi sử dụng các giá trị.

### Cách Sử Dụng
Để khai báo một enum, bạn sử dụng từ khóa `enum`, theo sau là tên của enum và các giá trị bên trong dấu ngoặc nhọn. Dưới đây là cú pháp cơ bản:

```typescript
enum TenEnum {
    GiaTri1,
    GiaTri2,
    GiaTri3
}
```

### Chi Tiết
- **Giá Trị Mặc Định**: Nếu không chỉ định giá trị cụ thể cho các thành phần của enum, TypeScript sẽ tự động gán giá trị bắt đầu từ 0 cho mỗi thành phần.
- **Giá Trị Tùy Chọn**: Bạn có thể chỉ định giá trị cho từng thành phần, ví dụ:
  
```typescript
enum Màu {
    Đỏ = "Đỏ",
    Xanh = "Xanh",
    Vàng = "Vàng"
}
```

- **Đồng Bộ Hóa với Giá Trị Số**: Enum có thể chứa cả giá trị chuỗi và giá trị số. Bạn có thể sử dụng chúng trong các tĩnh từ khác nhau.

## Ví Dụ
### Ví Dụ Cơ Bản

```typescript
enum NgàyTrongTuần {
    ChủNhật,
    ThứHai,
    ThứBa,
    ThứTư,
    ThứNăm,
    ThứSáu,
    ThứBảy
}

let hômNay: NgàyTrongTuần = NgàyTrongTuần.ThứBa;
console.log(hômNay); // Kết quả: 2
```

### Ví Dụ với Giá Trị Tùy Chọn

```typescript
enum TrạngThái {
    ĐangChạy = "Đang Chạy",
    ĐãHoànThành = "Đã Hoàn Thành",
    ĐãHủy = "Đã Hủy"
}

let trạngTháiHiệnTại: TrạngThái = TrạngThái.ĐangChạy;
console.log(trạngTháiHiệnTại); // Kết quả: Đang Chạy
```

## Giải Thích
### Những Lỗi Thường Gặp
- **Không Đặt Tên Rõ Ràng**: Đặt tên cho enum không rõ ràng có thể gây nhầm lẫn. Hãy sử dụng tên thể hiện ý nghĩa rõ ràng.
- **Mê Hoặc Giá Trị**: Nếu có nhiều enum với giá trị tương tự, cần chú ý đến ngữ cảnh khi sử dụng để tránh nhầm lẫn.
- **Không Xác Định Giá Trị**: Nếu không chỉ định giá trị, enum sẽ tự động gán giá trị bắt đầu từ 0, điều này có thể gây ra sự cố nếu bạn mong đợi giá trị khác.

## Tóm Tắt Một Câu
Enum trong TypeScript là một công cụ mạnh mẽ để định nghĩa và quản lý các tập hợp giá trị hằng số, giúp mã nguồn trở nên rõ ràng và dễ bảo trì.
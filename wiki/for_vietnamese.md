<!--
Meta Description: # Câu Lệnh "for" trong TypeScript: Hướng Dẫn Chi Tiết ## Tóm tắt Câu lệnh "for" trong TypeScript là một cách hiệu quả để lặp qua các phần tử của mảng ...
Meta Keywords: lặp, trong, typescript, một, được
-->

# Câu Lệnh "for" trong TypeScript: Hướng Dẫn Chi Tiết

## Tóm tắt
Câu lệnh "for" trong TypeScript là một cách hiệu quả để lặp qua các phần tử của mảng hoặc đối tượng, cho phép lập trình viên thực hiện các thao tác lặp lại dễ dàng và linh hoạt.

## Tài liệu
Câu lệnh "for" trong TypeScript được sử dụng để lặp lại một khối mã nhiều lần. Đây là một trong những cấu trúc lặp phổ biến nhất trong lập trình. Câu lệnh "for" có ba phần chính: khởi tạo, điều kiện và cập nhật.

### Cấu trúc cơ bản
```typescript
for (khởi_tạo; điều_kiện; cập_nhật) {
    // Khối mã sẽ thực thi
}
```

- **Khởi tạo**: Được thực hiện một lần trước khi vòng lặp bắt đầu. Thường dùng để khai báo và khởi tạo biến đếm.
- **Điều kiện**: Được kiểm tra trước mỗi lần lặp. Nếu điều kiện là true, khối mã sẽ được thực thi. Nếu false, vòng lặp sẽ dừng lại.
- **Cập nhật**: Được thực hiện sau mỗi lần lặp. Thường dùng để thay đổi giá trị của biến đếm.

### Ví dụ sử dụng
1. **Lặp qua số nguyên từ 0 đến 4**:
    ```typescript
    for (let i = 0; i < 5; i++) {
        console.log(i);
    }
    ```

2. **Lặp qua mảng**:
    ```typescript
    const fruits: string[] = ["Táo", "Chuối", "Cam"];
    for (let i = 0; i < fruits.length; i++) {
        console.log(fruits[i]);
    }
    ```

3. **Lặp ngược**:
    ```typescript
    for (let i = 5; i > 0; i--) {
        console.log(i);
    }
    ```

## Giải thích
Mặc dù câu lệnh "for" rất mạnh mẽ, nhưng có một số điểm cần lưu ý khi sử dụng:

- **Quá trình lặp vô hạn**: Nếu điều kiện không bao giờ trở thành false, vòng lặp sẽ chạy mãi mãi, dẫn đến treo ứng dụng.
- **Biến ngoài phạm vi**: Nếu biến được khai báo trong khối lặp không được sử dụng bên ngoài vòng lặp, điều này có thể gây nhầm lẫn trong việc theo dõi các giá trị.
- **Thay đổi mảng trong vòng lặp**: Nếu bạn thay đổi kích thước mảng trong khi lặp qua nó, bạn có thể gặp phải kết quả không mong muốn.

## Tóm tắt một dòng
Câu lệnh "for" trong TypeScript cho phép lặp lại một khối mã theo điều kiện xác định, giúp quản lý và xử lý dữ liệu một cách hiệu quả.
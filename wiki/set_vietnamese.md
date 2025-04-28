<!--
Meta Description: # Tập Hợp (Set) trong TypeScript: Cách Sử Dụng và Ứng Dụng ## Tóm Tắt Trong TypeScript, `Set` là một đối tượng cho phép lưu trữ các giá trị duy nhất, ...
Meta Keywords: set, một, các, trong, typescript
-->

# Tập Hợp (Set) trong TypeScript: Cách Sử Dụng và Ứng Dụng

## Tóm Tắt
Trong TypeScript, `Set` là một đối tượng cho phép lưu trữ các giá trị duy nhất, không trùng lặp. Nó hỗ trợ các thao tác như thêm, xóa và kiểm tra sự tồn tại của các phần tử, giúp quản lý tập hợp dữ liệu một cách hiệu quả.

## Tài Liệu
`Set` là một cấu trúc dữ liệu được giới thiệu trong ECMAScript 2015 (ES6), cho phép lưu trữ các giá trị duy nhất. Các giá trị trong tập hợp có thể là bất kỳ loại dữ liệu nào, bao gồm cả đối tượng và mảng. Điều này giúp lập trình viên dễ dàng xử lý và quản lý bộ dữ liệu mà không cần lo lắng về việc trùng lặp.

### Cách Sử Dụng
Để sử dụng `Set` trong TypeScript, trước tiên bạn cần khởi tạo một đối tượng `Set`. Dưới đây là một số phương thức chính của `Set`:

- **Khởi tạo**: Bạn có thể khởi tạo một `Set` bằng cách sử dụng từ khóa `new`.
  
  ```typescript
  const mySet = new Set<number>();
  ```

- **Thêm Phần Tử**: Sử dụng phương thức `add()` để thêm phần tử vào `Set`.
  
  ```typescript
  mySet.add(1);
  mySet.add(2);
  ```

- **Xóa Phần Tử**: Sử dụng phương thức `delete()` để xóa phần tử.
  
  ```typescript
  mySet.delete(1);
  ```

- **Kiểm Tra Sự Tồn Tại**: Sử dụng phương thức `has()` để kiểm tra xem một phần tử có tồn tại trong `Set` hay không.
  
  ```typescript
  console.log(mySet.has(2)); // true
  ```

- **Lấy Kích Thước**: Bạn có thể lấy số lượng phần tử trong `Set` bằng thuộc tính `size`.
  
  ```typescript
  console.log(mySet.size); // 1
  ```

- **Lặp Qua Các Phần Tử**: Bạn có thể sử dụng phương thức `forEach()` để lặp qua tất cả các phần tử trong `Set`.
  
  ```typescript
  mySet.forEach(value => {
      console.log(value);
  });
  ```

## Ví Dụ
### Ví Dụ Cơ Bản
Dưới đây là một ví dụ đơn giản về cách sử dụng `Set` trong TypeScript:

```typescript
const numbers = new Set<number>();
numbers.add(1);
numbers.add(2);
numbers.add(2); // Không bị thêm vì đã tồn tại

console.log(numbers.size); // 2
console.log(numbers.has(1)); // true
numbers.delete(1);
console.log(numbers.has(1)); // false

numbers.forEach(num => {
    console.log(num); // In ra 2
});
```

## Giải Thích
Khi làm việc với `Set`, có một số điểm cần lưu ý:

- **Giá trị Duy Nhất**: Một trong những tính năng quan trọng nhất của `Set` là nó chỉ lưu trữ các giá trị duy nhất. Nếu bạn cố gắng thêm một giá trị đã tồn tại, nó sẽ không được thêm vào.
  
- **So Sánh Tham Chiếu**: Đối với các đối tượng, `Set` sẽ kiểm tra sự tồn tại dựa trên tham chiếu, không phải giá trị. Điều này có nghĩa là hai đối tượng khác nhau về tham chiếu sẽ được coi là khác nhau ngay cả khi chúng có cùng giá trị.

- **Thứ Tự Thêm**: Các phần tử trong `Set` được lưu trữ theo thứ tự mà chúng được thêm vào, và bạn có thể lặp qua chúng theo thứ tự này.

## Tóm Tắt Một Dòng
`Set` trong TypeScript là một cấu trúc dữ liệu cho phép lưu trữ các giá trị duy nhất, hỗ trợ các thao tác thêm, xóa và kiểm tra sự tồn tại của các phần tử.
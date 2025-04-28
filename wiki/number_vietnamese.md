<!--
Meta Description: # Số Trong TypeScript: Cách Sử Dụng và Tính Năng ## Tóm tắt Trong TypeScript, kiểu dữ liệu "number" được sử dụng để đại diện cho các giá trị số, bao g...
Meta Keywords: number, typescript, let, kiểu, các
-->

# Số Trong TypeScript: Cách Sử Dụng và Tính Năng

## Tóm tắt
Trong TypeScript, kiểu dữ liệu "number" được sử dụng để đại diện cho các giá trị số, bao gồm cả số nguyên và số thập phân. Kiểu này cho phép thực hiện các phép toán số học và là một phần quan trọng trong lập trình.

## Tài liệu
Kiểu "number" trong TypeScript được thiết kế để xử lý tất cả các số, bao gồm cả số nguyên, số thực và số âm. Mặc dù TypeScript là một ngôn ngữ tĩnh, nó cho phép lập trình viên linh hoạt trong việc sử dụng các giá trị số mà không cần phải phân biệt giữa các kiểu số khác nhau. 

### Mục đích
- Cung cấp một kiểu dữ liệu đồng nhất cho mọi loại số.
- Hỗ trợ các phép toán số học cơ bản và nâng cao.

### Cách sử dụng
Để khai báo một biến kiểu số trong TypeScript, bạn có thể sử dụng cú pháp sau:

```typescript
let a: number = 5;
let b: number = 10.5;
```

Bạn cũng có thể thực hiện các phép toán số học như:

```typescript
let sum: number = a + b; // Kết quả: 15.5
let product: number = a * b; // Kết quả: 52.5
```

## Ví dụ
### Ví dụ 1: Khai báo và sử dụng biến kiểu số
```typescript
let age: number = 25;
console.log(`Tuổi của tôi là: ${age}`);
```

### Ví dụ 2: Thực hiện phép toán
```typescript
let x: number = 20;
let y: number = 30;
let total: number = x + y;
console.log(`Tổng của x và y là: ${total}`); // Kết quả: 50
```

### Ví dụ 3: Sử dụng số thập phân
```typescript
let price: number = 99.99;
let tax: number = 0.1; // 10%
let totalPrice: number = price + (price * tax);
console.log(`Giá cuối cùng là: ${totalPrice}`); // Kết quả: 109.89
```

## Giải thích
Mặc dù kiểu "number" trong TypeScript rất linh hoạt, có một số điểm cần lưu ý:
- Không phân biệt giữa số nguyên và số thực: Tất cả đều được biểu diễn dưới dạng "number".
- Giới hạn giá trị: TypeScript sử dụng kiểu dữ liệu số 64-bit, nên có thể gặp một số vấn đề khi làm việc với các số rất lớn hoặc rất nhỏ do giới hạn độ chính xác.

## Tóm tắt một dòng
Kiểu "number" trong TypeScript cho phép lập trình viên làm việc với tất cả các giá trị số một cách linh hoạt và hiệu quả.
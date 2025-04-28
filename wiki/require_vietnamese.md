<!--
Meta Description: # Cách sử dụng "require" trong TypeScript: Hướng dẫn chi tiết ## Tóm Tắt Trong TypeScript, `require` là một phương thức được sử dụng để nhập các mô-đu...
Meta Keywords: đun, bạn, dụng, require, typescript
-->

# Cách sử dụng "require" trong TypeScript: Hướng dẫn chi tiết

## Tóm Tắt
Trong TypeScript, `require` là một phương thức được sử dụng để nhập các mô-đun, cho phép bạn tái sử dụng mã nguồn và tổ chức các tệp mã lập trình một cách hiệu quả.

## Tài liệu
`require` là một phần của hệ thống mô-đun CommonJS, cho phép bạn nhập các mô-đun trong TypeScript. Qua đó, bạn có thể sử dụng các chức năng và biến đã được định nghĩa trong mô-đun khác. Điều này cực kỳ hữu ích trong việc chia nhỏ ứng dụng lớn thành các phần nhỏ hơn, dễ quản lý hơn.

### Cách sử dụng
Để sử dụng `require`, bạn cần cài đặt TypeScript và Node.js. Trong mã nguồn của bạn, bạn có thể sử dụng cú pháp sau:

```typescript
const <tên_mô-đun> = require('<đường_dẫn_mô-đun>');
```

### Chi tiết
- `tên_mô-đun`: Tên biến mà bạn muốn sử dụng để tham chiếu đến mô-đun đã nhập.
- `đường_dẫn_mô-đun`: Đường dẫn đến tệp mô-đun mà bạn muốn nhập, có thể là tuyệt đối hoặc tương đối.

Chú ý rằng khi sử dụng `require`, nếu mô-đun bạn nhập không tồn tại hoặc có lỗi trong mã nguồn, việc nhập sẽ thất bại và ném ra lỗi.

## Ví dụ
### Ví dụ cơ bản
Giả sử bạn có một mô-đun `mathUtils.ts` như sau:

```typescript
// mathUtils.ts
export function add(a: number, b: number): number {
    return a + b;
}
```

Bạn có thể nhập và sử dụng mô-đun này trong một tệp khác như sau:

```typescript
// main.ts
const mathUtils = require('./mathUtils');

const sum = mathUtils.add(5, 10);
console.log(sum); // Kết quả: 15
```

### Ví dụ với mô-đun bên ngoài
Đối với các mô-đun bên ngoài (như thư viện npm), bạn có thể sử dụng `require` như sau:

```typescript
const express = require('express');
const app = express();
```

## Giải thích
### Những điều cần lưu ý
- **Kiểm tra Type**: TypeScript không cung cấp kiểm tra kiểu cho các mô-đun được nhập bằng `require`. Để có lợi ích từ tính năng kiểu của TypeScript, bạn nên sử dụng cú pháp `import` thay vì `require` khi làm việc với các mô-đun TypeScript.
  
- **Thư viện không có kiểu**: Nếu bạn sử dụng mô-đun không có tệp định nghĩa kiểu (typings), bạn có thể gặp phải lỗi kiểu. Bạn có thể tạo tệp `.d.ts` để định nghĩa kiểu cho mô-đun đó.

- **Chạy trong môi trường không phải Node**: `require` chủ yếu được sử dụng trong môi trường Node.js. Nếu bạn chạy mã TypeScript trong trình duyệt, bạn có thể cần phải biên dịch mã sang ES Module và sử dụng cú pháp `import`.

## Tóm tắt một câu
`require` trong TypeScript là phương thức dùng để nhập mô-đun, giúp tổ chức mã nguồn và tăng tính tái sử dụng.
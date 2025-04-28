<!--
Meta Description: # Module trong TypeScript: Hướng Dẫn Chi Tiết và Tối Ưu SEO ## Tóm Tắt Module trong TypeScript là một cách tổ chức mã nguồn, giúp chia nhỏ ứng dụng th...
Meta Keywords: module, typescript, dụng, trong, các
-->

# Module trong TypeScript: Hướng Dẫn Chi Tiết và Tối Ưu SEO

## Tóm Tắt
Module trong TypeScript là một cách tổ chức mã nguồn, giúp chia nhỏ ứng dụng thành các phần riêng biệt, dễ quản lý và tái sử dụng. Chúng cho phép quản lý không gian tên và tránh xung đột giữa các biến, hàm và lớp.

## Tài Liệu
### Mục Đích
Module trong TypeScript được sử dụng để nhóm các phần mã lại với nhau, tạo ra các phần tử có thể tái sử dụng và tổ chức tốt hơn. Chúng giúp cải thiện khả năng bảo trì và khả năng mở rộng của ứng dụng.

### Cách Sử Dụng
Để tạo một module trong TypeScript, bạn có thể sử dụng từ khóa `export` để xuất các thành phần như biến, hàm, hoặc lớp từ module, và `import` để nhập các thành phần này vào một module khác.

#### Cú Pháp Cơ Bản
- Xuất biến: 
  ```typescript
  export const PI = 3.14;
  ```
- Xuất hàm:
  ```typescript
  export function add(x: number, y: number): number {
      return x + y;
  }
  ```
- Nhập module:
  ```typescript
  import { PI, add } from './math';
  ```

### Chi Tiết
- Các module trong TypeScript có thể được định nghĩa trong các file riêng biệt hoặc trong cùng một file.
- Khi sử dụng `export`, bạn có thể xuất nhiều thành phần từ một module và nhập chúng vào module khác.
- TypeScript hỗ trợ cả module CommonJS và ES6, cho phép bạn chọn cách tổ chức mã phù hợp với nhu cầu của dự án.

## Ví Dụ
### Ví Dụ 1: Tạo và Sử Dụng Module
**math.ts**
```typescript
export const PI = 3.14;

export function add(x: number, y: number): number {
    return x + y;
}
```

**app.ts**
```typescript
import { PI, add } from './math';

console.log(`Giá trị của PI là: ${PI}`);
console.log(`Tổng của 2 và 3 là: ${add(2, 3)}`);
```

### Ví Dụ 2: Xuất Mặc Định
**defaultExport.ts**
```typescript
export default function greet(name: string): string {
    return `Xin chào, ${name}!`;
}
```

**app.ts**
```typescript
import greet from './defaultExport';

console.log(greet('Thế giới'));
```

## Giải Thích
- **Xung Đột Tên**: Khi sử dụng nhiều module, bạn có thể gặp phải xung đột tên. Để tránh điều này, hãy sử dụng alias khi nhập hoặc xuất thành phần.
- **Module Cục Bộ**: Tùy thuộc vào cấu trúc dự án, bạn có thể cần sử dụng module cục bộ để giảm thiểu khả năng xung đột và cải thiện khả năng bảo trì.
- **Chạy Mã**: Đảm bảo rằng bạn đã cấu hình TypeScript để biên dịch các module đúng cách, sử dụng cấu hình `module` trong `tsconfig.json`.

## Tóm Tắt Một Câu
Module trong TypeScript là công cụ mạnh mẽ giúp tổ chức mã và quản lý không gian tên, tối ưu hóa khả năng tái sử dụng và bảo trì ứng dụng.
<!--
Meta Description: # Xuất (Export) trong TypeScript: Hướng Dẫn Chi Tiết ## Tóm tắt Từ khóa `export` trong TypeScript cho phép bạn chia sẻ các biến, hàm, lớp, và kiểu dữ ...
Meta Keywords: xuất, export, typescript, bạn, các
-->

# Xuất (Export) trong TypeScript: Hướng Dẫn Chi Tiết

## Tóm tắt
Từ khóa `export` trong TypeScript cho phép bạn chia sẻ các biến, hàm, lớp, và kiểu dữ liệu từ một tệp (file) này sang tệp khác, giúp tổ chức mã nguồn và tái sử dụng dễ dàng hơn.

## Tài liệu

### Mục đích
`export` được sử dụng để đánh dấu các thành phần mà bạn muốn có thể sử dụng từ các tệp khác. Việc sử dụng `export` giúp mã nguồn của bạn trở nên rõ ràng và dễ quản lý hơn, đặc biệt là trong các dự án lớn.

### Cách sử dụng
Có hai loại xuất trong TypeScript:
1. **Xuất tên (Named Exports)**: Cho phép bạn xuất nhiều thành phần từ một tệp.
2. **Xuất mặc định (Default Export)**: Chỉ cho phép xuất một thành phần duy nhất từ một tệp.

### Chi tiết
- **Xuất tên**:
  ```typescript
  // myModule.ts
  export const myVariable = 42;
  export function myFunction() {
      console.log("Hello, world!");
  }
  ```

- **Xuất mặc định**:
  ```typescript
  // myModule.ts
  const myDefaultFunction = () => {
      console.log("This is the default export");
  };
  export default myDefaultFunction;
  ```

Để nhập các thành phần đã xuất, bạn có thể sử dụng từ khóa `import`:
- **Nhập tên**:
  ```typescript
  // main.ts
  import { myVariable, myFunction } from './myModule';
  ```

- **Nhập mặc định**:
  ```typescript
  // main.ts
  import myDefaultFunction from './myModule';
  ```

## Ví dụ

### Xuất tên
```typescript
// shapes.ts
export const PI = 3.14;
export function calculateArea(radius: number) {
    return PI * radius * radius;
}

// main.ts
import { PI, calculateArea } from './shapes';

console.log(calculateArea(5)); // 78.5
```

### Xuất mặc định
```typescript
// greeter.ts
const greet = (name: string) => `Hello, ${name}!`;
export default greet;

// main.ts
import greet from './greeter';

console.log(greet('Alice')); // Hello, Alice!
```

## Giải thích
- **Common pitfalls**: Một số lập trình viên mới có thể gặp khó khăn khi phân biệt giữa xuất tên và xuất mặc định. Hãy nhớ rằng bạn có thể xuất nhiều thành phần với xuất tên nhưng chỉ có một thành phần với xuất mặc định.
- **Gotchas**: Khi nhập các thành phần, bạn cần đảm bảo rằng tên bạn sử dụng trong `import` phải khớp chính xác với tên đã xuất. Nếu không, TypeScript sẽ báo lỗi.

## Tóm tắt một dòng
Từ khóa `export` trong TypeScript cho phép chia sẻ và tái sử dụng các thành phần mã nguồn giữa các tệp khác nhau một cách dễ dàng và hiệu quả.
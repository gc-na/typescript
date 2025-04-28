<!--
Meta Description: # Từ Khóa "import" Trong TypeScript: Cách Sử Dụng và Ví Dụ ## Tóm Tắt Từ khóa "import" trong TypeScript được sử dụng để nhập các mô-đun, cho phép bạn ...
Meta Keywords: đun, typescript, import, dụng, các
-->

# Từ Khóa "import" Trong TypeScript: Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Từ khóa "import" trong TypeScript được sử dụng để nhập các mô-đun, cho phép bạn tái sử dụng mã và phân chia ứng dụng của mình thành các phần nhỏ, dễ quản lý.

## Tài Liệu
Từ khóa "import" cho phép bạn nhập các thành phần từ các mô-đun khác, giúp tổ chức mã nguồn của bạn một cách hiệu quả. TypeScript hỗ trợ các mô-đun ES6, cho phép bạn nhập các biến, hàm, lớp, hoặc toàn bộ mô-đun. Với TypeScript, bạn có thể sử dụng cú pháp "import" để đưa vào các thành phần mà bạn cần từ các tập tin khác, giúp tăng cường khả năng tái sử dụng và quản lý mã.

### Cú Pháp
Cú pháp cơ bản của từ khóa "import" như sau:

```typescript
import { TênThànhPhần } from 'đường/dẫn/tới/mô-đun';
```

Bạn cũng có thể nhập toàn bộ mô-đun và gán cho một biến:

```typescript
import * as TênBiến from 'đường/dẫn/tới/mô-đun';
```

Hoặc nhập một mô-đun mặc định:

```typescript
import TênMặcĐịnh from 'đường/dẫn/tới/mô-đun';
```

## Ví Dụ
### Ví dụ 1: Nhập một hàm
```typescript
// math.ts
export function add(a: number, b: number): number {
    return a + b;
}

// main.ts
import { add } from './math';

console.log(add(5, 3)); // Kết quả: 8
```

### Ví dụ 2: Nhập toàn bộ mô-đun
```typescript
// utils.ts
export function log(message: string): void {
    console.log(message);
}

// main.ts
import * as Utils from './utils';

Utils.log('Hello, World!'); // Kết quả: Hello, World!
```

### Ví dụ 3: Nhập mô-đun mặc định
```typescript
// greeting.ts
const greeting = 'Hello, TypeScript!';
export default greeting;

// main.ts
import greeting from './greeting';

console.log(greeting); // Kết quả: Hello, TypeScript!
```

## Giải Thích
Khi sử dụng từ khóa "import", có một số điểm cần lưu ý:

- **Đường dẫn tương đối và tuyệt đối**: Đảm bảo rằng đường dẫn tới mô-đun phải chính xác. Sử dụng đường dẫn tương đối (`./` hoặc `../`) nếu mô-đun nằm trong cùng một thư mục hoặc thư mục cha.
- **Tên thành phần**: Tên bạn sử dụng để nhập các thành phần phải khớp với tên đã xuất ra trong mô-đun.
- **Lỗi khi không tìm thấy mô-đun**: Nếu không tìm thấy mô-đun, TypeScript sẽ báo lỗi. Hãy kiểm tra đường dẫn và tên mô-đun.
- **Cấu hình TypeScript**: Đảm bảo rằng cấu hình TypeScript (tsconfig.json) của bạn cho phép sử dụng mô-đun.

## Tóm Tắt Một Dòng
Từ khóa "import" trong TypeScript cho phép bạn nhập và sử dụng các thành phần từ các mô-đun khác, giúp tổ chức mã hiệu quả hơn.
<!--
Meta Description: # Tìm Hiểu Về "await" trong TypeScript: Cách Sử Dụng và Ví Dụ ## Tóm Tắt `await` là một từ khóa trong TypeScript được sử dụng để chờ một Promise hoàn ...
Meta Keywords: await, dụng, promise, được, không
-->

# Tìm Hiểu Về "await" trong TypeScript: Cách Sử Dụng và Ví Dụ

## Tóm Tắt
`await` là một từ khóa trong TypeScript được sử dụng để chờ một Promise hoàn thành. Nó giúp làm cho mã bất đồng bộ trở nên dễ đọc hơn bằng cách cho phép viết mã theo cách đồng bộ.

## Tài Liệu
### Mục Đích
Từ khóa `await` chỉ có thể được sử dụng bên trong một hàm được định nghĩa với từ khóa `async`. Mục đích của `await` là tạm dừng thực thi mã cho đến khi Promise được giải quyết (resolved) hoặc bị từ chối (rejected).

### Cách Sử Dụng
Để sử dụng `await`, bạn cần:
1. Định nghĩa một hàm với từ khóa `async`.
2. Sử dụng `await` trước một Promise.

Cú pháp:
```typescript
async function exampleFunction() {
    const result = await someAsyncFunction();
    console.log(result);
}
```

### Chi Tiết
- `await` không chặn toàn bộ luồng thực thi của chương trình; nó chỉ tạm dừng hàm hiện tại.
- Nếu Promise bị từ chối, một lỗi sẽ được ném ra và bạn có thể xử lý nó bằng cách dùng `try...catch`.

## Ví Dụ
### Ví Dụ 1: Sử Dụng `await` với Fetch
```typescript
async function fetchData() {
    try {
        const response = await fetch('https://api.example.com/data');
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.error('Error fetching data:', error);
    }
}

fetchData();
```

### Ví Dụ 2: Đợi Nhiều Promise
```typescript
async function fetchMultiple() {
    const [data1, data2] = await Promise.all([
        fetch('https://api.example.com/data1').then(res => res.json()),
        fetch('https://api.example.com/data2').then(res => res.json())
    ]);
    console.log(data1, data2);
}

fetchMultiple();
```

## Giải Thích
### Cạm Bẫy Thường Gặp
- **Không Sử Dụng Trong Hàm Không Phải Async**: Nếu bạn cố gắng sử dụng `await` bên ngoài hàm `async`, bạn sẽ gặp lỗi cú pháp.
- **Quên Bắt Lỗi**: Nếu Promise bị từ chối mà không có `try...catch`, lỗi sẽ không được xử lý và có thể gây ra sự cố trong ứng dụng.

### Lưu Ý Thêm
- `await` có thể làm giảm hiệu suất nếu không được sử dụng đúng cách, đặc biệt là khi chờ nhiều Promise mà không sử dụng `Promise.all()`.
- `await` không thể được sử dụng trong các hàm không đồng bộ, vì vậy hãy luôn chắc chắn rằng hàm chứa `await` được định nghĩa là `async`.

## Tóm Tắt Một Dòng
`await` là một từ khóa trong TypeScript giúp tạm dừng thực thi mã cho đến khi Promise hoàn thành, làm cho mã bất đồng bộ dễ đọc hơn.
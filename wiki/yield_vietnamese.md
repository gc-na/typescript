<!--
Meta Description: # Từ Khóa "yield" Trong TypeScript: Hiểu Rõ Về Cách Sử Dụng ## Tóm Tắt Trong TypeScript, từ khóa `yield` được sử dụng trong các hàm generator để tạm d...
Meta Keywords: yield, hàm, generator, trả, một
-->

# Từ Khóa "yield" Trong TypeScript: Hiểu Rõ Về Cách Sử Dụng

## Tóm Tắt
Trong TypeScript, từ khóa `yield` được sử dụng trong các hàm generator để tạm dừng và trả về một giá trị, cho phép hàm tiếp tục thực thi từ nơi nó dừng lại trong lần gọi tiếp theo.

## Tài Liệu
### Mục Đích
Từ khóa `yield` cho phép bạn tạo ra các hàm generator. Những hàm này có thể trả về một chuỗi giá trị thay vì chỉ một giá trị duy nhất, nhờ vào khả năng tạm dừng và tiếp tục thực thi.

### Cách Sử Dụng
Để sử dụng `yield`, bạn cần khai báo một hàm generator bằng cách sử dụng từ khóa `function*`. Bên trong hàm này, bạn có thể sử dụng `yield` để trả về giá trị. Hàm generator sẽ trả về một đối tượng iterator, cho phép bạn duyệt qua các giá trị được trả về bằng cách gọi phương thức `next()`.

### Cú Pháp
```typescript
function* generatorFunction() {
    yield value1;
    yield value2;
    // ...
}
```

## Ví Dụ
### Ví Dụ Cơ Bản
```typescript
function* numberGenerator() {
    yield 1;
    yield 2;
    yield 3;
}

const gen = numberGenerator();

console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { value: 3, done: false }
console.log(gen.next()); // { value: undefined, done: true }
```

### Ví Dụ Sử Dụng Vòng Lặp
```typescript
function* fibonacci() {
    let a = 0, b = 1;
    while (true) {
        yield a;
        [a, b] = [b, a + b];
    }
}

const fib = fibonacci();
for (let i = 0; i < 5; i++) {
    console.log(fib.next().value); // 0, 1, 1, 2, 3
}
```

## Giải Thích
### Những Điều Cần Lưu Ý
- **Hàm Generator và Iterator:** Khi bạn gọi hàm generator, nó không thực thi ngay mà trả về một đối tượng iterator. Bạn cần gọi phương thức `next()` để thực hiện hàm và nhận giá trị từ `yield`.
- **Tạm Dừng và Tiếp Tục:** Sau khi `yield` được gọi, hàm generator sẽ tạm dừng tại đó cho đến khi `next()` được gọi lần tiếp theo. Điều này giúp tiết kiệm bộ nhớ và xử lý các tác vụ bất đồng bộ hiệu quả hơn.
- **Kết thúc Generator:** Khi không còn giá trị nào để trả về, hàm generator sẽ trả về một đối tượng với thuộc tính `done` là `true`.

## Tóm Tắt Một Dòng
Từ khóa `yield` trong TypeScript cho phép tạo ra các hàm generator, giúp tạm dừng và trả về giá trị, mang lại khả năng xử lý dữ liệu linh hoạt và hiệu quả.
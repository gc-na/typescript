<!--
Meta Description: # Sử Dụng "instanceof" Trong TypeScript: Kiểm Tra Kiểu Dữ Liệu ## Tóm Tắt Trong TypeScript, toán tử `instanceof` được sử dụng để xác định xem một đối ...
Meta Keywords: instanceof, một, đối, tượng, thể
-->

# Sử Dụng "instanceof" Trong TypeScript: Kiểm Tra Kiểu Dữ Liệu

## Tóm Tắt
Trong TypeScript, toán tử `instanceof` được sử dụng để xác định xem một đối tượng có phải là thể hiện (instance) của một lớp hoặc một hàm khởi tạo cụ thể hay không. Điều này rất hữu ích khi làm việc với các đối tượng và phân loại chúng theo kiểu dữ liệu.

## Tài Liệu

### Mục đích
Toán tử `instanceof` giúp kiểm tra mối quan hệ giữa một đối tượng và một lớp (class) hoặc hàm khởi tạo (constructor function). Khi sử dụng, nó trả về giá trị boolean: `true` nếu đối tượng là một thể hiện của lớp hoặc hàm khởi tạo được chỉ định, ngược lại trả về `false`.

### Cú pháp
```typescript
object instanceof constructor
```

- `object`: Đối tượng cần được kiểm tra.
- `constructor`: Lớp hoặc hàm khởi tạo mà bạn muốn kiểm tra xem đối tượng có phải là thể hiện hay không.

### Chi Tiết
- `instanceof` có thể được sử dụng với cả lớp (class) và hàm khởi tạo.
- Nó kiểm tra chuỗi prototype của đối tượng để xác định xem nó có thuộc về lớp hoặc hàm khởi tạo đó hay không.
- `instanceof` có thể hoạt động với các loại dữ liệu như: `Array`, `Date`, `RegExp`, cũng như các lớp do người dùng định nghĩa.

## Ví Dụ

### Ví Dụ Cơ Bản
```typescript
class Animal {}
class Dog extends Animal {}

const dog = new Dog();

console.log(dog instanceof Dog); // true
console.log(dog instanceof Animal); // true
console.log(dog instanceof Object); // true
console.log(dog instanceof Array); // false
```

### Ví Dụ Với Hàm Khởi Tạo
```typescript
function Person(name: string) {
    this.name = name;
}

const john = new Person("John");

console.log(john instanceof Person); // true
```

## Giải Thích
- **Cảnh báo**: Khi sử dụng `instanceof`, hãy nhớ rằng nó chỉ hoạt động với các đối tượng, không áp dụng cho các kiểu dữ liệu nguyên thủy như `string`, `number`, hay `boolean`.
- **Lưu ý về chuỗi prototype**: Nếu bạn thay đổi chuỗi prototype của một đối tượng, kết quả của `instanceof` có thể thay đổi.
- **Sử dụng với các thư viện bên ngoài**: Khi làm việc với các đối tượng từ thư viện bên ngoài, hãy chắc chắn rằng bạn đang làm việc với cùng một chuỗi prototype, nếu không, `instanceof` có thể không hoạt động như mong đợi.

## Tóm Tắt Một Dòng
Toán tử `instanceof` trong TypeScript cho phép kiểm tra xem một đối tượng có phải là thể hiện của một lớp hoặc hàm khởi tạo cụ thể hay không.
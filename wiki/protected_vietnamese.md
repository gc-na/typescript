<!--
Meta Description: # Từ Khóa "protected" trong TypeScript: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa `protected` trong TypeScript cho phép bạn định nghĩa các thuộc tính...
Meta Keywords: lớp, protected, trong, các, truy
-->

# Từ Khóa "protected" trong TypeScript: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa `protected` trong TypeScript cho phép bạn định nghĩa các thuộc tính và phương thức trong lớp mà chỉ có thể được truy cập từ lớp đó và các lớp kế thừa.

## Tài Liệu
Trong TypeScript, từ khóa `protected` được sử dụng để xác định phạm vi truy cập cho các thành viên (thuộc tính và phương thức) của lớp. Khi một thuộc tính hoặc phương thức được khai báo với `protected`, nó có thể được truy cập trong lớp mà nó được định nghĩa và trong tất cả các lớp con (lớp kế thừa) của lớp đó.

### Mục Đích
Mục đích chính của `protected` là để cho phép các lớp con truy cập vào các thuộc tính và phương thức mà không cần phải công khai chúng với tất cả các lớp khác, bảo vệ sự riêng tư hơn so với `public`.

### Cách Sử Dụng
Để sử dụng từ khóa `protected`, bạn chỉ cần thêm nó trước thuộc tính hoặc phương thức trong định nghĩa lớp. Dưới đây là cú pháp cơ bản:

```typescript
class BaseClass {
    protected property: string;

    protected method(): void {
        console.log("This is a protected method.");
    }
}

class DerivedClass extends BaseClass {
    public accessProtected() {
        this.property = "Hello";
        this.method();
    }
}
```

## Ví Dụ
Dưới đây là một ví dụ minh họa cách sử dụng `protected` trong TypeScript:

```typescript
class Animal {
    protected name: string;

    constructor(name: string) {
        this.name = name;
    }

    protected speak(): void {
        console.log(`${this.name} makes a noise.`);
    }
}

class Dog extends Animal {
    constructor(name: string) {
        super(name);
    }

    public bark(): void {
        this.speak(); // Truy cập vào phương thức protected
        console.log(`${this.name} barks.`);
    }
}

const dog = new Dog("Rex");
dog.bark(); // Rex makes a noise. Rex barks.
```

## Giải Thích
Khi bạn sử dụng `protected`, có một số điều cần lưu ý:

- **Không thể truy cập từ bên ngoài**: Các thuộc tính và phương thức được đánh dấu là `protected` không thể được truy cập từ bên ngoài lớp hoặc lớp con. Điều này giúp bảo vệ thông tin và giảm thiểu việc sử dụng sai.
  
- **Kế thừa**: Chỉ các lớp kế thừa mới có thể truy cập vào các thành viên `protected`. Nếu bạn cố gắng truy cập từ một lớp không phải là lớp con, TypeScript sẽ báo lỗi.

- **Khác với `private`**: Trong khi `private` chỉ cho phép truy cập trong lớp mà nó được định nghĩa, `protected` cho phép truy cập trong cả lớp và lớp con.

## Tóm Tắt Một Câu
Từ khóa `protected` trong TypeScript cho phép các thuộc tính và phương thức chỉ có thể được truy cập từ lớp cha và các lớp con của nó, giúp bảo vệ sự riêng tư của dữ liệu.
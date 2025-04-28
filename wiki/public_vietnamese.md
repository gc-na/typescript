<!--
Meta Description: # Từ Khóa "public" trong TypeScript: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa "public" trong TypeScript được sử dụng để chỉ định phạm vi truy cập củ...
Meta Keywords: public, trong, tính, dụng, thuộc
-->

# Từ Khóa "public" trong TypeScript: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa "public" trong TypeScript được sử dụng để chỉ định phạm vi truy cập của các thuộc tính và phương thức trong lớp, cho phép chúng được truy cập từ bất kỳ đâu bên ngoài lớp đó.

## Tài Liệu
### Mục Đích
Từ khóa "public" là một trong ba mức độ truy cập chính trong TypeScript, bao gồm "public", "private" và "protected". Mức độ "public" cho phép các thuộc tính và phương thức của lớp được truy cập từ bất kỳ đâu trong chương trình, bao gồm cả bên ngoài lớp.

### Cách Sử Dụng
Khi khai báo một thuộc tính hoặc phương thức trong một lớp, bạn có thể thêm từ khóa "public" trước tên của thuộc tính hoặc phương thức đó. Nếu không chỉ định mức độ truy cập, TypeScript sẽ mặc định là "public".

```typescript
class HinhTron {
    public banKinh: number;

    constructor(banKinh: number) {
        this.banKinh = banKinh;
    }

    public tinhDienTich(): number {
        return Math.PI * this.banKinh * this.banKinh;
    }
}
```

### Chi Tiết
- **Mặc định**: Nếu bạn không chỉ định phạm vi truy cập, thuộc tính và phương thức sẽ được coi là "public" mặc định.
- **Tính Kế Thừa**: Các thuộc tính và phương thức "public" có thể được kế thừa bởi các lớp con.
- **Tính Tương Thích**: Việc sử dụng "public" giúp mã dễ đọc và dễ hiểu hơn cho những lập trình viên khác.

## Ví Dụ
Dưới đây là một ví dụ đơn giản để minh họa cách sử dụng từ khóa "public":

```typescript
class Nguoi {
    public ten: string;

    constructor(ten: string) {
        this.ten = ten;
    }

    public gioiThieu(): void {
        console.log(`Xin chào, tôi là ${this.ten}.`);
    }
}

const nguoi1 = new Nguoi("Nguyen Van A");
nguoi1.gioiThieu(); // Kết quả: Xin chào, tôi là Nguyen Van A.
```

## Giải Thích
### Cạm Bẫy Thường Gặp
- **Quá sử dụng "public"**: Việc sử dụng quá nhiều thuộc tính và phương thức "public" có thể dẫn đến mã không an toàn và khó bảo trì. Nên chỉ định "public" khi thật sự cần thiết.
- **Nhầm lẫn với "private"**: Đảm bảo bạn hiểu rõ sự khác biệt giữa "public" và "private", tránh làm lộn xộn việc truy cập thuộc tính và phương thức.

### Lưu Ý
- Từ khóa "public" giúp tăng cường khả năng tương tác với các đối tượng, nhưng nên được sử dụng một cách hợp lý để bảo vệ dữ liệu bên trong lớp.
- Việc sử dụng "public" trong các lớp phức tạp có thể dẫn đến sự khó khăn trong việc quản lý và bảo trì mã nguồn.

## Tóm Tắt Một Dòng
Từ khóa "public" trong TypeScript cho phép truy cập không giới hạn đến các thuộc tính và phương thức của lớp từ bên ngoài.
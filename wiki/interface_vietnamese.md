<!--
Meta Description: # Giao diện (Interface) trong TypeScript: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm tắt Giao diện (interface) trong TypeScript là một cấu trúc cho phép định ...
Meta Keywords: giao, diện, tính, một, typescript
-->

# Giao diện (Interface) trong TypeScript: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm tắt
Giao diện (interface) trong TypeScript là một cấu trúc cho phép định nghĩa các thuộc tính và phương thức mà một đối tượng phải có, giúp tăng cường tính linh hoạt và tổ chức mã nguồn.

## Tài liệu
### Mục đích
Giao diện trong TypeScript giúp định nghĩa hình thức của các đối tượng, cho phép phát hiện lỗi khi biên dịch. Giao diện không chỉ là một bản thiết kế cho các đối tượng mà còn có thể được sử dụng để quản lý các kiểu dữ liệu phức tạp trong ứng dụng.

### Cách sử dụng
Giao diện được khai báo bằng từ khóa `interface`, tiếp theo là tên của giao diện và khối mã chứa các thuộc tính và phương thức. Các thuộc tính trong giao diện có thể có kiểu dữ liệu cụ thể và có thể được đánh dấu là tùy chọn.

#### Cú pháp cơ bản:
```typescript
interface TênGiaoDiện {
    thuộc tính1: kiểu1;
    thuộc tính2?: kiểu2; // thuộc tính tùy chọn
    phươngThức1(): kiểuTrảVề;
}
```

## Ví dụ
### Ví dụ 1: Định nghĩa một giao diện đơn giản
```typescript
interface Người {
    tên: string;
    tuổi: number;
    giớiTinh?: string; // thuộc tính tùy chọn
}

const nguoi1: Người = {
    tên: "Nguyễn Văn A",
    tuổi: 30,
    giớiTinh: "Nam"
};

const nguoi2: Người = {
    tên: "Trần Thị B",
    tuổi: 25
};
```

### Ví dụ 2: Sử dụng giao diện với phương thức
```typescript
interface HìnhChữNhật {
    chiềuDài: number;
    chiềuRộng: number;
    tínhDiệnTích(): number;
}

const hìnhChữNhật: HìnhChữNhật = {
    chiềuDài: 10,
    chiềuRộng: 5,
    tínhDiệnTích: function() {
        return this.chiềuDài * this.chiềuRộng;
    }
};

console.log(hìnhChữNhật.tínhDiệnTích()); // Kết quả: 50
```

## Giải thích
Giao diện là một công cụ mạnh mẽ trong TypeScript, nhưng có một số điều cần lưu ý:
- **Phương thức không có thân**: Giao diện chỉ định nghĩa kiểu nhưng không thực thi.
- **Tính kế thừa**: Giao diện có thể kế thừa từ các giao diện khác, cung cấp tính linh hoạt cao hơn.
- **Giao diện so với kiểu**: Giao diện có thể được sử dụng như một kiểu dữ liệu, nhưng có thể mở rộng hoặc kết hợp nhiều giao diện khác nhau.

## Tóm tắt một dòng
Giao diện trong TypeScript là một cấu trúc giúp định nghĩa các thuộc tính và phương thức của đối tượng, nâng cao tính tổ chức và an toàn cho mã nguồn.
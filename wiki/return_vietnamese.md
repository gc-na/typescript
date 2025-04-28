<!--
Meta Description: # Câu Lệnh "return" trong TypeScript: Hướng Dẫn Chi Tiết ## Tóm Tắt Câu lệnh "return" trong TypeScript được sử dụng để trả về giá trị từ một hàm, giúp...
Meta Keywords: hàm, return, trả, câu, trong
-->

# Câu Lệnh "return" trong TypeScript: Hướng Dẫn Chi Tiết

## Tóm Tắt
Câu lệnh "return" trong TypeScript được sử dụng để trả về giá trị từ một hàm, giúp kiểm soát luồng thực thi và kết quả của hàm.

## Tài Liệu
Câu lệnh "return" là một phần thiết yếu trong việc định nghĩa hàm trong TypeScript. Nó cho phép lập trình viên trả về giá trị từ hàm, và kết thúc quá trình thực thi của hàm đó. Trong TypeScript, việc xác định kiểu dữ liệu của giá trị trả về là rất quan trọng, giúp đảm bảo tính an toàn kiểu trong quá trình phát triển.

### Mục Đích
- Để trả về giá trị từ hàm.
- Để kết thúc việc thực thi hàm.

### Cách Sử Dụng
Câu lệnh "return" thường được sử dụng trong thân hàm, theo cú pháp sau:
```typescript
function tenHàm(): kiểuDữLiệu {
    // logic
    return giáTrị;
}
```
Trong đó:
- `tenHàm`: tên của hàm.
- `kiểuDữLiệu`: kiểu dữ liệu của giá trị mà hàm sẽ trả về.
- `giáTrị`: giá trị mà bạn muốn trả về.

## Ví Dụ
### Ví Dụ Cơ Bản
1. Hàm trả về một số:
```typescript
function tinhTong(a: number, b: number): number {
    return a + b;
}

const tong = tinhTong(5, 10); // tong sẽ là 15
```

2. Hàm trả về một chuỗi:
```typescript
function chaoMung(ten: string): string {
    return `Chào mừng, ${ten}!`;
}

const thongDiep = chaoMung("An"); // thongDiep sẽ là "Chào mừng, An!"
```

## Giải Thích
Mặc dù câu lệnh "return" rất đơn giản, nhưng có một số điều cần lưu ý:
- Nếu không sử dụng câu lệnh "return" trong hàm, hàm sẽ tự động trả về `undefined`.
- Đảm bảo rằng kiểu dữ liệu của giá trị trả về phù hợp với kiểu dữ liệu đã khai báo cho hàm, nếu không TypeScript sẽ báo lỗi.
- Câu lệnh "return" không chỉ trả về giá trị mà còn kết thúc thực thi của hàm. Đặt câu lệnh "return" ở những vị trí không chính xác có thể dẫn đến kết quả không mong muốn.

## Tóm Tắt Một Câu
Câu lệnh "return" trong TypeScript cho phép lập trình viên trả về giá trị từ hàm và kiểm soát luồng thực thi của chương trình.
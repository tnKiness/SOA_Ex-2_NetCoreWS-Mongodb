# SOA - Exercise 2

## Tổng quan Dự án

Dự án này là một API quản lý cửa hàng sách sử dụng ASP.NET Core và MongoDB. Dự án cung cấp các endpoint để thực hiện các thao tác CRUD (Create, Read, Update, Delete) đối với các sách trong cơ sở dữ liệu MongoDB. Các tính năng chính của API bao gồm:

- **Get**:
  - Lấy toàn bộ danh sách sách từ cơ sở dữ liệu.
  - Lấy thông tin chi tiết của một cuốn sách dựa trên ID.
- **Post**: Thêm một cuốn sách mới vào cơ sở dữ liệu.
- **Put**: Cập nhật thông tin của một cuốn sách theo ID.
- **Delete**: Xóa một cuốn sách theo ID.

## Các Thành Phần Chính

### 1. **Model** (`Book` và `BookStoreDatabaseSettings`)

- `Book`: Đại diện cho dữ liệu của một cuốn sách trong hệ thống gồm các thuộc tính:
  - `Id`: ID duy nhất của cuốn sách (kiểu ObjectId của MongoDB).
  - `BookName`: Tên cuốn sách.
  - `Price`: Giá của cuốn sách.
  - `Category`: Thể loại của cuốn sách.
  - `Author`: Tác giả của cuốn sách.
  
- `BookStoreDatabaseSettings`: Lưu trữ thông tin cấu hình để kết nối với MongoDB gôm các thuộc tính:
  - `ConnectionString`: Chuỗi kết nối đến MongoDB.
  - `DatabaseName`: Tên cơ sở dữ liệu.
  - `BooksCollectionName`: Tên collection lưu trữ sách.

### 2. **Controller** (`BooksController`)

- **Get**: 
  - Lấy tất cả các sách từ cơ sở dữ liệu.
  - Lấy một cuốn sách theo ID.
  
- **Post**:
  - Thêm một cuốn sách mới vào cơ sở dữ liệu.

- **Put**:
  - Cập nhật một cuốn sách đã tồn tại theo ID.

- **Delete**:
  - Xóa một cuốn sách theo ID.

### 3. **Service** (`BooksService`): Đóng vai trò là cầu nối giữa BooksController và cơ sở dữ liệu MongoDB với các phương thức chính là:

- `GetAsync`: Lấy danh sách tất cả các sách hoặc một cuốn sách theo ID.
- `CreateAsync`: Tạo một cuốn sách mới.
- `UpdateAsync`: Cập nhật thông tin cuốn sách.
- `RemoveAsync`: Xóa một cuốn sách.

## Kết quả 
- **API Hoạt Động**: Tất cả các endpoint API đều hoạt động như mong đợi, cho phép quản lý sách từ cơ sở dữ liệu MongoDB thông qua các phương thức GET, POST, PUT, DELETE.
  ![image](https://github.com/user-attachments/assets/184510fd-51e7-4c50-aa51-878220f51a4d)

- **Tương tác cơ sở dữ liệu**: Kết nối thành công với MongoDB để thực hiện các thao tác.
- **Swagger**:  Cho phép thử nghiệm các API trực tiếp trên trình duyệt, giúp việc kiểm tra và phát triển thuận tiện hơn với người dùng.

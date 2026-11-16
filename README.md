# Bài thực hành 05 – Bài tập 1: Document Exporter System

Project Java 17 + Maven + JUnit 5, theo hướng dẫn CT240T.

## Cấu trúc và pattern
- **Factory:** `DocumentReader`, `PDFReader`, `DocxReader`, `CsvReader`, `DocumentReaderFactory`.
- **Strategy:** `CompressionStrategy`, `ZipCompressionStrategy`, `RarCompressionStrategy`, `TarCompressionStrategy`.
- **Observer:** `ExportObserver`, `AuditLogObserver`, `ConsoleNotificationObserver`.
- **Service:** `DocumentExporterService` kết hợp ba pattern. Phương thức `exportDocument` không thay đổi khi thêm CSV và TAR.

## Cách chạy
1. IntelliJ IDEA → Open → chọn thư mục `lab5-design-patterns` → tải Maven dependencies, chọn JDK 17 hoặc 21.
2. Chạy `DocumentExporterService.main()` để xem xuất PDF + ZIP và CSV + TAR.
3. Chạy `DocumentExporterTest` hoặc Terminal: `mvn test`.
4. Chụp ảnh màn hình kết quả test (5 test xanh) để nộp theo yêu cầu.

**Lưu ý:** Đọc file và nén đều được mô phỏng bằng chuỗi như trong tài liệu, không xử lý file thật.

## Kết quả dự kiến khi chạy main
```text
Đang tiến hành xuất file PDF...
Nén dữ liệu theo chuẩn ZIP...
[Audit Log] Đã ghi nhật ký xuất file: BaoCaoTaiChinh2026.pdf (Kích thước: 50 bytes)
[Thông báo] Xuất báo cáo thành công file BaoCaoTaiChinh2026.pdf
Đang tiến hành xuất file CSV...
Nén dữ liệu theo chuẩn TAR...
[Audit Log] Đã ghi nhật ký xuất file: DanhSachSinhVien.csv (Kích thước: 48 bytes)
[Thông báo] Xuất báo cáo thành công file DanhSachSinhVien.csv
```

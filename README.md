# ABMWEBGIS

Mô phỏng tác tử trên WebGIS Việt Nam, chạy tĩnh trên GitHub Pages. © 2026 Long Ngo · MIT.

## Chức năng v0.1.0

- Vietflexmap 1.0.2 làm nền, không sửa package npm.
- 100 tác tử mặc định, nhóm màu, setup/play/pause/step, seed tái lập, GeoJSON / CSV.
- Chọn khung demo Vĩnh Long, TP.HCM, Hà Nội, Cần Thơ hoặc nạp polygon GeoJSON WGS84 để ràng buộc không gian thực.
- Tích hợp trình chạy chính thức NetLogo Web ở tab riêng, upload .nlogo / .nlogox bằng nút Upload a Model của NetLogo Web.

**Giới hạn quan trọng:** GIS dùng thuật toán random walk độc lập. File NetLogo *chưa* được biên dịch/thi hành như logic tác tử GIS. Trình NetLogo nhúng khác nguồn gốc nên không truy cập an toàn trạng thái turtles qua iframe. Để chạy chính xác mô hình NetLogo lên GIS cần cầu nối runtime có API tick/turtles, mapping patch x/y sang WGS84, và quy tắc chuyển đổi hệ tọa độ theo vùng; không thể khẳng định chỉ upload file bất kỳ là GIS tự chạy. NetLogo Web không hỗ trợ mọi extension và primitive của NetLogo desktop.

## Triển khai

Settings → Pages → Build and deployment → Deploy from a branch → main → / (root). Không cần Node hay backend. Trang: https://xulytiengviet.github.io/ABMWEBGIS/

## Nâng cấp dự kiến

1. Spatial NetLogo runtime bridge (cùng origin, tránh iframe cross-origin), đồng bộ agent identifiers, positions và ticks.
2. Dữ liệu polygon chính thức 34 tỉnh/thành và 3,321 xã/phường sau 2025; GeoJSON upload hiện là cách áp vùng chính xác.
3. Định tuyến theo đường giao thông, raster friction, GIS patches, biểu đồ và xuất snapshot.

Nền bản đồ có thể cần Internet và tile service. Tác tử không đại diện tình huống thực tế.

## Thư viện 30 bài toán (v0.2.0)

Trang chủ có dropdown **30 bài toán ABM**, chọn mỗi bài để tự thiết lập vùng minh họa, số tác tử, vận tốc và quy tắc hành vi. Năm họ hành vi mô phỏng: di chuyển đến điểm hấp dẫn, về điểm nhận/điểm tập kết, đi giữa các cực, tránh vùng rủi ro, tuần tra; thêm lan truyền trạng thái theo khoảng cách.

Các tình huống: giao thông giờ cao điểm; sơ tán ngập; giao hàng; dịch bệnh; cháy rừng; di cư lao động; vaccine; lan truyền thông tin; du lịch; xe buýt; robot nông nghiệp; sâu bệnh; đánh bắt; thu gom rác; trạm sạc; cứu thương; người đi bộ; trường học; chợ nông sản; vận chuyển lúa; xâm nhập mặn; rừng ngập mặn; sạt lở; drone; logistics; mua sắm; an ninh sự kiện; bến phà; phân bố dân số; cứu trợ thiên tai.

**Giới hạn khoa học:** Các hành vi là nguyên mẫu minh họa chứ không phải 30 mô hình đã kiểm định. Chưa có mạng đường, kịch bản vật lý thủy văn, ranh giới hành chính chính thức hoặc đồng bộ runtime NetLogo. Các kịch bản thay đổi chế độ/đích di chuyển nhưng không giải bài toán tối ưu có ràng buộc thực tế. Có thể nạp GeoJSON Polygon/MultiPolygon để áp giới hạn GIS, mặc định vùng là khung minh họa.

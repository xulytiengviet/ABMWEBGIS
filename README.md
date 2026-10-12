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

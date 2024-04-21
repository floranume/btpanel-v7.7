# btpanel-v7.7.0
btpanel-v7.7.0-backup sao lưu bảng điều khiển phiên bản v7.7.0 gốc chính thức

**Lệnh cài đặt Centos/Ubuntu/Debian môi trường chạy độc lập (py3.7)）**

```Bash
curl -sSO https://raw.githubusercontent.com/floranume/btpanel-v7.7/main/install/install_panel.sh && bash install_panel.sh
```

**Liên kết cài đặt thay thế cho máy chủ không có quyền truy cập vào GitHub. Các tập tin được lưu trữ công khai tại[d.moe.ms](http://d.moe.ms/?btpanel-v7.7.0)**

```
curl -sSO http://d.moe.ms/AAAAA/btpanel-v7.7.0/install/install_panel.sh && bash install_panel.sh
```

# Crack thủ công:

1. Chặn số điện thoại di động

```
sed -i "s|bind_user == 'True'|bind_user == 'XXXX'|" /www/server/panel/BTPanel/static/js/index.js
```

2. Xóa ràng buộc bắt buộc của các tập tin js trên điện thoại di động

```
rm -f /www/server/panel/data/bind.pl
```

3. Mở khóa thủ công tất cả các plugin trả phí của chùa và chúng sẽ không bao giờ hết hạn.

đường dẫn tập tin：`/www/server/panel/data/plugin.json`

Chuỗi tìm kiếm：`"endtime": -1`Thay thế tất cả bằng`"endtime": 999999999999`

4. Khóa tệp plugin.json để ngăn việc tự động sửa sang phiên bản miễn phí.

```
chattr +i /www/server/panel/data/plugin.json
```

============================

! ! Nếu bạn cần bỏ chặn số điện thoại di động của mình

```
sed -i "s|if (bind_user == 'REMOVED') {|if (bind_user == 'True') {|g" /www/server/panel/BTPanel/static/js/index.js
```

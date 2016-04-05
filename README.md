# Wireshark-DHCP
## Bước 1:
- Khởi động Wireshark
<img src="http://i.imgur.com/sNRzL3D.png">

- Chọn card mạng đang sử dụng. VD ở đây là Ethenet:
<img src="http://i.imgur.com/z6UZ04B.png">

## Bước 2:
- Xóa bỏ IP của máy bằng câu lệnh `ipconfig /release` (Trong hệ điều hành Windown)
<img src="http://i.imgur.com/hD90ENE.png">

## Bước 3:
- Xin cấp phát lại địa chỉ IP bằng câu lệnh `ipconfig /renew`
<img src="http://i.imgur.com/fwvylTF.png">

## Bước 4:
- Lọc gói tin DHCP trong Wireshark bằng cách gõ `bootp` trên thanh filter
<img src="http://i.imgur.com/myXiWmV.png">

## Bước 5:
- Phân tích gói tin DHCP
<img src="http://i.imgur.com/W30PBUr.png">

###Gói Discover
<img src="http://i.imgur.com/s6sbgb6.png">

- Thông tin gói Discover

<img src="http://i.imgur.com/dBCOeFA.png">

###Gói Offer
<img src="http://i.imgur.com/de12KIB.png">

- Thông tin gói Offer

<img src="http://i.imgur.com/9MC5elM.png">

###Gói Request
<img src="http://i.imgur.com/XAwAMcj.png">

- Thông tin gói Request

<img src="http://i.imgur.com/I4PlvRt.png">

###Gói ACK
<img src="http://i.imgur.com/UrztOBK.png">

- Thông tin gói ACK

<img src="http://i.imgur.com/1ECUWbI.png">

## Kết luận:
- Quy trình giao thức DHCP bao gồm:
<ul>
  <li>Client gửi gói Discover multicast để tìm server</li>
  <li>Offer từ server đến client gômg thông tin cấu hình ip</li>
  <li>Client gửi gói Request multicast xác nhận thông tin từ server</li>
  <li>ACK từ server đến client xác nhận cho client thuê địa chỉ IP</li>
  </ul>
- Tất cả việc trao đổi thông tin giữa một DHCP server và client sẽ sử dụng giao thức UDP tại hai cổng 67 và 68.
- Tất cả các gói tin client gửi đều là broadcast.
- Tất cả các gói tin server gửi đều là unicast.




# GeoCode(Phân giải lat, lng thành địa chỉ)
## 1. Input(Đầu vào)
```
https://api.map4d.vn/v2/api/geocode?key={key}&lat={lat}&lng={lng}
key và lat và lng là thuộc tính bắc buộc.
lat: là vĩ độ theo bản đồ gps, có giá trị từ -90 đến 90
lng: là kinh độ theo bản đồ gps, có giá trị từ -180 đến 180
```
## 2. Output(Đầu ra)
```json
{
  "code": "string",
  "message": "string",
  "result": {
    "id": "string",
    "location": {
      "lng": 0,
      "lat": 0
    },
    "address": "string",
    "name": "string",
    "objectId": "string",
    "description": "string",
    "types": [
      "string"
    ],
    "tags": [
      "string"
    ],
    "addressComponents": [
      {
        "code": "string",
        "type": "string",
        "name": "string"
      }
    ],
    "photos": [
      {
        "url": "string",
        "name": "string"
      }
    ],
    "startDate": "2019-09-30T02:21:25.183Z",
    "endDate": "2019-09-30T02:21:25.183Z",
    "createdDate": "2019-09-30T02:21:25.183Z",
    "updatedDate": "2019-09-30T02:21:25.183Z",
    "geometry": {
      "type": "string",
      "coordinates": [
        {}
      ]
    },
    "rank": {
      "value": 0
    },
    "icon": {
      "type": "string",
      "color": "string"
    },
    "phoneNumber": "string",
    "website": "string",
    "businessHours": [
      {
        "open": {
          "day": 0,
          "time": "string"
        },
        "close": {
          "day": 0,
          "time": "string"
        }
      }
    ]
  }
}
```
```html
code: là mã trả về, nếu 'ok' nghĩa là thành công, ngoài ra thì yêu cầu bị lỗi
message: là nội dung của mã lỗi(nếu có)
result: là place được tìm thấy gần nhất(nếu có địa điểm trong 50 mét sẽ trả về, không thì sẽ trả về đường trong phạm vi 50 mét, nếu không có nữa thì sẽ trả về địa giới hành chính chứa vị trí này), nếu lỗi thì result là null
id: là khóa của địa điểm
location: vị trí đặt địa điểm(lat là vĩ độ theo bản đồ GCS, lng là kinh độ theo bản đồ GCS)
address: địa chỉ của địa điểm. VD: 31 Lê Văn Duyệt, Phường Nai Hiên Đông, Quận Sơn Trà, Thành phố Đà Nẵng
name: tên của địa điểm
objectId: là địa điểm đó nó thuộc đối tượng nào(giống như địa điểm nó thuộc tòa nhà nào)
description: mô tả thêm về địa điểm
types: danh sách các kiểu của place, vd: cafe, restaurant..
tags: danh sách các nhãn của người dùng thêm vào để thuận tiện cho việc tìm kiếm
addressComponents: danh sách địa hành chính mà địa điểm đó thuộc vị trí đó
photos: danh sách thông tin hình ảnh về địa điểm
startDate: ngày tạo dựng địa điểm thật để tìm kiếm theo thời gian
endDate: ngày kết thúc địa điểm đó, để phục vụ cho việc tìm kiêm theo thời gian
createdDate: ngày tạo địa điểm trên bản đồ
updatedDate: ngày cập nhật địa điểm trên bản đồ
geometry: cấu trúc của địa điểm(có thể là điểm, đường, polygon...)
rank: là giới hạn trọng số ưu tiên của địa điểm
icon: là kiểu đại diện cho địa điểm
phoneNumber: số điện thoại liên hệ đến địa điểm
webiste: thông tin trang mạng của địa điểm
businessHours: danh sách thời gian mở cửa và đóng của
```
[Ví dụ](/examples/v1.0/geocode.html)
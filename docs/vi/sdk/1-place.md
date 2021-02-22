# 1. AutoSugest(Tự động đề xuất chuỗi tìm kiếm)
## 1.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/autosuggest?key={key}&text={text}&location={location}&isacronyms={isacronyms}
key và text là thuộc tính bắt buộc.
text: là chuối muốn gợi ý. VD: "Đà Nẵng"
location: địa điểm bạn đang tìm kiếm trên bản đồ. VD: 16.036505,108.218186
isacronym: type boolean- default false - Có tìm từ viết tắt hay không? (Nếu có thì perfomance sẽ kém hơn không tìm theo từ viết tắt)
```
## 1.2. Output(Đầu ra)
```json
{
  "code": "string",
  "message": "string",
  "result": [
    {
      "id": "string",
      "objectId": "string",
      "name": "string",
      "address": "string",
      "location": {
        "lng": 0,
        "lat": 0
      },
      "types": [
        "string"
      ],
      "tags": [
        "string"
      ],
      "geometry":{
        "type": "string"
      }
    }
  ]
}
```
```html
code: là mã trả về, nếu 'ok' nghĩa là thành công, ngoài ra thì yêu cầu bị lỗi
message: là nội dung của mã lỗi(nếu có)
result: là danh sách place được tìm thấy, nếu lỗi thì result là null
id: là khóa của địa điểm
objectId: là địa điểm đó nó thuộc đối tượng nào(giống như địa điểm nó thuộc tòa nhà nào)
name: tên của địa điểm
address: địa chỉ của địa điểm
location: vị trí đặt địa điểm(lat là vĩ độ theo bản đồ GCS, lng là kinh độ theo bản đồ GCS)
types: danh sách các kiểu của place, vd: cafe, restaurant..
tags: danh sách các nhãn của người dùng thêm vào để thuận tiện cho việc tìm kiếm
geometry.type: là kiểu đối tượng loại gì. VD: Point, MultiPoint, Polygon...
```
[Ví dụ](/examples/v1.0/autosugest.html)

# 2. Text Search(Tìm kiếm dạng văn bản)
## 2.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/place/text-search?key={key}&text={text}&types={type}&types={type}&datetime={datetime}&location={location}&accuracy={accuracy}
key và text là thuộc tính bắc buộc.
text: là nội dung muốn tìm bắt buộc phải có
types: là kiểu của địa điểm. vd: cafe, atm
datetime: là thời gian địa điểm vẫn còn tồn tại mú giờ là 0, đổi ra đơn vị là miliseconds
location: là tọa độ lat,lng tại địa điểm mà bạn muốn tìm, vd: 16.036505,108.218186
accuracy: là độ chính xác của địa điểm, nếu 0 là tìm chính xác, ngoài ra là tìm tương đối.
```
## 2.2. Output(Đầu ra)
```json
{
  "code": "string",
  "message": "string",
  "result": [
    {
      "id": "string",
      "objectId": "string",
      "name": "string",
      "address": "string",
      "location": {
        "lng": 0,
        "lat": 0
      },
      "types": [
        "string"
      ],
      "photos": [
        {
          "url": "string",
          "name": "string"
        }
      ],
      "tags": [
        "string"
      ],
      "geometry": {
        "type": "string"
      }
    }
  ]
}
```
```html
code: là mã trả về, nếu 'ok' nghĩa là thành công, ngoài ra thì yêu cầu bị lỗi
message: là nội dung của mã lỗi(nếu có)
result: là địa điểm tương ứng với id truyền vào
id: là khóa chính của địa điểm
objectId: là địa điểm đó nó thuộc đối tượng nào(giống như địa điểm nó thuộc tòa nhà nào)
name: tên của địa điểm
address: địa chỉ của địa điểm. VD: 31 Lê Văn Duyệt, Phường Nai Hiên Đông, Quận Sơn Trà, Thành phố Đà Nẵng
location: vị trí đặt địa điểm(lat là vĩ độ theo bản đồ GCS, lng là kinh độ theo bản đồ GCS)
types: danh sách các kiểu của place, vd: cafe, restaurant..
tags: danh sách các nhãn của người dùng thêm vào để thuận tiện cho việc tìm kiếm
geometry.type: là kiểu đối tượng loại gì. VD: Point, MultiPoint, Polygon...
```
[Ví dụ](/examples/v1.0/textsearch.html)

# 3. Nearby Search(Tìm kiếm lân cận)
## 3.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/place/nearby-search?key={key}&location={location}&radius={radius}&text={text}&types={types}&tags={tags}&datetime={datetime}&accuracy={accuracy}
key và location và radius là thuộc tính bắc buộc.
location: là tọa độ lat,lng tại địa điểm mà bạn muốn tìm, vd: 16.036505,108.218186
radius: là bán kinh tìm dữ liệu xung quanh đơn vị là mét
text: là nội dung muốn tìm
types: là kiểu của địa điểm. vd: cafe, atm
tags: là đánh dấu địa điểm riêng để tìm
datetime: là thời gian địa điểm vẫn còn tồn tại mú giờ là 0, đổi ra đơn vị là miliseconds
accuracy: là độ chính xác của địa điểm, nếu 0 là tìm chính xác, ngoài ra là tìm tương đối.
```
## 3.2. Output(Đầu ra)
```json
{
  "code": "string",
  "message": "string",
  "result": [
    {
      "id": "string",
      "name": "string",
      "description": "string",
      "address": "string",
      "location": {
        "lng": 0,
        "lat": 0
      },
      "types": [
        "string"
      ],
      "tags": [
        "string"
      ],
      "photos": [
        {
          "url": "string",
          "name": "string"
        }
      ],
      "geometry": {
        "type": "string"
      }
    }
  ]
}
```
```html
code: là mã trả về, nếu 'ok' nghĩa là thành công, ngoài ra thì yêu cầu bị lỗi
message: là nội dung của mã lỗi(nếu có)
result: là địa điểm tương ứng với id truyền vào
id: là khóa chính của địa điểm
objectId: là địa điểm đó nó thuộc đối tượng nào(giống như địa điểm nó thuộc tòa nhà nào)
name: tên của địa điểm
address: địa chỉ của địa điểm. VD: 31 Lê Văn Duyệt, Phường Nai Hiên Đông, Quận Sơn Trà, Thành phố Đà Nẵng
location: vị trí đặt địa điểm(lat là vĩ độ theo bản đồ GCS, lng là kinh độ theo bản đồ GCS)
types: danh sách các kiểu của place, vd: cafe, restaurant..
tags: danh sách các nhãn của người dùng thêm vào để thuận tiện cho việc tìm kiếm
photos: danh sách hình ảnh về địa điểm
geometry.type: là kiểu đối tượng loại gì. VD: Point, MultiPoint, Polygon...
```
[Ví dụ](/examples/v1.0/nearbysearch.html)

# 4. Viewbox Search(Tìm kiếm trong hộp hình chữ nhật)
## 4.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/place/viewbox-search?key={key}&viewbox={viewbox}&text={text}&types={type}&types={type}&tags={tags}&datetime={datetime}&accuracy={accuracy}
key và viewbox là thuộc tính bắc buộc.
viewbox: là khung muốn tìm kiếm, định dạng: minLat,minLng,maxLat,maxLng. VD: 16.056453967981348,108.19387435913086,16.093031550262133,108.25927734375
text: là nội dung muốn tìm
types: là kiểu của địa điểm. vd: cafe, atm
tags: là đánh dấu địa điểm riêng để tìm
datetime: là thời gian địa điểm vẫn còn tồn tại mú giờ là 0, đổi ra đơn vị là miliseconds
accuracy: là độ chính xác của địa điểm, nếu 0 là tìm chính xác, ngoài ra là tìm tương đối.
```
#### 6.2. Output(Đầu ra)
```json
{
  "code": "string",
  "message": "string",
  "result": [
    {
      "id": "string",
      "name": "string",
      "description": "string",
      "address": "string",
      "location": {
        "lng": 0,
        "lat": 0
      },
      "types": [
        "string"
      ],
      "tags": [
        "string"
      ],
      "photos": [
        {
          "url": "string",
          "name": "string"
        }
      ],
      "geometry": {
        "type": "string"
      }
    }
  ]
}
```
```html
code: là mã trả về, nếu 'ok' nghĩa là thành công, ngoài ra thì yêu cầu bị lỗi
message: là nội dung của mã lỗi(nếu có)
result: là địa điểm tương ứng với id truyền vào
id: là khóa chính của địa điểm
objectId: là địa điểm đó nó thuộc đối tượng nào(giống như địa điểm nó thuộc tòa nhà nào)
name: tên của địa điểm
address: địa chỉ của địa điểm. VD: 31 Lê Văn Duyệt, Phường Nai Hiên Đông, Quận Sơn Trà, Thành phố Đà Nẵng
location: vị trí đặt địa điểm(lat là vĩ độ theo bản đồ GCS, lng là kinh độ theo bản đồ GCS)
types: danh sách các kiểu của place, vd: cafe, restaurant..
tags: danh sách các nhãn của người dùng thêm vào để thuận tiện cho việc tìm kiếm
photos: danh sách hình ảnh về địa điểm
geometry.type: là kiểu đối tượng loại gì. VD: Point, MultiPoint, Polygon...
```
[Ví dụ](/examples/v1.0/viewboxsearch.html)

# 5. Get Place By Id(Chi tiết địa điểm)
## 5.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/place/{id}?key={key}
key và id là thuộc tính bắc buộc.
id: là khóa chính của địa điểm
```
## 5.2. Output(Đầu ra)
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
    "startDate": "2019-10-02T04:13:34.635Z",
    "endDate": "2019-10-02T04:13:34.635Z",
    "createdDate": "2019-10-02T04:13:34.635Z",
    "updatedDate": "2019-10-02T04:13:34.635Z",
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
result: là địa điểm tương ứng với id truyền vào
id: là khóa chính của địa điểm
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
geometry: cấu trúc của địa điểm(có thể là điểm, đường, polygon...). VD geometry={type:"Point", coordinates: [106.6816057,10.7701922]}
rank: là giới hạn trọng số ưu tiên của địa điểm
icon: là kiểu đại diện cho địa điểm
phoneNumber: số điện thoại liên hệ đến địa điểm
webiste: thông tin trang mạng của địa điểm
businessHours: danh sách thời gian mở cửa và đóng của
```
[Ví dụ](examples/v1.0/placedetail.html)

# 6. Get Place Type By Id(Lấy chi tiết của kiểu địa điểm)
## 6.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/place/type/{id}?key={key}
key và id là thuộc tính bắc buộc.
id: là khóa chính của type. vd: cafe, atm
```
## 6.2 Output(Đầu ra)
```json
{
  "code": "string",
  "message": "string",
  "result": {
    "id": "string",
    "name": "string",
    "iconName": "string",
    "iconUrl": "string",
    "color": "string",
    "description": "string"
  }
}
```
```html
code: là mã trả về, nếu 'ok' nghĩa là thành công, ngoài ra thì yêu cầu bị lỗi
message: là nội dung của mã lỗi(nếu có)
result: là địa điểm tương ứng với id truyền vào
id: là khóa chính của type
name: là tên của type
iconName: là tên của icon
iconUrl: là url truy cập trực tiêp tới icon
color: màu của icon
description: mô tả về icon
```
[Ví dụ](/examples/v1.0/typeid.html)

# 7. Get Icon(Icon đại diện cho kiểu của địa điểm)
## 7.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/place/icon?key={key}&option={option}&type={type}&size={size}
key là thuộc tính bắc buộc.
option: là tùy chọn 0 hoặc 1 hoặc 2.
  option = 0 --> icon giọt nước để vẽ địa điểm trên sdk
  option = 1 --> icon giọt nước để client add vào hiển thị khi có kết quả search 
  option = 2 --> icon hình tròn để sử dụng trong các trường hợp khác.
type: là kiểu dữ liệu của địa điểm. vd: cafe, atm...
size: là kích thướt của icon, là 1x hoặc 2x hoặc 3x
```
## 7.2. Output(Đầu ra)
```
stream
```
```html
stream: dữ liệu trả về dạng stream, nếu không có thì sẽ hiển thị icon mặt định
```
[Ví dụ](/examples/v1.0/icon.html)

# 8. GeoCode(Phân giải lat, lng thành địa chỉ)
## 8.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/geocode?key={key}&lat={lat}&lng={lng}
key và lat và lng là thuộc tính bắc buộc.
lat: là vĩ độ theo bản đồ gps, có giá trị từ -90 đến 90
lng: là kinh độ theo bản đồ gps, có giá trị từ -180 đến 180
```
## 8.2. Output(Đầu ra)
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
# 9. GeoCode And Reverse Geocoding(Phân giải địa chỉ thành lat lng hoặc ngược lại)
**GeoCode**: Phân giải địa chỉ(address) ra danh sách các địa điểm khớp với địa chỉ này nhất(thường thì 1 phần tử gần đúng nhất), nếu địa chỉ mơ hồ thì có thể tra nhiều kết quả khớp nhất.

**Reverse Geocoding**: Phân giải location truyền vào thành địa điểm tại đó hoặc gần sát đó. Nếu có địa điểm trong 50 mét sẽ trả về, không thì sẽ trả về đường trong phạm vi 50 mét, nếu không có nữa thì sẽ trả về địa giới hành chính chứa vị trí này), nếu lỗi thì result là null
## 8.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/v2/geocode?key={key}&location={location}&
location: địa điểm bạn đang tìm kiếm trên bản đồ. VD: 16.036505,108.218186
address: địa chỉ cần phân giải ra lat lng. Ví dụ: 31 Lê Văn Duyệt, Phường Nại Hiên Đông, Quận Sơn Trà, Thành Phố Đà Nẵng
viewbox: (optional) Viewbox có thể chứa kết quả trả về. ví dụ: Ex: 16.056453967981348,108.19387435913086,16.093031550262133,108.25927734375
```
**Bắt buộc phải có *location* hoặc *address*, nếu có cả 2 thì ưu tiên address.**
## 8.2. Output(Đầu ra)
```json
{
  "code": "string",
  "message": "string",
  "result": [
     {
      "id": "string",
      "objectId": "string",
      "name": "string",
      "address": "string",
      "location": {
        "lng": 0,
        "lat": 0
      },
      "types": [
        "string"
      ],
      "tags": [
        "string"
      ],
      "geometry":{
        "type": "string"
      }
    }
    ]
}
```
```html
code: là mã trả về, nếu 'ok' nghĩa là thành công, ngoài ra thì yêu cầu bị lỗi
message: là nội dung của mã lỗi(nếu có)
result: là danh place được tìm thấy gần nhất(đối với **Reverse Geocoding** nếu có địa điểm trong 50 mét sẽ trả về, không thì sẽ trả về đường trong phạm vi 50 mét, nếu không có nữa thì sẽ trả về địa giới hành chính chứa vị trí này), nếu lỗi thì result là null
id: là khóa của địa điểm
location: vị trí đặt địa điểm(lat là vĩ độ theo bản đồ GCS, lng là kinh độ theo bản đồ GCS)
address: địa chỉ của địa điểm. VD: 31 Lê Văn Duyệt, Phường Nai Hiên Đông, Quận Sơn Trà, Thành phố Đà Nẵng
name: tên của địa điểm
objectId: là địa điểm đó nó thuộc đối tượng nào(giống như địa điểm nó thuộc tòa nhà nào)
types: danh sách các kiểu của place, vd: cafe, restaurant..
tags: danh sách các nhãn của người dùng thêm vào để thuận tiện cho việc tìm kiếm
geometry: cấu trúc của địa điểm(có thể là điểm, đường, polygon...)
```

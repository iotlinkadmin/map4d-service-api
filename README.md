# Tìm kiếm
## Tìm kiếm dữ liệu
https://api-dev.map4d.vn/v2/api/place/text-search?parameters
### Thông số bắc buộc:
* key - Đăng ký tại iotlink.com.vn!
* text - Chuỗi muốn tìm kiếm!

### Thông số tùy chọn:
* datetime - Thời gian mà địa điểm này đăng ký(nghĩa là thời gia bắt đầu và kết thúc chứa thời gian này), đơn vị là miliseconds

### Kết quả trả về:
Trả về dạng json
```sh
{
  "code": "string",
  "message": "string",
  "result": [
    {
      "id": "string",
      "name": "string",
      "address": "string",
      "location": {
        "lng": 0,
        "lat": 0
      },
      "types": [
        "string"
      ],
      "source": "string"
    }
  ]
}
```
Nếu thành công thì code là "ok"
## Tìm kiếm viewbox
https://api-dev.map4d.vn/v2/api/place/viewbox-search?parameters
### Thông số bắc buộc:
* key - Đăng ký tại iotlink.com.vn!
* viewbox - Phạm vi hình chữ nhật mà bạn muốn tìm kiếm dữ liệu, toạn độ là nam, tây, bắc, đông. Thí dụ: 16.056453967981348,108.19387435913086,16.093031550262133,108.25927734375!

### Thông số tùy chọn:
* datetime - Thời gian mà địa điểm này đăng ký(nghĩa là thời gia bắt đầu và kết thúc chứa thời gian này), đơn vị là miliseconds
* type - Kiểu loại place mà bạn muốn tìm. Thí dụ: atm, cafe

### Kết quả trả về:
Trả về dạng json
```sh
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
      "source": "string",
      "imageUrl": "string"
    }
  ]
}
```
Nếu thành công thì code là "ok"

## Tìm kiếm bán kính
https://api-dev.map4d.vn/v2/api/place/nearby-search?parameters
### Thông số bắc buộc:
* key - Đăng ký tại iotlink.com.vn!
* location - Trung tâm vị trí muốn tìm: lat,lng. Thí dụ: 16.036461,108.218159!
* radius - Bán kinh trong phạm vi muốn tìm kiếm, đơn vị là mét. Thí dụ: 50000!
* text hoặc type - Yêu cầu phải có ít nhất một trong 2 loại này.

### Thông số tùy chọn:
* datetime - Thời gian mà địa điểm này đăng ký(nghĩa là thời gia bắt đầu và kết thúc chứa thời gian này), đơn vị là miliseconds
* type - Kiểu loại place mà bạn muốn tìm. Thí dụ: atm, cafe
* text - Loại đối tượng muốn tìm. Thí dụ: Azura

### Kết quả trả về:
Trả về dạng json
```sh
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
      "source": "string",
      "imageUrl": "string"
    }
  ]
}
```
Nếu thành công thì code là "ok"

# Phân giải lat lng ra địa chỉ
https://api-dev.map4d.vn/v2/api/geocode?parameters
### Thông số bắc buộc:
* key - Đăng ký tại iotlink.com.vn!
* lat - Vị trí vĩ độ muốn phân giải: Có giá trị từ -90 -> 90
* lng - Vị trí kinh độ muốn phân giải: Có giá trị từ 0 -> 360

### Kết quả trả về:
Trả về dạng json
```sh
{
  "code": "string",
  "message": "string",
  "result": {
    "name": "string",
    "address": "string",
    "countryName": "string",
    "countryCode": "string",
    "province": "string"
  }
}
```
Nếu thành công thì code là "ok"

# Chỉ đường đi giữa các điểm
https://api-dev.map4d.vn/v2/api/route?parameters
## Thông số bắc buộc:
* key - Đăng ký tại iotlink.com.vn!
* mode - Loại phương tiện muốn đi một trong các loại sau: car(xe hơi) hoặc bike(xe đạp) hoặc foot(đi bộ)!

## Thông số tùy chọn:
* origin - Vị trí điểm đầu(lat,lng). Thí dụ: 16.024634,108.209217
* points - Vị trí danh sách các điểm muốn đi qua(lat,lng;lat,lng...). Thí dụ: 16.039173,108.210912;16.044597,108.217263
* destination - Vị trí điểm cuối(lat,lng). Thí dụ: 16.020179,108.211212

## Kết quả trả về:
Trả về dạng json
```sh
{
  "code": "string",
  "message": "string",
  "result": {
    "status": "string",
    "routes": [
      {
        "legs": [
          {
            "distance": {
              "text": "string",
              "value": 0
            },
            "duration": {
              "text": "string",
              "value": 0
            },
            "endAddress": "string",
            "startAddress": "string",
            "endLocation": {
              "lng": 0,
              "lat": 0
            },
            "startLocation": {
              "lng": 0,
              "lat": 0
            },
            "steps": [
              {
                "distance": {
                  "text": "string",
                  "value": 0
                },
                "duration": {
                  "text": "string",
                  "value": 0
                },
                "endLocation": {
                  "lng": 0,
                  "lat": 0
                },
                "startLocation": {
                  "lng": 0,
                  "lat": 0
                },
                "htmlInstructions": "string",
                "maneuver": "string",
                "polyline": "string",
                "travelMode": "string"
              }
            ]
          }
        ],
        "overviewPolyline": "string",
        "summary": "string",
        "distance": {
          "text": "string",
          "value": 0
        },
        "duration": {
          "text": "string",
          "value": 0
        },
        "snappedWaypoints": [
          {
            "lng": 0,
            "lat": 0
          }
        ]
      }
    ],
    "geocoded_waypoints": [
      {
        "geocoder_status": "string",
        "place_id": "string",
        "types": [
          "string"
        ]
      }
    ]
  }
}
```
Nếu thành công thì code là "ok"
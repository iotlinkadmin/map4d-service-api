# 1. Init map(Load nội dung file js)
## 1.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/map/init?key={key}
key là thuộc tính bắc buộc.
```
## 1.2. Output(Đầu ra)
```text
Nội dung tập tin javascript
```
[Chức năng nội dung tập tin javascript](https://github.com/map4d/map4d-web-sdk)

# 2. Load map theo version
## 2.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/map/js?key={key}&version={version}&callback={callback}
key là thuộc tính bắc buộc.
version là phiên bản nội dung javascript
callback 
```
## 2.2. Output(Đầu ra)
```text
Nội dung tập tin javascript
```
[Chức năng nội dung tập tin javascript](https://github.com/map4d/map4d-web-sdk)


# 3. Tile(Lấy thông tin của tile)
## 3.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/tile/{z}/{x}/{y}?key={key}&tileUrl={tileUrl}&mode={mode}
key và mode là thuộc tính bắc buộc.
z: là độ zoom của map
x: là tọa độ x
y: là tọa độ y
tileUrl: là url của tile
mode: là loại 2d hoặc 3d
```
## 3.2. Output(Đầu ra)
```json
{
  "code": "string",
  "message": "string",
  "result": {
    "rasterTile": "string",
    "objects": [
      {
        "id": "string",
        "name": "string",
        "places": [
          "string"
        ],
        "location": {
          "lng": 0,
          "lat": 0
        },
        "scale": 0,
        "bearing": 0,
        "elevation": 0,
        "camera": {
          "zoom": 0,
          "bearing": 0,
          "tilt": 0,
          "target": {
            "lng": 0,
            "lat": 0
          }
        },
        "types": [
          "string"
        ],
        "minZoom": 0,
        "maxZoom": 0,
        "startDate": "2020-07-06T07:20:52.010Z",
        "endDate": "2020-07-06T07:20:52.010Z",
        "model": {
          "id": "string",
          "type": "string",
          "objName": "string",
          "objUrl": "string",
          "textureName": "string",
          "textureUrl": "string",
          "color": "string",
          "height": 0,
          "coordinates": [
            {
              "lng": 0,
              "lat": 0
            }
          ]
        }
      }
    ],
    "places": [
      {
        "id": "string",
        "name": "string",
        "types": [
          "string"
        ],
        "location": {
          "lng": 0,
          "lat": 0
        },
        "rank": {
          "value": 0
        },
        "icon": {
          "type": "string",
          "url": "string",
          "color": "string"
        }
      }
    ]
  }
}
```
```html
code: là mã trả về, nếu 'ok' nghĩa là thành công, ngoài ra thì yêu cầu bị lỗi
message: là nội dung của mã lỗi(nếu có)
result: là danh sách các xe theo thứ tự từ gần đến xa
rasterTile: là nội dung tile dạng base64
objects: là danh sách các object trong tile đó
places: là danh sách place trong tile đó
```
[Ví dụ](/examples/v1.0/tile.html)

# 4. Tile(Lấy thông tin đối tượng và địa điểm của tile)
## 4.1. Input(Đầu vào)
```
https://api.map4d.vn/sdk/tile/v2/{z}/{x}/{y}?key={key}&mode={mode}
key và mode là thuộc tính bắc buộc.
z: là độ zoom của map
x: là tọa độ x
y: là tọa độ y
mode: là loại 2d hoặc 3d
```
## 3.2. Output(Đầu ra)
```json
{
  "code": "string",
  "message": "string",
  "result": {
    "objects": [
      {
        "id": "string",
        "name": "string",
        "places": [
          "string"
        ],
        "location": {
          "lng": 0,
          "lat": 0
        },
        "scale": 0,
        "bearing": 0,
        "elevation": 0,
        "camera": {
          "zoom": 0,
          "bearing": 0,
          "tilt": 0,
          "target": {
            "lng": 0,
            "lat": 0
          }
        },
        "types": [
          "string"
        ],
        "minZoom": 0,
        "maxZoom": 0,
        "startDate": "2020-07-06T07:20:52.010Z",
        "endDate": "2020-07-06T07:20:52.010Z",
        "model": {
          "id": "string",
          "type": "string",
          "objName": "string",
          "objUrl": "string",
          "textureName": "string",
          "textureUrl": "string",
          "color": "string",
          "height": 0,
          "coordinates": [
            {
              "lng": 0,
              "lat": 0
            }
          ]
        }
      }
    ],
    "places": [
      {
        "id": "string",
        "name": "string",
        "types": [
          "string"
        ],
        "location": {
          "lng": 0,
          "lat": 0
        },
        "rank": {
          "value": 0
        },
        "icon": {
          "type": "string",
          "url": "string",
          "color": "string"
        }
      }
    ]
  }
}
```
```html
code: là mã trả về, nếu 'ok' nghĩa là thành công, ngoài ra thì yêu cầu bị lỗi
message: là nội dung của mã lỗi(nếu có)
result: là danh sách các xe theo thứ tự từ gần đến xa
objects: là danh sách các object trong tile đó
places: là danh sách place trong tile đó
```
[Ví dụ](/examples/v1.0/tile.html)
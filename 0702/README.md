# Object Detection with Azure Computer Vision & PIL

웹 URL로 지정한 이미지를 Azure Computer Vision API에 보내 객체 탐지 결과를 받아오고, PIL을 통해 이미지 위에 바운딩 박스와 라벨을 그려 시각화합니다.

## 코드 구조
- random_color()
  - 랜덤 RGB 색상 튜플 반환
- get_font()
  - 플랫폼에 맞는 한글 지원 폰트 로드 / 실패 시, 기본 폰트 사용
- request_objects(url)
  - Azure Computer Vision의 Objects API에 이미지 URL을 POST 요청하고, JSON 응답을 반환
- draw_image(url, data)
  - 원본 이미지를 가져와 PIL Image 객체로 로드
  - data['objectsResult']['values'] 리스트를 순회하며 바운딩 박스와 라벨 그리기
  - 최종 Image 객체 반환
# OCR on prescription

### 개요:
- 처방전 데이터에서 OCR 수행
- 데이터를 수정하여 성능 향상을 시도하였다.

### 주요 사용기법:
- 학습된 모델이 회전된 글자, 세로쓰기, 도장에서 글자를 잘 포착하지 못함
- 기존 모델이 잘 포착하지 못한 데이터를 추가해 fine-tuning하면 성능 향상이 가능할 것으로 판단
- 잘 포착하지 못하는 영역을 crop해서 원본데이터에 붙여 넣는 방식으로 oversampling 하여 <br/>
  labelme를 통해 글자 영역에 대해 bounding box를 그리고 값을 입력하는 annotation 작업 수행
![labelme](https://github.com/KANG-dg/object_detection_for_recycle/assets/121837927/e361f134-dbe4-4c6f-b37d-ff61926bc70e)

### 결과 & 회고
- oversampling된 데이터를 추가하여 학습시키는 것은 성능 향상에 유의미한 효과 있었음
- labelme를 통해 annotation을 수행함으로서 필요시 추가적으로 데이터를 수집하고 <br/>
  직접 라벨링하는 방법으로 데이터 생산가능

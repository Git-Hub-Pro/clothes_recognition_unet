# clothes_recognition_unet
# 구현 내용:  U-NET  구조를 활용한 사진에서 의상의 상의 부분 마스크 하기.

# 데이터 수집 : 구글 검색 후, 모델 사진 중에서 상의가 특정 원색으로 이루어진 사진 모으기.이때, 폴더를 색깔별로 모아준다.사진은 최대한 많이 준비.
- 실제로는 구글에서 검색하여 사진을 모은 결과 60장(추후100장) 정도 모았다. 흑백과 흰색은 구별하기가 어려워서, 
  이미지는 구별하기 쉽게 빨간색, 노란색, 오렌지색, 초록색, 파란색으로 구분지었다.(특히 모델의 옷이 단색인 의상 위주로 찾았다.)

# 데이터 조작 : OpenCV를 활용하여 이미지 파일을 HSV로 바꿔준 후, 데이터 별로 마스크 이미지를 만들어준다.      
- train data에서 원본 이미지와 마스크 부분을 만들었다.
- HSV 데이터를 활용하여 이미지를 편집한 후, 추가적으로 그림판을 활용하여 마스크 부분을 체크하였다.
 (여기서는 경계선으로 트레이닝 시키고 싶어 경계선 검출 작업도 추가적으로 하였습니다.)

# 데이터 모델링: UNET 구조를 사용한다. 
- 이때, input 은 (128,128,3) 8bit 입력으로 받은 다음, 255으로 나누어 소수점으로 만들었습니다. 출력값은 bool 형입니다.

# 구현 결과
- 데이터 수가 적고, 경계선으로 트레이닝을 하였지만, 이미지에서 상의 부분을 잘 검출하였습니다. (정확도는 데이터양이 적어 의미가 없어 하지 않았습니다.) 
  원하는 출력은 경계선이었지만, scatter 느낌으로 원하는 영역을 표시하였습니다.

# 데이터
https://drive.google.com/drive/folders/1esBgGGzf_C_hDmwxhjfx4SiHl3S_fPGq?usp=sharing

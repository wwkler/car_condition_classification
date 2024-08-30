# car_condition_classification
<h3>차량의 상태(정상, 스크래치, 찌그러짐, 이격, 파손)를 판별하는 모델 서비스 </h3>

데이터셋
> KT 부트캠프에서 제공한 차량 정상 이미지 300장, 차량 파손 이미지 300장<br>
> https://drive.google.com/file/d/1ZZ2k5Ptd4qn0uBV82Dj5jCNMWiUd2ej-/view<br><br>
> AI허브 차량 파손 데이터 샘플 데이터 1201장 (차량 이미지 + 차량 이미지에 대한 정보를 제공하는 데이터)<br>
> https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&dataSetSn=581

<br>

라벨링 분류 방법 
> KT에서 제공 : 파일 이름에서 추론하여 라벨링 시도
> 
    -  파일 제목에 scratch, blemish가 나온다? -> scratch(스크래치) 폴더에 저장
    -  파일 제목에 dent가 나온다? -> crushed(찌그러짐) 폴더에 저장 
    -  파일 제목에 dagmage가 나온다? -> breakage(파손) 폴더에 저장 
    -  나머지 -> scratch(스크래치) 폴더에 저장 

    - 이격이 없는 이유는 이격이라 보여지는 차량 사진 데이터가 없었기 떄문 

<br>
         
> AI 허브에서 제공 : 차량 이미지에 대한 정보 제공 json 데이터를 이용해 어떤 차량 파손 유형인지 확인
>
    -  라벨링 데이터를 의미하는 json 파일에 Breakage 단어가 등장하면? -> breakage(파손) 폴더에 저장
    -  라벨링 데이터를 의미하는 json 파일에 Scratched 단어가 등장하면? -> scratched(스크래치) 폴더에 저장
    -  라벨링 데이터를 의미하는 json 파일에 Crushed 단어가 등장하면? -> crushed(찌그러짐) 폴더에 저장
    -  라벨링 데이터를 의미하는 json 파일에 Separated 단어가 등장하면? -> separated(이격) 폴더에 저장


문제점
> AI 허브에서 제공하는 차량 정보 데이터에서 여러 개의 파손 유형이 발견되어서 어떤 파손 유형으로 결정할지에 대한 부분에 대한 전략을 찾지 못함
> 그로 인해 차량에 대한 라벨링 부여하는 것이 어려웠고 다중 분류 모델 자체는 만들었지만 더욱 효과적인 다중 분류 모델이 만들어지지 못했다.

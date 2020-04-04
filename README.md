# Making Predictions with Data and Python
python 분석을 통한 신용 연체자 예측

# 0. 개요

<img width="828" alt="스크린샷 2020-04-04 오전 11 39 47" src="https://user-images.githubusercontent.com/62536330/78417043-1984d200-7669-11ea-82dd-a4729cc5a0c4.png">

 현재 소득이 줄어든 직장인과 자영업자가 카드사나 캐피털사에서 빌린 돈을 갚지 못하는 비율이 높아지고 있다. 이들에 비해 신용등급이 우량한 사람들이 이용하는 은행은 아직 연체율 증가 모습이 뚜렷하지 않지만, 금융권 전반으로 부실 채권에 대한 공포가 커지는 분위기다. 업계에서는 연체율 관리를 위해 카드사와 캐피털사가 곳간을 닫기 시작하면 한계차주가 저축은행 신협 새마을금고 대부업 등으로 내몰려 더 높은 이자를 내야 하는 것을 우려하고 있다. 이와 함께 이들의 부실이 시스템적인 리스크로 전이돼 은행을 비롯한 금융권 전반으로 확산될 가능성도 배제하지 못하는 상황이다.

<h3>이에 따른 미리 신용 연체자들의 채무상환 가능성을 예측하여 관리할 수 있는 데이터 분석을 다양한 알고리즘을 사용하여 비교해 봤습니다. </h3>

# 1. 데이터 정제  EDA

데이터 수집은 github에서 가져왔으며 대만달러 기준 가상의 데이터를 바탕으로 진행.
<ul>
      <li>limit_bal : 개인과 가족들의 신용을 나타내는 변수</li>
      <li>sex : 성별 (1 = 남자, 2 = 여자)</li>
      <li>education : 교육 ( 1 = graduate school, 2 = university, 3 = highschool, 4= ohters</li>
      <li>age : 나이</li>
      <li>pay_01~06 : 과거의 지불한 금액 (달 기준)</li>
      <li>bill_amt 01~06 : 청구 금액 (달 기준)</li>
      <li>pay_amt_ 01~06 : 과거의 총 지불 금액 (달 기준)</li>
      <li>default payment next month : + 연체 , - 지불 O </li> 
</ul>

<img width="1005" alt="스크린샷 2020-04-04 오전 11 36 20" src="https://user-images.githubusercontent.com/62536330/78417042-18ec3b80-7669-11ea-90e1-11bc90377ee5.png">

# 2. 모델링


# 3. 예측

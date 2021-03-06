# Making Predictions with Data and Python
3만개의 데이터를 통한 python 신용 연체자 분석 

# 0. 개요

<img width="828" alt="스크린샷 2020-04-04 오전 11 39 47" src="https://user-images.githubusercontent.com/62536330/78417043-1984d200-7669-11ea-82dd-a4729cc5a0c4.png">

 현재 소득이 줄어든 직장인과 자영업자가 카드사나 캐피털사에서 빌린 돈을 갚지 못하는 비율이 높아지고 있다. 이들에 비해 신용등급이 우량한 사람들이 이용하는 은행은 아직 연체율 증가 모습이 뚜렷하지 않지만, 금융권 전반으로 부실 채권에 대한 공포가 커지는 분위기다. 업계에서는 연체율 관리를 위해 카드사와 캐피털사가 곳간을 닫기 시작하면 한계차주가 저축은행 신협 새마을금고 대부업 등으로 내몰려 더 높은 이자를 내야 하는 것을 우려하고 있다. 이와 함께 이들의 부실이 시스템적인 리스크로 전이돼 은행을 비롯한 금융권 전반으로 확산될 가능성도 배제하지 못하는 상황이다.

<h3>이에 따른 미리 신용 연체자들의 채무상환 가능성을 예측하여 관리할 수 있는 데이터 분석을 다양한 알고리즘을 사용하여 비교해 봤습니다. </h3>

# 1. 데이터 정제  EDA

데이터 수집은 github에서 가져왔으며 대만달러 기준 가상의 데이터를 바탕으로 진행.
<ul>
      <li>limit_bal : 개인과 가족들의 신용을 나타내는 변수</li>
      <li>sex : 성별 (1 = 남자, 2 = 여자)</li>
      <li>education : 교육 ( 1 = graduate school, 2 = university, 3 = highschool, 4 = ohters</li>
      <li>age : 나이</li>
      <li>pay_01~06 : 과거의 지불한 금액 (달 기준)</li>
      <li>bill_amt 01~06 : 청구 금액 (달 기준)</li>
      <li>pay_amt_ 01~06 : 과거의 총 지불 금액 (달 기준)</li>
      <li>default payment next month : + 연체 , - 지불 O </li> 
</ul>

<img width="1005" alt="스크린샷 2020-04-04 오전 11 36 20" src="https://user-images.githubusercontent.com/62536330/78417042-18ec3b80-7669-11ea-90e1-11bc90377ee5.png">

 ※ 위의 데이터를 바탕으로 더미변수로 원핫인코딩함
(범주형 변수를 연속형 변수로 바꿔서 로지스틱회귀를 할 수 있게 함. education을 삭제하고 3가지 col을 int형으로)

 ※ 교육에 4(others)가 없기에 삭제, 새로운 더미변수로 기존의 edu삭제 ,default.payment.next.month -> default로 1,0을 기준으로 변경
따라서 다음과 같이 변경 , 성별은 남자인지 아닌지 1,0으로만 다음과 같이 모든 범주형 변수들은 연속형 변수로 바꿈.

<img width="1003" alt="스크린샷 2020-04-04 오전 11 35 36" src="https://user-images.githubusercontent.com/62536330/78417039-15f14b00-7669-11ea-95b3-e6dc0cd41939.png">

# 2. 모델링

정밀도와 재현율 정확도를 기준으로 Logistic 회귀  , NaiveBayes, ClassTree를 비교.

<img width="953" alt="스크린샷 2020-04-04 오후 12 00 53" src="https://user-images.githubusercontent.com/62536330/78417339-f6a7ed00-766b-11ea-9a9a-e6e97338a941.png">

Logisitic 회귀가 가장 우월한 퍼포먼스를 보였기에 채택.

# 3. 예측

이를 바탕으로 대학을 나온 50대 기혼 남성을 새로운 데이터에 삽입하여 예측해봄.

<img width="1109" alt="스크린샷 2020-04-04 오후 12 04 07" src="https://user-images.githubusercontent.com/62536330/78417397-82ba1480-766c-11ea-8978-92087e64a312.png">

# 4. 느낀점

이와 같이 범주형데이터를 연속형데이터로 바꾸어 데이터를 정제하고 이를 바탕으로 고객의 데이터를 활용하여 개인 연체의 가능성, 개인의 신용등급 더욱 나아가 기업의 재정상태를 고려하여 기업의 파산을 예측해 볼 수 있는 기회였습니다.


# 5. 참고 
논문 참조 

 금융 빅데이터 개방시스템(CreDB)을 활용한 채무불이행 예측 모형에 관한 연구
조남용(Jo, Nam. 한국IT서비스학회 학술대회 논문집 Volume: 2019 Issue 2 (2019)

영상 참조 

 https://www.youtube.com/watch?v=frM_7UMD_-A&t=483s


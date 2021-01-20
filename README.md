# FPL-Fantasy-Premier-league-Forecasting

## Purpose

- 판타지 리그에서 제공하는 스탯을 이용해 다음 경기의 Point를 예상

## Algorithm

- 회귀(Regression) 알고리즘 이용
- Autokeras에서 제공하는 회귀 블럭 사용 (AK)
- LSTM 을 이용해 회귀 분석 (LSTM)
- XGBoost을 이용해 회귀 분석 (XGBoost)

## Result

- LSTM이 약간 더 좋은 성능을 보임
- 두 방법 모두 4가 넘는 MSE (Mean Squared Error) 값을 가짐
- 그래프로 보면 추세에서는 비슷한 면을 보임
- 단 대부분의 선수가 낮은 값(3 이하의) 을 가지는 경우가 대부분이므로 예측 값도 대부분 3이하의 값을 가지게 됨
- 스케일을 맞춰주면 더 좋은 예측성능을 보일 가능성이 있음
- XGBoost의 변수 중요도를 통해 분석한 결과는 이전 게임의 Yellow Card가 다음 게임 Point에 가장 큰 영향 (출전 여부 때문?)
- 그 외 중요 변수는 홈 게임 여부, 선수 가치 등
- 이전 게임의 어시스트, 보너스는 다음 게임 포인트에 영향이 없음.

## Limitation

- 선수의 특성에 따라 예측값이 달라질 수 있음 -> 그러나 선수별 예측 모델을 만들기에는 선수 개인이 가지고 있는 통계 자료가 너무 적음
- 실제 값에 비해 예측값의 스케일이 작게 움직임 

# Preprocessed Data

## 데이터
- 국민건강보험공단_건강검진정보(https://www.data.go.kr/data/15007122/fileData.do) 의 2014-2019년도 데이터

## 데이터 전처리
1. '기준년도' 등 당뇨병과 관련이 없는 항목 제거
2. 지나치게 수치가 큰 데이터, 비정상적인 값 제거
3. 식전혈당, 고혈압 여부, 복부비만 여부 class화

## columns
- '성별코드', '연령대코드', '허리둘레', '식전혈당', '총콜레스테롤', '트리글리세라이드', 'HDL콜레스테롤', 'LDL콜레스테롤', '혈색소', '요단백', '혈청크레아티닌', 'AST', 'ALT', '감마지티피', '흡연상태', '음주여부', '복부비만', '비만여부', '고혈압'

## csv 파일 설명
### data_test
- 전처리 한 2019년 데이터
- Test 용도로 사용

### data_preprocessed
- 전처리 된 2014, 2015, 2017, 2018년 데이터
- 17, 18년도의 데이터 모두 포함
- 14, 15, 17년도 중 당뇨병 전단계와 당뇨병 데이터 포함(정상 데이터 미포함)
- 16년도 데이터는 음주항목 전부 null로 미포함

| Class         | Numbers       |
| ------------- | ------------- |
| 0             | 800762        |
| 1             | 924629        |
| 2             | 234337        |

- Total: 1959728 rows, 19 columns

## data_preprocessed_over
- data_preprocessed을 SMOTE를 이용하여 Oversampling한 데이터

| Class         | Numbers       |
| ------------- | ------------- |
| 0             | 924629        |
| 1             | 924629        |
| 2             | 924629        |

- Total: 2773887 rows, 19 columns

## data_preprocessed_under
- data_preprocessed을 랜덤하게 Undersampling한 데이터

| Class         | Numbers       |
| ------------- | ------------- |
| 0             | 234337        |
| 1             | 234337        |
| 2             | 234337        |

- Total: 703011 rows, 19 columns

https://drive.google.com/file/d/1AcdYV-t6Ebu5lxTEvUotgsUWt5PhHAqa/view?usp=sharing

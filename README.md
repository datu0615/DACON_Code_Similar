# DACON_Code_Similar
![v3](https://user-images.githubusercontent.com/84311270/174436961-011b984f-12b2-4a26-a73d-e5ad6e6f3cf9.png)


두 코드간 유사성(동일 결과물 산출 가능한지) 여부를 판단할 수 있는 AI 알고리즘을 개발

## Dataset  
sample_train.csv [File] : 300개의 문제에 대한 코드 중에서 17970개의 Pair한 Sample로 추출한 데이터셋  
	│	├ code1 : 유사성을 비교할 Python 코드 1  
	│	├ code2 : 유사성을 비교할 Python 코드 2  
	│	└ similar : 0일 경우 서로 다른 문제를 해결하는 코드, 1일 경우 서로 같은 문제를 해결하는 코드  
	│
  
test.csv [File] : 학습 데이터에 없는 다른 문제 300개에 대한 코드 중에서 179700개의 Pair 쌍으로 이루어진 테스트용 데이터셋  
	│	├ pair_id : 각 pair 쌍에 부여되는 id 번호  
	│	├ code1 : 유사성을 비교할 Python 코드 1  
	│	└ code2 : 유사성을 비교할 Python 코드 2  
	│

sample_submission.csv [File]  
	│	├ pair_id : 각 pair 쌍에 부여되는 id 번호  
	│	└ similar : 0일 경우 서로 다른 문제를 해결하는 코드, 1일 경우 서로 같은 문제를 해결하는 코드  
	│  

code [Folder] : 학습용으로 주어지는 300개의 문제에 대한 코드  
		├ problem001 : 문제 번호  
		│	├ problem001_1.py : 문제(001)를 해결하는 솔루션 코드 1  
		│	├ problem001_2.py : 문제(001)를 해결하는 솔루션 코드 2  
		│	└ problem001_...  
		├ problem002 : 문제 번호  
		│	├ problem002_1.py : 문제(002)를 해결하는 솔루션 코드 1  
		│	├ problem002_2.py : 문제(002)를 해결하는 솔루션 코드 2  
		│	└ problem002_...    
		└ ...  
    
## Model  
re 모듈을 이용한 전처리 및 rank-bm25를 이용하여 pair를 구성하여 데이터 증강, graphcodebert-base 모델을 사용하여 학습.
   

#1. 'ex1.csv' 파일을 dataframe 형식으로 읽어서 출력하고
# 다시 0,1 행만 화면에 출력하세요.

import numpy as np
import pandas as pd

df=pd.read_csv('datasets/ex1.csv')
print(df)

print(df[0:2]) # 0~1번째 행 호출
print(df.loc[0:1]) # 이름기준호출 : 행 이름이 0, 1인 행 호출
print(df.iloc[0:2]) #순서 기준 호출: 순서가 0,1번째인 행 호출

#2.'ex2csv' 파일을 그대로 출력하고,
#두 줄 띄고, 'ex1.csv'과 똑같이 만들어 출력하세요

df=pd.read_csv('datasets/ex2.csv')
print(df)
print('\n')

df1=pd.read_csv('datasets/ex2.csv',names=['a','b','c','d','message'])
print(df1)

#3. 'ex2.csv'데이터를 읽어서 names를 이용하여 'ex1.csv'과 같은 컬럼명을 추가하고,
#'message'를 색인으로 하는 dataframe으로 구성하여 저장하고, 'a'열만 출력하세요.

df=pd.read_csv('datasets/ex2.csv')
print(df)
print('\n')

df=pd.read_csv('datasets/ex2.csv', names=['a','b','c','d','message'])
print(df1)
print('\n')

df1.index=df1['message']
df2=df1.drop(['message'],axis=1)
print(df2['a'])

 <p align="center">
  <h1 align="center">기계독해 모델 구현 ✨</h1>

  <p align="center">

## 프로젝트 소개 

Google의 BERT와 GPT통해 자연어 처리 과제에서 딥러닝 알고리즘의 탁월한 성능을 보여주는 것이 입증되었습니다. 그러나 위 모델을 그대로 한국어에서 번역, 질의응답. 분류 등의 문제에 적용하는 경우 영문과 비교하여 성능이 떨어집니다. 이를 해결하기 위해 데이터 전처리, 모델 비교 및 하이퍼파라미터 튜닝을 통해 최적의 기계독해 모델을 구현하였습니다. 

 
  <br/>
  
## STEP1 EDA

<br/>

Context:  “국민주택기금을 활용해 금리가 낮은 월세 대출 보증상품을 내놓는 방안을 협의하고 .....  <br/> 
한국은행에 35년간 몸담으며 조사국장, 부총재보 등을 지냈다. 주택금융공사는 이달 말까지 부산국제금융센터로 <br/>
이전해 다음달 1일부터 부산 시대를 시작한다. <br/>
<br/>

**Question:  "미국 하와이대 출신 인물이 취임한 날짜는?" Answer: "29일"**

<br/>
<br/>

데이터는 위와 같이 문맥과 질문 그리고 답변으로 구성된다.  

   '''python

   anwsers = dataset['answers']

   max_ = 0
   sum_ = 0
   lengths = []

   for answer in anwsers:
       for text in answer['text']:
           #@print(text)
           l = len(text)
           lengths.append(l)

            if l > max_:
                max_ = l

            sum_ += l

    print(f'Mean: {sum_/len(lengths)}, Max: {max_}')

'''
---
  
</p>
<br/>

## STEP1 모델 선정 

<br/>
<img src = "https://user-images.githubusercontent.com/86638764/211512808-66df2b6e-20c2-4da6-9c76-d58a61d4e7ca.png">

한국어 Machine Reading Comprehesion 데이터셋 KorQuard로 QA대회 'KorQuard'의 리더보드의 상위 성적을 기록한 대부분의 참가자들은 이 언어모델 BERT를 사용하였습니다.
마찬가지로 비슷한 수준의 높은 성능을 보여주는 GPT모델이 존재하지만 모델의 크기가 상대적으로 너무 커 주어진 GPU로 학습시키기 어려워 BERT 기반의 모델을 선정했습니다. 



## STEP2 모델 학습

Huggingface를 통해 사전학습된 모델을 불러와 학습을 진행했습니다. Hanbert, Kobert, Koelectra, KoRoberta, Kobart 등 다양한 모델을 실험하였고 

<br/>

## 기술스택 ⭐️

<br/>

---
<br/>




## Python! 
```python
print('hello world!')
```

<br/>

### AI tools 🚩

---

<br/>


<br/>

- Pytorch  
- wandb
- openCV
- huggingface
- numpy
- pandas 


<br/>

---

<br/>


## Projects 🍪

<br/>

---
<br/>



상추생장 예측 및 생육환경 예측 모델

문장분류 

질의응답모델 

CNN모델 numpy부터 구현(CNN from scatch)

Dacon 4D블록 분류대회 (in process)

X-ray영상을 통한 코로나 양성/음성 분류 모델 



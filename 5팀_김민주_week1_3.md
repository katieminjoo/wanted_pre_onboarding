# Week 1-3 과제(김민주)

# ****Extractive Text Summarization****

## What is this?

(여러 논문에서 이야기되어온 extractive text summarization 의 정의)

- Extractive summarization aims at identifying the salient information that is then extracted and grouped together to form a concise summary.
- extracting and composing important sentences from the given text
- Extractive summarization selects a subset of sentences from the text to form a summary
- >> 추출적 요약이란 문헌 내의 문장들 중에서 중요한 문장만 골라냄으로써 요약을 수행하고, 이는 각각의 문장이 얼마나 중요한지 혹은 사소한지를 분류하는 이진 분류 문제와 동일하다고 볼 수 있음. 문장 내에 등장하는 단어들이 주제어인지 비주제어인지 분류하는 이진 분류 문제인 자동 색인과 유사.
    
    따라서 자동색인에서 사용하던 기법들을 그대로 자동 요약에 사용할 수 있음.
    

## Dataset : **CNN/Daily Mail**

![Untitled](Week%201-3%20%E1%84%80%20a9d09/Untitled.png)

- The CNN / DailyMail Dataset is an English-language dataset containing just over 300k unique news articles as written by journalists at CNN and the Daily Mail.
- 'summarization': **[Versions 2.0.0 and 3.0.0 of the CNN / DailyMail Dataset](https://www.aclweb.org/anthology/K16-1028.pdf)**
 can be used to train a model for abstractive and extractive summarization (**[Version 1.0.0](https://papers.nips.cc/paper/5945-teaching-machines-to-read-and-comprehend.pdf)**
 was developed for machine reading and comprehension and abstractive question answering).
- For each instance, there is a string for the article, a string for the highlights, and a string for the id.

```
{'id': '0054d6d30dbcad772e20b22771153a2a9cbeaf62',
 'article': '(CNN) -- An American woman died aboard a cruise ship that docked at Rio de Janeiro on Tuesday, the same ship on which 86 passengers previously fell ill, according to the state-run Brazilian news agency, Agencia Brasil. The American tourist died aboard the MS Veendam, owned by cruise operator Holland America. Federal Police told Agencia Brasil that forensic doctors were investigating her death. The ship's doctors told police that the woman was elderly and suffered from diabetes and hypertension, according the agency. The other passengers came down with diarrhea prior to her death during an earlier part of the trip, the ship's doctors said. The Veendam left New York 36 days ago for a South America tour.'
 'highlights': 'The elderly woman suffered from diabetes and hypertension, ship's doctors say .\nPreviously, 86 passengers had fallen ill on the ship, Agencia Brasil says .'}
```

![Untitled](Week%201-3%20%E1%84%80%20a9d09/Untitled%201.png)

## SOTA MODELS

1. HAHSum (Rouge 44.68) (2019)
    
    ![HAHSum structure :: consists of ALBERT Encoder, Abstract Layer, Redundancy Layer, and Output Layer. ~~( 너무 어렵^^...)~~](Week%201-3%20%E1%84%80%20a9d09/Untitled%202.png)
    
    HAHSum structure :: consists of ALBERT Encoder, Abstract Layer, Redundancy Layer, and Output Layer. ~~( 너무 어렵^^...)~~
    
    - 기존연구 동향 : Recent neural network approaches to summarization are largely either selection-based extraction or generation-based abstraction.
    - 제안 ! This paper proposes a **neural model** for single document summarization based on joint extraction and syntactic compression.
    - <how model works>
    1. chooses sentences from the document
    2. identifies possible compressions based on constituency parses
    3. scores those compressions with a neural model to produce the final summary.
    - <Learning phase>
    
    construct oracle extractive compressive summaries, then learn both of our components jointly with this supervision.
    
2. MatchSUM (Rouge 44.41) (2020)
    
    ![80CF5E6A-B84C-4CFD-803B-44683C448016.jpeg](Week%201-3%20%E1%84%80%20a9d09/80CF5E6A-B84C-4CFD-803B-44683C448016.jpeg)
    
    - 기존 framework : extracting sentences individually and modeling the relationship between sentences
    - 제안! <Semantic matching problem>
        
        formulate the extractive summarization task as a semantic text matching problem, in which a source document and candidate summaries will be (extracted from the original text) matched in a semantic space
        

> 요약기법에는 ROUGE 성능 지표라는 것을 사용한다는 것을 처음 알게되었고 이에 대해 조사를 해보았다.
> 
> 
> 완전히 이해하기는 어렵지만 
> 
> [예시를 통한 ROUGE 성능 지표의 이해 - Programador | Huffon Blog](https://huffon.github.io/2019/12/07/rouge/)
> 

> 요약 태스크에 관해 동향 정리가 깔끔히 잘되어있어서 참고문헌으로 추가
> 

[자동 요약 기법의 연구 동향 정리](https://bab2min.tistory.com/625)

※
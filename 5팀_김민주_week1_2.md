# Week1-2 과제(김민주)

# Paperswithcode에서 NLU sub task 중 하나를 선택하여 정리해보세요.

- 문제 정의
    
    ### Relation Extraction
    
    - task가 해결하고자 하는 문제가 무엇인가?
        - Relation extraction is the task of predicting attributes and relations for entities in a sentence
        - **Relation Extraction is the key component for building relation knowledge graphs, and it is of crucial significance to natural language processing applications such as structured search, sentiment analysis, question answering, and summarization.**
    - 데이터 소개
        
        ### DocRED
        
        :: **DocRED (Document-Level Relation Extraction Dataset) is a relation extraction dataset constructed from Wikipedia and Wikidata.**
        
        https://github.com/thunlp/DocRED
        
        [](https://arxiv.org/pdf/1906.06127v3.pdf)
        
        ![Untitled](Week1-2%20%E1%84%80%E1%85%AA%2085eae/Untitled.png)
        
        - **DocRED contains 132,375 entities and 56,354 relational facts annotated on 5,053 Wikipedia documents. In addition to the human-annotated data, the dataset provides large-scale distantly supervised data over 101,873 documents.**
        - **Each document in the dataset is human-annotated with named entity mentions, coreference information, intra- and inter-sentence relations, and supporting evidence.**
        - **DocRED requires reading multiple sentences in a document to extract entities and infer their relations by synthesizing all information of the document. Along with the human-annotated data, the dataset provides large-scale distantly supervised data.**
        
        ![Untitled](Week1-2%20%E1%84%80%E1%85%AA%2085eae/Untitled%201.png)
        
    - SOTA(State-of-the-Art : 최신 기술) 모델 소개(대표 모델 2)
        1. **[SSAN-RoBERTa-large+Adaptation](https://paperswithcode.com/paper/entity-structure-within-and-throughout) (F1 65.92) (2021)**
            - paper
            
            [](https://arxiv.org/pdf/2102.10249v1.pdf)
            
            - keywords
                - SSAN
                    
                    ![Untitled](Week1-2%20%E1%84%80%E1%85%AA%2085eae/Untitled%202.png)
                    
                    - Structured Self-Attention Network (from transformer)
                    - it extends the standard self-attention mechanism with structural guidance.
                - mention dependencies
                - Document-Level Relation Extraction
                    - sentence level RE 에 국한되지 않고 더 나아가 document 전체의 맥락을 파악하는 document-level RE 가 frequently used
                - 
        2. **[SAIS-BERT-base](https://paperswithcode.com/paper/sais-supervising-and-augmenting-intermediate) (F1 62.77) (2021)**
            
            SAIS : supervising and augmenting intermediate steps
            
            RoBERTa 관련 모델들이 상위 5위를 차지하였지만 6위에 있는 bert base 모델은 어떤건지 궁금해서 넣어봤다.
            
            ![Untitled](Week1-2%20%E1%84%80%E1%85%AA%2085eae/Untitled%203.png)
            
            - paper
            
            [](https://arxiv.org/pdf/2109.12093v1.pdf)
            
            - keywords
                - Document Encoding
                - Coreference Resolution
                    - 대명사를 고유명사로 치환
                - Entity typing
                    - 불가능한 RE 타입 filtering
                - Pooled evidence retrieval
                    - To capture textual context
                - Fine grained evidence retrieval
                
            

※ 아래 항목을 하나의 파일로 정리하여 업로드 해주세요.

- 본인 아이디 및 닉네임

- 게시글 URL

- 게시글 캡처

2. 팀원들의 게시글을 읽고 피드백 댓글을 달아보세요.

※ 아래 항목을 하나의 파일로 정리하여 업로드 해주세요.

- 본인 아이디 및 닉네임

- 팀원 게시글 URL

- 해당 게시글에 작성한 댓글 캡처
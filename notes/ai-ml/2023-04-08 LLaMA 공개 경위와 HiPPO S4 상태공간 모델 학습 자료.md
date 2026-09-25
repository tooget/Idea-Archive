# LLaMA 공개 경위와 HiPPO/S4 상태공간 모델 학습 자료
*작성 2023-04-08 · 수정 2023-04-15*

https://morioh.com/p/8684334855e8  
https://github.com/facebookresearch/llama/pull/73/files  
학계에만 공개한 게 일반에 퍼짐 (진짜임)  
gpt3 보다 성능이 괜찮음  





차세대 Transformer? Hippo/S4  
시계열, 긴 문자열 데이터를 가지고 연산속도가 늦어지지 않음  
https://www.slideshare.net/DeepLearningJP2016/dlefficiently-modeling-long-sequences-with-structured-state-spaces 24P  
Path-X 문제를 유일하게 푼 모델  
다른 모든 태스크에서 Transformer 등을 포함한 다른 추론모델보다 압도적인 성능 우위  
Hippo/S4/S4d https://srush.github.io/annotated-s4/ 공부하기 좋음  
저자: https://stanford.edu/~albertgu/  
제어이론(상태-공간 모델)에서 영감을 받음https://www.google.com/search?q=control+state-space+model  
https://github.com/HazyResearch/state-spaces  
S4/S4d Cell이 엔지니어링 레벨에서 학계내 PyTorch의 구현체가 등장하기 시작함  
https://www.google.com/search?q=pytorch+s4dcell  

https://www.groovypost.com/howto/opt-out-your-data-on-chatgpt/

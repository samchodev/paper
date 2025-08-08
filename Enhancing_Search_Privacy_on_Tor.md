# Enhancing Search Privacy on Tor (2024~2025)

## [Tor 네트워크에서의 딥러닝 모델을 활용한 키워드 핑거프린팅 공격기법](https://www.dbpia.co.kr/pdf/pdfView.do?nodeId=NODE11862188&googleIPSandBox=false&mark=0&minRead=5&ipRange=false&b2cLoginYN=false&icstClss=010000&isPDFSizeAllowed=true&accessgl=Y&language=ko_KR&hasTopBanner=true) | 황채원, 전혜승, 김고운, 홍지우, 강호성, 오세은 | KCC 2024

### Keyword - Tor, Deep Learning, Keyword Fingerprinting(KF)

| 요약 | 딥러닝 모델(DKF)과 Winlap 피처를 적용하여 Tor 네트워크에서 키워드 핑거프린팅 공격의 정확성을 향상 |
| --- | --- |
| **문제** | . |
| **해결** | . |
| **실험** | . |
| **결과** | . |
| **한계** | . |

- Website Fingerprinting(WF) 공격: (Tor 네트워크의) 트래픽을 분석하여 사용자가 접속하는 웹사이트를 유추
- Keyword Fingerprinting(KF) 공격: 검색엔진에 입력한 검색어를 추적
    * 키워드는 사용자의 관심사, 습관, 질병 등 민감한 정보를 직접적으로 내포 -> WF보다 프라이버시 침해 심각

- State-of-the-Art KF 모델 성능을 향상시킨 딥러닝 기반 DKF(Deep Keyword Fingerprinting) 모델을 제안
- 효과적 학습 위한 대규모의 최신 데이터 세트를 수집

- 최초로 토르 네트워크상에서의 KF 공격에 딥러닝을 적용한 DKF 모델과 Winlap 피처를 제안
    * 핑거프린팅 공격의 정확성을 높임
- Winlap 피처는 트래픽을 일정한 시간 윈도우로 나누어 패킷의 수와 크기 정보를 활용
    * 기존에는 광범위한 시간 분포를 가지던 트래픽을 일정한 시간 단위로 정규화
    * 트래픽의 순차적인 정보를 유지하면서도 트래픽 패턴을 규칙적이고 추상화된 형태로 모델에 제공
- DKF는 기존 WF 및 KF 연구들에 비해 우수한 성능 / 토르 네트워크가 딥러닝을 적용한 KF 공격에 취약함을 증명
- CW 환경에서 두 가지 검색엔진 데이터에 대해 모두 80% 이상의 정확도 / OW 환경에서도 State-of-the-Art 달성

> Tor 네트워크가 여전히 KF 공격에 취약하므로 토르 네트워크의 KF 공격에 대한 방어기법 개발이 필요
> 본 연구의 KF 공격에 대한 취약점 분석이 방어 기법 연구에 도움을 줄 수 있을 것으로 기대

## [Poster] [Securing Search Privacy on Tor: Deep Keyword Fingerprinting and BurstGuard Defense](https://www.acsac.org/2024/files/web/poster-acsac24-final18.pdf) | Chaewon Hwang*, Haeseung Jeon*, Jiwoo Hong, Hosung Kang, Se Eun Oh | ACSAC, December 2024

### Keyword - Tor, Deep Learning, Keyword Fingerprinting(KF)

- Anonymous networks like Tor provide user anonymity by employing a 3-hop node routing system, where each node is aware of only its predecessor and successor.
- However, Keyword Fingerprinting (KF) attacks pose a threat to user privacy by inferring user-typed keywords through the analysis of traffic metadata, such as traffic volume and timing information.
- Despite the significant privacy risks associated with KF attacks, current research predominantly utilizes traditional machine learning (ML) techniques.
- This approach persists even though deep learning (DL) models have demonstrated improvements in analyzing Tor traffic, particularly in Website Fingerprinting (WF).
- To bridge this gap, we introduce a novel DL-based approach, Deep Keyword Fingerprinting, which utilizes a large dataset and extended WF features to significantly enhance existing fingerprinting models.
- Additionally, we explore a novel defense mechanism designed to disrupt keyword trace patterns, thereby bolstering search privacy on Tor.
- We extended the Traffic Aggregation Matrix (TAM) and developed a new KF feature that effectively captures keyword traffic patterns.
- Moreover, we developed a state-of-the-art KF model that significantly outperforms competing models, with a 41% higher accuracy than Tik-Tok, 48% higher than DF, and 55% higher than k-FP in the DuckDuckGo dataset.
- Lastly, we introduce a new padding-based KF defense that outperforms FRONT and WTF-PAD by 19% and 7%, with 66% and 24% reduced bandwidth overhead.

## [Enhancing Search Privacy on Tor: Advanced Deep Keyword Fingerprinting Attacks and BurstGuard Defense]() ACM AsiaCCS, July 2025

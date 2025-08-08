# DeepCoAST (2023~2024)

## [딥러닝 기반 분할 데이터 상관관계 탐지를 통한 Website Fingerprinting 방어 모델의 취약점 탐색](https://drive.google.com/file/d/1-BeWx9cO5HpAYIxE7zRV0j3Rqk9qsA4I/view) | 김고운, 곽현정, 김수진, 박지현, 박유희, 오세은 | KIISC Youngnam 2023

### Keyword - Tor, Website Fingerprinting, Deep Learning

| 요약 | 분할 경로 기반 WF 방어 기법의 취약점으로 분할 데이터 간 상관 관계 탐지 딥러닝 모델 제안 |
| --- | --- |
| **문제** | 분할경로 기반 WF 방어기법의 취약점이 있을까? |
| **해결** | 네트워크 트래픽 간 상관관계 분석해서 분할된 경로 찾아 트래픽 복원 |
| **실험** | BE 데이터셋에 TrafficSliver, HyWF, Conflux로 경로 셋팅을 시뮬레이션 한 95개의 사이트 트래픽 |
| **결과** | 방향 피처 < Tik-Tok 피처 / Epoch 증가시 Loss 감소 AUC 증가 / 95% 이상의 정확도? |
| **한계** | 2개로 분할된 트래픽만 실험 |

- 최근 가장 많이 사용되는 익명 네트워크인 Tor
- Tor를 대상으로 머신러닝 모델을 활용한 Website Fingerprinting 공격과 방어기법이 활발히 제안
- [TrafficSliver](https://sebastianreuter.info/publications/pdf/ccs-trafficsliver.pdf) [(Github)](https://github.com/TrafficSliver)는 Tor 유저가 Entry Node로 트래픽을 전송할 때 다중의 Entry Node들을 사용하여 여러 개의 경로로 나눠서 보내도록 하는 분할기법을 적용한 방어 모델
     * 기존의 공격 모델의 정확도를 현저하게 낮추는 강력한 방어기법
- 네트워크 트래픽 간 상관관계 분석 / 분할된 경로들을 찾아 / 하나의 경로를 사용했을 때와 같은 트래픽으로 복원시킬 수 있는 모델 제안
    * 분할 트래픽 쌍을 탐지하여 병합 ~= Vanilla Tor 네트워크에서 하나의 Entry 노드를 사용하여 수집한 트래픽
        - WF 공격 모델에 여전히 높은 정확도로 핑거프린팅 가능
- 분할 방법을 사용하는 방어기법이 여전히 Website Fingerprinting 공격으로부터 안전하지 않음

> IPD 피처 등 다른 피처를 탐색하여 기존 성능을 개선할 수 있는 방안들을 모색할 것  
> n개 (n>2)의 분할된 트래픽들을 대상으로 하는 상관관계 탐지모델을 제안할 예정

## [DeepCoAST: Unveiling Split Trace Correlation to Counter Traffic Splitting Defenses](https://ieeexplore.ieee.org/document/10737061) | Goun Kim, Hyeonjeong Kwak, Sujin Kim, Youhe Park, Jihyun Park, Se Eun Oh | IEEE Access, October 2024

### Keyword - Tor, Traffic Splitting Defenses, Deep Learning

| 요약 | 트래픽 분할 기법에 대항해 상관관계를 찾아 분할을 추적하는 딥러닝 모델 제안 |
| --- | --- |
| **문제** | 트래픽 분할 기법을 효과적으로 파훼할 수 있을까? |
| **해결** | 딥러닝 기반 상관 분석기인 DeepCoAST / DeepCoFFEA 기반 분할 트래픽에 강인한 특징 추출 모델 아키텍처 |
| **실험** | 세 가지 트래픽 분할 방어 기법-TrafficSliver, HyWF, CoMPS에서 생성된 95쌍의 분할 트래픽 |
| **결과** | AUC 0.98 |
| **한계** | 2개로 분할된 트래픽만 실험 |

- 토르 네트워크(Tor Network): 널리 사용되고 있는 익명화 네트워크
    * 사용자의 익명성을 보장하기 위해 다양한 연구 지속
    * 트래픽 분석 공격에 취약 -> 네트워크 레벨의 공격자가 통신의 양 종단을 추론할 수 있음
- 트래픽 분석 공격의 대표적인 예
    * 웹사이트 핑거프린팅(Website Fingerprinting) 공격
    * 종단 간 흐름 상관 분석(End-to-End Flow Correlation) 공격
- 트래픽 분석 공격의 위협에 대응하기 위해 다양한 방어 기법이 제안
- 최근 트래픽 분할기법을 이용한 방어 모델이 효과적인 방안으로 주목
- 트래픽 분할기법: 추가적인 대역폭 소모 없이 패킷을 여러 회로로 나누어 전송함으로써 공격자가 관찰할 수 있는 트래픽 정보를 제한하는 방법
- 트래픽 분할 기법을 대상으로 **딥러닝 기반 상관 분석기(Correlator)인 DeepCoAST**
    * _두 개의_ 분할된 트래픽 간의 상관성을 분석 / 상관성이 높은 트래픽을 병합 / 핑거프린팅 공격의 가능성 평가
- DeepCoAST를 위해 보다 효과적인 상관관계 특징을 제안하기 위해 WF 특성에 기반한 정교한 특징 분석을 수행
    * [DeepCoFFEA](https://ieeexplore.ieee.org/document/9833801) [(Github)](https://github.com/traffic-analysis/deepcoffea)를 기반으로 하여 분할 트래픽에 강인한 특징 추출 모델 아키텍처를 설계
- 세 가지 트래픽 분할 방어 기법-TrafficSliver, HyWF, CoMPS에서 생성된 95쌍의 분할 트래픽에 대해 AUC 0.98을 달성
- DeepCoAST와 같은 공격을 효과적으로 방어하기 위해 트래픽 분할 기반 웹사이트 핑거프린팅 방어 메커니즘의 추가적인 개선이 필요

> 다양한 네트워크 경로 설정에서의 DeepCoAST 평가 및 모델 고도화에 대한 후속 연구의 필요성  

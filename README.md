# Capstone_2022

캡스톤 디자인2 추천시스템 연구 내용입니다.

- **일반화 및 경량화를 목적으로 한 ADLFM**
    - 주요내용
    
    잠재 요인 모델의 한계를 개선하고자 각각의 아이템별로 사용자의 선호도를 적응적으로 학습하는 ADLFM이 등장하였습니다. 이는 아이템의 특징을 설명하는 Item Description을 입력으로 받아 사용자와 아이템의 잠재 벡터를 구하고 Attention Score를 활용하여 개인의 다양성을 반영할 수 있는 방법을 제시합니다. 하지만 아이템 설명을 포함하는 데이터 셋을 요구하기 때문에 적용할 수 있는 대상이 많지 않아 한계가 있습니다. 논문에서는 아이템 설명 대신 보편적으로 사용하는 item ID를 입력으로 하고 Self-Attention, Multi-head attention, Multi-Conv1d 등 개선된 딥러닝 모델 구조를 적용함으로써 ADLFM의 한계를 개선할 수 있는 일반화된 ADLFM(G-ADLFM)을 제안합니다. 결론적으로 기존 ADLFM의 성능은 최대한 유지하면서 빠른 학습과 추론이 가능하고(경량화) 다양한 도메인에 적용할 수 있는(일반화) 새로운 모형입니다.

<h1>📌 Intro</h1><br>
패션 판독기는 조코딩 유튜버님의 가이드에 따라 만든 토이 프로젝트입니다. 이 프로젝트는 사용자에게 이미지를 제출하고 그 이미지를 기반으로 옷의 패션 스타일을 판독합니다.<br><br>

우리는 패션 스타일 분류 시스템을 구축하여 개인의 스타일 선호도를 파악하고자 합니다. <br><br>

사용자의 이미지를 입력으로 받아 해당 이미지를 주요 패션 스타일 카테고리로 분류하는 문제를 해결하고자 합니다.<br><br>


<h1>📌 Implementation</h1><br>

<a href="https://teachablemachine.withgoogle.com/models/T6def4dBV/">티처블머신</a>으로 스트리트 스타일, 클래식 스타일, 복고 스타일, 미니멀 스타일, 보헤미안 스타일을 머신러닝으로 학습시켜서 자바스크립트 코드로 받아왔습니다
<ol>
 <li>데이터 수집: 다양한 패션 스타일의 이미지 데이터를 수집하였습니다.</li>

 <li>데이터 전처리: 수집한 데이터를 정제하고, 티처블 머신에 적합한 형식으로 가공했습니다.</li>

 <li>티처블 머신 모델 생성: 수집한 데이터를 사용하여 티처블 머신을 학습시켜 패션 스타일을 분류할 수 있는 모델을 생성했습니다.</li>

 <li>모델 평가: 학습된 모델을 평가하여 분류 정확도와 성능을 검증했습니다.</li>
</ol>
<br><br>
<a href="https://codepen.io/aaronvanston/pen/yNYOXR">코드 펜</a>에 드래그 엔 드랍으로 이미지를 업로드 할 수 있는 오픈소스를 가져와서 티처블머신의 코드와 결합했습니다<br><br>

사진으로만 처리 할 예정이라 비디오 처리 자바스크립트 부분을 삭제하고 출력시킬 프리셋 타이틀을 만들었습니다<br><br>

학습시킨 데이터에 맞춰서 출력시킬 프리셋 데이터를 만들었습니다

```
switch (prediction[0].className) {
                        case "스트리트":
                            resultTitle = "스트리트"
                            resultExplain = " 독특하고 개성적인 스타일로, 스트리트 패션과 스케이트보드 문화에서 영감을 받은 의상을 착용합니다"
                            resultCeleb = "# 오버사이즈 티셔츠  # 조거 팬츠  # 스니커즈 "
                            break;
                        case "클래식":
                            resultTitle = "클래식"
                            resultExplain = "전통적이고 우아한 느낌을 가진 스타일로, 단정하고 고급스러운 의상을 선호합니다"
                            resultCeleb = "# 테일러드 슈트  # 카디건  # 플로럴 패턴 드레스"
                            break;
                        case "복고":
                            resultTitle = "복고"
                            resultExplain = "거의 패션 트렌드에 영감을 받은 스타일로, 70년대, 80년대, 90년대 등 특정 시대의 패션 요소를 재현합니다"
                            resultCeleb = "# 와이드 레그 팬츠  # 저지  # 재킷"
                            break;
                        case "미니멀":
                            resultTitle = "미니멀"
                            resultExplain = "깔끔하고 심플한 디자인을 선호하는 스타일로, 단순하면서도 세련된 룩을 만들어냅니다"
                            resultCeleb = "# 블랙 앤 화이트 조합  # 심플한 원피스  # 슬립 드레스"
                            break;
                        case "보헤미안":
                            resultTitle = "보헤미안"
                            resultExplain = "자유로운 영혼과 부유한 감성을 표현하는 스타일로, 자연스러운 실루엣과 플로우 장식, 프린트 패턴 등을 활용합니다"
                            resultCeleb = "# 플로럴 원피스  # 와이드 브림햇  # 부츠 "
                            break;
                        default:
                            resultTitle = "알수없음"
                            resultExplain = ""
                            resultCeleb = ""
                    }
```

각 분석 결과에 따라 해당하는 스타일에 대한 제목, 설명 및 해당하는 옷들을 표시하며 바 차트를 사용해서 데이터를 시각화 해서 사용자에게 제공하도록 하였습니다

<h1>📌 Last (show) </h1><br>

입력된 이미지를 기반으로 분류된 스타일을 확인할 수 있으며, 이를 통해 개인의 스타일 선호도를 파악할 수 있습니다.

![screencapture-file-C-Users-User-OneDrive-1-AiMl-index-html-2024-04-25-11_23_41](https://github.com/TEEPUT/AI_FashionReader/assets/129711481/5de04f78-5010-406d-8b25-8ad542336eef)
복고 스타일이 강한 패션은 아래 결과와 같이 잘 표시해주는걸 알 수 있습니다 <br><br>

![screencapture-file-C-Users-User-OneDrive-1-AiMl-index-html-2024-04-25-11_24_03](https://github.com/TEEPUT/AI_FashionReader/assets/129711481/8fdfa90d-4acf-45bb-8494-02c88f5d2617)
스트리트 스타일과 복고 스타일의 혼합적인 패션 스타일인데 아래 결과와 같이 복고 스타일이 좀 더 많은 비중을 차지하는걸 알 수 있습니다 <br><br>





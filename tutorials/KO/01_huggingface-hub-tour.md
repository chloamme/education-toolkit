# 워크샵: Hugging Face Hub 투어

<aside>

💡 **환영합니다!**

대학 강사들이 실습, 과제 또는 수업을 쉽게 준비할 수 있는 툴킷을 준비했습니다. 이 콘텐츠는 기존 커리큘럼에  쉽게 통합될 수 있도록, 필요한 것들이 자체 완비된 방식으로 설계했습니다. 모든 콘텐츠는 **무료**이며, 널리 알려진 오픈소스 기술(`transformers`, `gradio` 등)을 사용합니다.

또는, Hugging Face 팀 멤버에게 튜토리얼 강연을 요청하기 위해서는 [ML demo.cratization 투어](https://www.notion.so/ML-Demo-cratization-tour-with-66847a294abd4e9785e85663f5239652)를 참조해주세요.

[여기](https://www.notion.so/Education-Toolkit-7b4a9a9d65ee4a6eb16178ec2a4f3599)에서 준비한 모든 튜토리얼과 자료를 찾아보실 수 있습니다. 

</aside>

**소요시간:** 20-40분

**목표:** 머신러닝(ML) 생태계와 팀에서 협엽할 수 있는, 무료 [Hub platform](http://hf.co)를 효과적으로 사용하는 방법 습득

학습 목표:

- Hub에서 공유하는 30,000개 이상의 모델을 탐색하는 방법 배우기
- 해결하고자 하는 task에 적합한 모델과 데이터셋을 찾는 효율적인 방법 배우기
- 기여(contribute) 및 협업하는 방법 배우기
- 커뮤니티에서 만든 ML 데모 탐색해보기

**형식:** 짧은 실습 또는 숙제

**대상:** 기존 모델을 사용하고자 하거나 모델을 공유하고자 하는 모든 백그라운드의 학생

**사전 요구사항**

- 머신러닝에 대한 높은 수준의 이해
- (선택사항이나 권장함) Git 사용 경험 ([참고자료](https://learngitbranching.js.org/))

## **왜 Hub인가?**

Hub는 누구나 모델, 데이터셋, ML 데모를 공유하고 탐색할 수 있는 중앙 플랫폼입니다. "AI 해답" 문제는 한 회사가 해결하는 것이 아니라 지식과 자원을 공유하는 문화로서 해결될 것입니다. 그래서 Hub는 가장 광범위한 오픈 소스 모델, 데이터셋, 데모 컬렉션을 구축하는 것을 목표로 합니다.

허깅페이스 Hub에 대한 몇가지 사실들:

- 30,000개 이상의 공개된 모델이 있습니다.
- 자연어 처리, 컴퓨터 비전, 오디오/음성, 강화학습을 위한 모델이 있습니다!
- 180개 이상의 언어에 대한 모델이 있습니다.
- 어떤 ML 라이브러리라도 Hub를 활용할 수 있습니다: 텐서플로 및 파이토치에서 spaCy, SpeechBrain, 20개의 다른 라이브러리와의 advanced 통합까지 가능합니다.

## 모델 탐색하기

모델 탐색을 시작해봅시다. [hf.co/models](http://hf.co/models)에 30,000개의 모델이 있습니다. 가장 많이 다운로드된 모델 중 하나로 [gpt2](https://huggingface.co/gpt2)를 볼 수 있습니다. 클릭해봅시다.

모델을 클릭하면 웹사이트는 모델 카드로 이동합니다. 모델 카드는 모델을 문서화하는 도구로, 모델에 대한 유용한 정보를 제공하고 검색 가능성 및 재현성에 필수적입니다.

인터페이스에는 많은 컴포넌트가 있으므로 하나씩 살펴보겠습니다:

[https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt](https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt)

- 화면 상단에서, 태스크(*text generation, image classification*, 등), 프레임워크(*PyTorch*, *TensorFlow*, 등), 모델 언어(*English*, *Arabic*, *등*), 라이선스(*예를들어 MIT*)와 같은 다양한 **태그**를 찾을 수 있습니다.

![](../../images/mode_card_tags.png)

- 오른쪽 열에서, *Inference API*를 사용하여 브라우저에서 바로 모델을 실행해볼 수 있습니다. GPT2는 텍스트 생성 모델이므로, 주어진 초기 입력에 따라 추가적인 텍스트를 생성합니다. “It was a bright and sunny day.”와 같이 입력해보세요.

![](../../images/model_card_inference_api.png)

- 중앙에서, 모델 카드 내용을 살펴볼 수 있습니다. 용도 및 제한사항, 트레이닝 절차, 인용 정보와 같은 섹션이 있습니다.  

![](../../images/model_card_content.png)

이러한 모든 데이터는 어디에서 올까요? 허깅페이스에서는, 모든 것은 **Git repositories**에 기반으로 하며 오픈소스입니다. 모델 카드는 **([README.md](http://README.md))** 마크다운 파일이며, 콘텐츠 상단에 태그 등의 메타데이터를 포함하고 있습니다.

![](../../images/model_card_git.png)

모든 모델은 Git-기반의 repository이므로, 버전 컨트롤이 가능합니다. GitHub와 마찬가지로 Git 클론, add, 커밋, 브랜칭, push 등을 할 수 있습니다. Git를 사용해본적이 없다면, 이 [자료](https://learngitbranching.js.org/)를 살펴보세요.

**도전 1**. GPT2 repository의 `config.json` 파일을 여세요. 이 config 파일은 하이퍼파라미터와 모델 로딩에 유용한 정보가 포함되어 있습니다. 이 파일에서 다음에 답해보세요:

- 활성화 함수(activation function)는 무엇입니까?
- 어휘(vocabulary) 크기는 얼마입니까?

## **모델 탐색하기**

지금까지 우리는 하나의 모델을 탐색했습니다. 가봅시다! [https://huggingface.co/models](https://huggingface.co/models)의 좌측에서 다양한 것들을 필터링해서 찾아볼 수 있습니다.

- **Tasks:** 다양한 도메인에서 여러가지 task에 대한 지원이 있습니다: 컴퓨터 비전(Computer Vision), 자연어 처리(Natural Language Processing), 오디오(Audio), 기타 등등. +13을 클릭해서 모든 가능한 task를 볼 수 있습니다. 
- **Libraries:** Hub는 원래 transformers 모델을 위한 것이었지만, 여러가지 라이브러리들과 통합되었습니다. Keras, spaCy, allenNLP 등의 모델을 찾을 수 있습니다. 
- **Datasets:** 또한 Hub는 수천개의 데이터셋을 호스팅합니다. 이 것에 대해서는 조금 후에 알아보겠습니다.

![](../../images/model_card_filters.png)

- **Languages:** Hub의 많은 모델은 NLP관련 입니다. low-resource language((번역 중 설명 추가) 영어/중국어/스페인어 등 처럼 모델을 훈련하기 위해 많은 언어 자원이 있는 언어와 다르게, 해당 언어를 사용하고 있는 사람이 적어서 언어 자원도 적은 언어들이 있으며 그러한 언어들의 종류는 많습니다(예: 타밀어, 텔루구어 등). 이런 경우, 보통 대량의 언어 자원을 필요로 하는 언어 관련 모델 학습에 어려움이 있기 때문에, row-resource language라는 연구 분야로 다양하게 해결하고자 하는 시도가 있습니다.)를 포함하여 수백개의 language에 대한 모델을 찾을 수 있습니다.

**도전 2**. 영어 모델에서 몇개의 토큰 분류 모델(token classification models)이 있습니까?

**도전 3**. 자동 음성 인식(Automatic Speech Recognition)을 위해 스페인어 모델을 선택해야 한다면, 무엇을 선택하겠습니까? (이 task와 language를 위해 어떤 모델도 가능)

## 모델 올리기

Hub에 모델을 업로드하려고 한다고 가정하겠습니다. Scikit-learn, Keras, Transformers 등 어떤 ML 라이브러리의 모델도 가능합니다.
각 스텝을 살펴보겠습니다.

1. 새로운 모델 repository를 생성하기 위해 [huggingface.co/new](http://huggingface.co/new)로 갑니다. 생성하려는 repository는 공개 또는 비공개 모두 가능합니다. 
2. 모델 카드가 있는 공개 레포로 시작해보겠습니다. 웹 UI 또는 Git을 통해 모델 업로드를 할 수 있습니다. 아직 Git을 사용해보지 않았다면, 웹 인터페이스를 사용하는 것을 추천합니다. Add File을 클릭하고, 올리고 싶은 곳에 file을 놓습니다. 전체 워크플로우를 이해하고 싶다면 Git을 통한 접근 방식을 사용하세요.

    1. git과 git-lfs를 시스템에 설치하세요.
        1. Git: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
        2. Git-lfs: [https://git-lfs.github.com/](https://git-lfs.github.com/). 큰 파일은 Git LFS로 업로드해야 합니다. ML 분야에서 자주 발생하는 몇 메가바이트를 초과하는 파일에 대해서는 Git이 잘 동작하지 않습니다. ML 모델은 기가바이트 또는 테라바이트까지 될 수도 있습니다! 🤯
    2. 방금 생성한 레포지토리를 클론합니다.

        ```python
        git clone https://huggingface.co/<사용자이름>/<모델id>
        ```

    3. 해당 디렉토리로 이동 및 Git LFS 초기화
        1. 선택사항입니다. `.gitattributes`에 큰 파일에 대한 공통 파일 확장자의 목록을 제공하고 있습니다. 만약 업로드 하려는 파일이 `.gitattributes` 파일에 포함되어 있지 않다면, 여기 기술된 것이 필요할 수 있습니다. 다음과 같이 할 수 있습니다.

            ```python
            git lfs track "*.your_extension"
            ```

            ```python
             git lfs install
            ```

    4. 파일을 레포지토리에 추가합니다. 파일은 사용 중인 프레임워크/라이브러리에 따라 다릅니다. 전반적으로 중요한 것은 모델을 로딩하기 위해 필요한 모든 아티팩트를 제공하는 것입니다. 예를 들어:
        1. 텐서플로우의 경우, SavedModel이나 `h5` 파일을 업로드 해야합니다.
        2. 파이토치인 경우, 일반적으로 `pytorch_model.bin` 입니다.
        3. 사이킷런의 경우, 일반적으로 `joblib` 파일입니다.

        사이킷런 모델 파일을 저장하는 파이썬 예제입니다. 

        ```python
        from sklearn import linear_model
        reg = linear_model.LinearRegression()
        reg.fit([[0, 0], [1, 1], [2, 2]], [0, 1, 2])

        from joblib import dump, load
        dump(reg, 'model.joblib')
        ```

    5. 커밋하고 파일을 푸쉬합니다. (파일이 레포지토리에 저장되었는지 확인합니다.)

    ```python
    git add .
    git commit -m "First model version"
    git push
    ```

우리는 해냈습니다! 레포지토리에서 모든 최근에 추가된 파일을 확인할 수 있습니다!

![](../../images/model_card_updated_repo.png)

이 UI에서는 모델 파일과 커밋들을 탐색할 수 있으며 각 커밋 간의 차이를 알 수 있게 해줍니다.

**도전 4**. 당신의 차례입니다! 당신이 선택한 라이브러리의 더미 모델을 업로드 하세요.

이제 모델이 Hub에 올라가 있고, 다른 사람들이 찾을 수 있습니다! 조직을 생성하여 다른 사람들과 쉽게 협업할 수도 있습니다. Hub를 통한 호스팅은 팀이 레포지토리를 업데이트할 수 있게 하며, 브랜치에서 작업하거나 공동 작업하는 것과 같이 익숙한 작업 방식을 수행할 수 있도록 합니다. 

`README`의 상단에 메타데이터가 있습니다. 지금은 라이선스만 있지만, 더 많은 것을 추가할 수 있습니다. 그 중 일부를 시도해 보겠습니다.

```yaml
 tags:
- es       # 이 것은 자동으로 언어 태그로 감지됩니다. 
- bert     # 필터링을 위한 부가적인 태그를 넣을 수 있습니다. 
- text-classification # 이 것은 자동으로 task tag로 감지 됩니다. 
datasets:
- llamas # 이 것이 허브에 만약 있다면, 허브의 데이터셋에 연결됩니다.
```

**도전 5**. 이 [문서](https://huggingface.co/docs/hub/model-repos#how-are-model-tags-determined)을 사용하여, 위젯에 있는 기본 예제를 변경하세요.

메타데이터는 다른 사람들이 당신의 모델을 빠르게 탐색할 수 있도록 합니다. 이제, 스페인어로 된 텍스트 분류 모델을 검색할 때 모델이 나타납니다. 모델은 데이터셋을 볼 때도 표시됩니다. 

잠깐...데이터셋?

## 데이터셋

ML 파이프라인을 사용하면, 모델을 훈련할 데이터셋이 있습니다. Hub는 오픈소스이며 여러 도메인에서 무료로 사용할 수 있는 약 3000개의 데이터셋을 호스팅합니다. 게다가 오픈소스 `datasets` [라이브러리](https://huggingface.co/docs/datasets/)는 이러한 데이터셋을 사용하기 쉽도록 하며, 스트리밍과 같은 매우 편리한 피쳐를 사용하여 거대한 데이터셋도 쉽게 사용할 수 있습니다. 이 실습은 라이브러리를 살펴보지는 않지만 라이브러리를 탐색하는 방법에 대해 설명합니다. 

모델과 마찬가지로, [https://hf.co/datasets](https://hf.co/datasets)로 이동할 수 있습니다. 좌측에서, task, 라이선스, 데이터셋 사이즈에 대한 다양한 필터를 찾을 수 있습니다.

NLP 모델의 성능을 테스트 용도로 가장 유명한 [GLUE](https://huggingface.co/datasets/glue) 데이터셋을 탐색해봅시다. 

- 모델 레포지토리와 마찬가지로, 데이터셋을 문서화하는 데이터셋 카드가 있습니다. 조금 아래로 스크롤하면, 요약, 구조 등을 찾을 수 있습니다. 

![](../../images/datasets_card.png)

- 상단에서, 브라우저에서 직접 데이터셋의 일부를 탐색해볼 수 있습니다. GLUE 데이터셋은 COLA 및 QNLI와 같이 선택할 수 있는 여러개의 하위 데이터셋 (또는 서브셋)으로 나뉘어져 있습니다. 

  ![](../../images/datasets_slices.png)

- 데이터셋 카드의 우측에서, 이 데이터셋을 훈련에 사용한 모델의 리스트를 볼 수 있습니다. 

![](../../images/datasets_models_trained.png)

**도전 6**. 공통 음성 데이터셋을 찾아봅니다. 아래 질문들에 답해보세요:

- 공통 음성 데이터셋은 어떤 태스크에 사용할 수 있습니까?
- 이 데이터셋에서 다루는 언어는 몇개입니까?
- 데이터셋 분할은 무엇입니까?

## ML 데모

모델 및 데이터셋 공유도 좋지만 공개적으로 사용 가능한 대화형 데모는 훨씬 더 좋습니다. 모델의 데모는 생태계에서 점점 중요한 부분을 차지합니다. 데모는 아래와 같은 것들을 가능하게 합니다:

- 모델 개발자가 이해 관계자 프리젠테이션, 컨퍼런스, 수업 프로젝트와 같이 다양한 청중에게 자신의 작업을 쉽게 **프리젠테이션** 하기
- 모델을 테스트하는 장벽을 낮춤으로써 머신러닝의 **재현성**을 높이기
- 비기술적인 청중에게 **모델의 임팩트**를 공유하기
- 머신러닝 **포트폴리오** 구축하기

Gradio 및 Streamlit과 같은 오픈소스 파이썬 프레임워크는 이러한 데모를 매우 쉽게 구축할 수 있게 해주며, 허깅페이스 [Spaces](http://hf.co/spaces/launch)와 같은 툴은 호스팅하고 공유할 수 있도록 합니다. 후속 실습으로, **Gradio 및 Hugging Face를 이용한 머신러닝 데모 구축 및 호스팅** 튜토리얼 해보기를 추천합니다. 

> 이 튜토리얼에서 다음을 수행합니다:
>
> - 커뮤니티에서 만든 ML 데모 탐색하기.
> - `gradio` 라이브러리를 이용하여 머신러닝 모델을 위한 파이썬 데모를 빠르게 구축하기
> - Hugging Face Spaces를 이용하여 무료로 데모 호스팅하기
> - 수업이나 컨퍼런스를 위해 Hugging Face org에 게시하기
>
> ***소요시간: 20-40 분***
>
> 👉 [튜토리얼에 액세스하려면 여기를 클릭하십시오](https://colab.research.google.com/github.com/huggingface/education-toolkit/tree/main/02_ml-demos-with-gradio.ipynb)

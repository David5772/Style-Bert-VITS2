# Style-Bert-VITS2

**이용 시에는 반드시 [부탁과 기본 모델 이용 약관](/docs/TERMS_OF_USE.md)을 읽어주시기 바랍니다.**

Bert-VITS2 with more controllable voice styles.

https://github.com/litagin02/Style-Bert-VITS2/assets/139731664/e853f9a2-db4a-4202-a1dd-56ded3c562a0

You can install via `pip install style-bert-vits2` (inference only), see [library.ipynb](/library.ipynb) for example usage.

- **해설 튜토리얼 비디오** [YouTube](https://youtu.be/aTUSzgDl1iY) [니코니코 동화](https://www.nicovideo.jp/watch/sm43391524)
- [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](http://colab.research.google.com/github/litagin02/Style-Bert-VITS2/blob/master/colab.ipynb)
- [**자주 묻는 질문** (FAQ)](/docs/FAQ.md)
- [🤗 온라인 데모는 여기서 확인하세요](https://huggingface.co/spaces/litagin/Style-Bert-VITS2-Editor-Demo)
- [Zenn의 해설 기사](https://zenn.dev/litagin/articles/034819a5256ff4)

- [**릴리즈 페이지**](https://github.com/litagin02/Style-Bert-VITS2/releases/), [업데이트 내역](/docs/CHANGELOG.md)
  - 2024-06-16: Ver 2.6.0 (모델의 차분 병합, 가중 병합, 널 모델 병합 추가, 사용 방법에 대해서는 [이 기사](https://zenn.dev/litagin/articles/1297b1dc7bdc79) 참조)
  - 2024-06-14: Ver 2.5.1 (이용 약관을 '부탁'으로 변경한 것만)
  - 2024-06-02: Ver 2.5.0 (**[이용 약관](/docs/TERMS_OF_USE.md) 추가**, 폴더 분류를 통한 스타일 생성, Koharune Ami 및 Amitaro 모델 추가, 설치 속도 향상 등)
  - 2024-03-16: ver 2.4.1 (**bat 파일을 통한 설치 방법 변경**)
  - 2024-03-15: ver 2.4.0 (대규모 리팩토링 및 다양한 개선, 라이브러리화)
  - 2024-02-26: ver 2.3 (사전 기능 및 에디터 기능 추가)
  - 2024-02-09: ver 2.2
  - 2024-02-07: ver 2.1
  - 2024-02-03: ver 2.0 (JP-Extra)
  - 2024-01-09: ver 1.3
  - 2023-12-31: ver 1.2
  - 2023-12-29: ver 1.1
  - 2023-12-27: ver 1.0

This repository is based on [Bert-VITS2](https://github.com/fishaudio/Bert-VITS2) v2.1 and Japanese-Extra, so many thanks to the original author!

**개요**

- 입력된 텍스트 내용을 바탕으로 감정이 풍부한 음성을 생성하는 [Bert-VITS2](https://github.com/fishaudio/Bert-VITS2) v2.1과 Japanese-Extra를 기반으로, 감정과 발화 스타일을 강약 포함하여 자유롭게 제어할 수 있게 한 것입니다.
- Git이나 Python이 없는 사람도 (Windows 사용자라면) 쉽게 설치하고 학습할 수 있습니다. (많은 부분을 [EasyBertVits2](https://github.com/Zuntan03/EasyBertVits2/)에서 차용했습니다). 또한 Google Colab에서의 학습도 지원합니다: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](http://colab.research.google.com/github/litagin02/Style-Bert-VITS2/blob/master/colab.ipynb)
- 음성 합성에만 사용할 경우, GPU가 없어도 CPU로 동작합니다.
- 음성 합성에만 사용할 경우, Python 라이브러리로 `pip install style-bert-vits2`를 통해 설치할 수 있습니다. 예시는 [library.ipynb](/library.ipynb)를 참조하세요.
- 다른 시스템과 연계하여 사용할 수 있는 API 서버도 포함되어 있습니다 ([@darai0512](https://github.com/darai0512) 님의 PR입니다, 감사합니다).
- 원래 "즐거운 글은 즐겁게, 슬픈 글은 슬프게" 읽는 것이 Bert-VITS2의 강점이므로, 스타일 지정이 기본 설정이어도 감정이 풍부한 음성을 생성할 수 있습니다.


## 사용 방법

- CLI 사용 방법은 [여기](/docs/CLI.md)를 참조하세요.
- [자주 묻는 질문](/docs/FAQ.md)도 참조하세요.

### 동작 환경

각 UI와 API 서버는 Windows 명령 프롬프트, WSL2, Linux(Ubuntu Desktop)에서 동작 확인을 완료했습니다(WSL에서는 경로 지정 시 상대 경로 등을 활용하세요). NVidia의 GPU가 없을 경우 학습은 불가능하지만 음성 합성과 병합은 가능합니다.

### 설치

Python 라이브러리로서의 pip 설치 및 사용 예제는 [library.ipynb](/library.ipynb)를 참조하세요.

#### Git이나 Python에 익숙하지 않은 분들

Windows를 전제로 합니다.

1. [이 zip 파일](https://github.com/litagin02/Style-Bert-VITS2/releases/download/2.6.0/sbv2.zip)을 **경로에 일본어나 공백이 포함되지 않은 위치에** 다운로드하여 압축을 풉니다.
  - 그래픽 카드(GPU)가 있는 분은 `Install-Style-Bert-VITS2.bat`을 더블 클릭합니다.
  - 그래픽 카드(GPU)가 없는 분은 `Install-Style-Bert-VITS2-CPU.bat`을 더블 클릭합니다. CPU 버전에서는 학습은 불가능하지만 음성 합성과 병합은 가능합니다.
2. 기다리면 자동으로 필요한 환경이 설치됩니다.
3. 이후 자동으로 음성 합성을 위한 에디터가 실행되면 설치가 성공한 것입니다. 기본 모델이 다운로드되므로 바로 사용할 수 있습니다.

또한 업데이트를 원할 경우 `Update-Style-Bert-VITS2.bat`을 더블 클릭하세요.

단, 2024-03-16의 **2.4.1** 버전 미만에서 업데이트하는 경우, 모든 파일을 삭제한 후 다시 설치해야 합니다. 죄송합니다. 이동 방법은 [CHANGELOG.md](/docs/CHANGELOG.md)를 참조하세요.

#### Git이나 Python을 사용할 수 있는 분들

Python의 가상 환경 및 패키지 관리 도구인 [uv](https://github.com/astral-sh/uv)가 pip보다 빠르므로, 이를 사용하여 설치하는 것을 권장합니다.
(사용하고 싶지 않다면 일반 pip도 괜찮습니다.)

```bash
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
git clone https://github.com/litagin02/Style-Bert-VITS2.git
cd Style-Bert-VITS2
uv venv venv
uv pip install torch torchaudio --index-url https://download.pytorch.org/whl/cu118
uv pip install -r requirements.txt
venv\Scripts\activate
python initialize.py  # 필요한 모델과 기본 TTS 모델을 다운로드
```
마지막 단계를 잊지 마세요.

### 음성 합성

음성 합성 에디터는 `Editor.bat`을 더블 클릭하거나 `python server_editor.py --inbrowser` 명령어로 실행할 수 있습니다 (`--device cpu` 옵션을 사용하여 CPU 모드로 실행). 에디터에서 각 대사별로 설정을 변경하여 스크립트를 작성하거나, 저장, 불러오기, 사전 편집 등을 할 수 있습니다. 설치 시 기본 모델이 다운로드되므로 학습하지 않아도 사용할 수 있습니다.

에디터 부분은 [별도의 리포지토리](https://github.com/litagin02/Style-Bert-VITS2-Editor)에 분리되어 있습니다.

버전 2.2 이전의 음성 합성 WebUI는 `App.bat`을 더블 클릭하거나 `python app.py` 명령어로 WebUI를 실행합니다. 또는 `Inference.bat`으로 음성 합성 단독 탭을 열 수 있습니다.

음성 합성에 필요한 모델 파일의 구조는 다음과 같습니다 (수동으로 배치할 필요는 없습니다).

```
model_assets
├── your_model
│   ├── config.json
│   ├── your_model_file1.safetensors
│   ├── your_model_file2.safetensors
│   ├── ...
│   └── style_vectors.npy
└── another_model
    ├── ...
```

이와 같이, 추론에는 `config.json`, `*.safetensors`, `style_vectors.npy`가 필요합니다. 모델을 공유할 때는 이 세 가지 파일을 함께 공유하세요.

이 중 `style_vectors.npy`는 스타일을 제어하는 데 필요한 파일로, 학습 시 기본으로 평균 스타일 "Neutral"이 생성됩니다. 여러 스타일을 사용하여 더 자세히 제어하고 싶은 경우 "스타일 생성"을 참조하세요 (평균 스타일만으로도 학습 데이터가 감정이 풍부하다면 충분히 감정이 풍부한 음성을 생성할 수 있습니다).

### 학습

- CLI에서 학습하는 방법은 [여기](docs/CLI.md)를 참조하세요.
- paperspace에서 학습하는 방법은 [여기](docs/paperspace.md), colab에서 학습하는 방법은 [여기](http://colab.research.google.com/github/litagin02/Style-Bert-VITS2/blob/master/colab.ipynb)를 참조하세요.

학습에는 2-14초 정도의 여러 음성 파일과 그에 대한 텍스트 데이터가 필요합니다.

- 기존 코퍼스 등에 이미 분할된 음성 파일과 텍스트 데이터가 있는 경우 그대로 (필요시 텍스트 파일을 수정하여) 사용할 수 있습니다. 아래의 "학습 WebUI"를 참조하세요.
- 그렇지 않은 경우, (길이는 상관없이) 음성 파일만 있으면, 학습에 바로 사용할 수 있는 데이터셋을 만들기 위한 도구가 포함되어 있습니다.

#### 데이터셋 만들기

- `App.bat`을 더블 클릭하거나 `python app.py` 명령어로 실행한 후 "데이터셋 생성" 탭에서 음성 파일을 적절한 길이로 자르고, 그 후 텍스트 자동 작성이 가능합니다. 또는 `Dataset.bat`을 더블 클릭하여 단독 탭을 열 수 있습니다.
- 지시에 따라 생성한 후, 아래의 "학습" 탭에서 학습을 진행할 수 있습니다.

#### 학습 WebUI

- `App.bat`을 더블 클릭하거나 `python app.py` 명령어로 실행한 WebUI의 "학습" 탭에서 지시에 따라 학습을 진행하세요. 또는 `Train.bat`을 더블 클릭하여 단독 탭을 열 수 있습니다.

### 스타일 생성

- 기본적으로, 기본 스타일 "Neutral" 외에 학습 폴더의 분류에 따라 스타일이 생성됩니다.
- 그 외의 방법으로 수동으로 스타일을 생성하고 싶은 분들을 위한 안내입니다.
- `App.bat`을 더블 클릭하거나 `python app.py` 명령어로 실행한 WebUI의 "스타일 생성" 탭에서 음성 파일을 사용하여 스타일을 생성할 수 있습니다. 또는 `StyleVectors.bat`을 더블 클릭하여 단독 탭을 열 수 있습니다.
- 학습과 독립적으로 수행되므로, 학습 중에도 가능하며, 학습이 끝난 후에도 여러 번 다시 시도할 수 있습니다 (전처리가 완료되어 있어야 합니다).
  
### API 서버

구축된 환경에서 `python server_fastapi.py`를 실행하면 API 서버가 시작됩니다.
API 사양은 시작 후 `/docs`에서 확인할 수 있습니다.

- 입력 문자 수는 기본적으로 100자가 최대입니다. 이는 `config.yml`의 `server.limit`에서 변경할 수 있습니다.
- 기본 설정에서는 CORS가 모든 도메인에서 허용됩니다. 가능한 한 `config.yml`의 `server.origins` 값을 변경하여 신뢰할 수 있는 도메인으로 제한하십시오(키를 삭제하면 CORS 설정이 비활성화됩니다).

또한, 음성 합성 에디터의 API 서버는 `python server_editor.py`로 시작할 수 있습니다. 하지만 아직 완전히 정비되지 않았습니다. [에디터 리포지토리](https://github.com/litagin02/Style-Bert-VITS2-Editor)에서 필요한 최소한의 API만 현재 구현되어 있습니다.

음성 합성 에디터의 웹 배포에 대해서는 [이 Dockerfile](Dockerfile.deploy)을 참조하십시오.

### 병합

두 모델을 "음질", "음높이", "감정 표현", "템포"의 4가지 측면에서 혼합하여 새로운 모델을 만들거나, 특정 모델에 다른 두 모델의 차이를 추가하는 등의 작업이 가능합니다.
`App.bat`을 더블 클릭하거나 `python app.py`를 실행하여 열리는 WebUI의 "병합" 탭에서 두 모델을 선택하여 병합할 수 있습니다. 또는 `Merge.bat`을 더블 클릭하여 단독 탭을 열 수 있습니다.

### 자연성 평가

학습 결과 중 어느 스텝이 좋은지에 대한 "하나의" 지표로, [SpeechMOS](https://github.com/tarepan/SpeechMOS)를 사용하는 스크립트를 제공합니다:
```bash
python speech_mos.py -m <model_name>
```
스텝별 자연성 평가가 표시되며, 결과는 `mos_results` 폴더의 `mos_{model_name}.csv`와 `mos_{model_name}.png`에 저장됩니다. 읽어들이고 싶은 문장을 변경하려면 내부 파일을 수정하여 각자 조정할 수 있습니다. 다만 이는 어디까지나 악센트, 감정 표현, 억양을 전혀 고려하지 않은 기준에 따른 평가이므로, 실제로 읽어보게 해서 선별하는 것이 가장 좋습니다.

## Bert-VITS2와의 관계

기본적으로 Bert-VITS2의 모델 구조를 약간 수정한 것에 불과합니다. [이전 사전 학습 모델](https://huggingface.co/litagin/Style-Bert-VITS2-1.0-base)과 [JP-Extra 사전 학습 모델](https://huggingface.co/litagin/Style-Bert-VITS2-2.0-base-JP-Extra)도 사실상 Bert-VITS2 v2.1 또는 JP-Extra와 동일한 것을 사용하고 있습니다(불필요한 가중치를 제거하고 safetensors로 변환한 것).

구체적으로는 다음과 같은 점이 다릅니다.

- [EasyBertVits2](https://github.com/Zuntan03/EasyBertVits2)처럼, Python이나 Git을 모르는 사람도 쉽게 사용할 수 있습니다.
- 감정 임베딩 모델을 256차원의 [wespeaker-voxceleb-resnet34-LM](https://huggingface.co/pyannote/wespeaker-voxceleb-resnet34-LM)으로 변경(감정 임베딩보다는 화자 식별을 위한 임베딩).
- 감정 임베딩에서 벡터 양자화를 제거하고 단순한 완전 연결층으로 변경.
- `style_vectors.npy` 스타일 벡터 파일을 생성하여, 해당 스타일을 사용해 효과의 강도를 연속적으로 지정하면서 음성을 생성할 수 있습니다.
- 다양한 WebUI를 제작.
- bf16 학습 지원.
- safetensors 형식 지원, 기본적으로 safetensors 사용.
- 기타 경미한 버그 수정 및 리팩토링.

## References
In addition to the original reference (written below), I used the following repositories:
- [Bert-VITS2](https://github.com/fishaudio/Bert-VITS2)
- [EasyBertVits2](https://github.com/Zuntan03/EasyBertVits2)

[The pretrained model](https://huggingface.co/litagin/Style-Bert-VITS2-1.0-base) and [JP-Extra version](https://huggingface.co/litagin/Style-Bert-VITS2-2.0-base-JP-Extra) is essentially taken from [the original base model of Bert-VITS2 v2.1](https://huggingface.co/Garydesu/bert-vits2_base_model-2.1) and [JP-Extra pretrained model of Bert-VITS2](https://huggingface.co/Stardust-minus/Bert-VITS2-Japanese-Extra), so all the credits go to the original author ([Fish Audio](https://github.com/fishaudio)):


In addition, [text/user_dict/](text/user_dict) module is based on the following repositories:
- [voicevox_engine](https://github.com/VOICEVOX/voicevox_engine)
and the license of this module is LGPL v3.

## LICENSE

This repository is licensed under the GNU Affero General Public License v3.0, the same as the original Bert-VITS2 repository. For more details, see [LICENSE](LICENSE).

In addition, [text/user_dict/](text/user_dict) module is licensed under the GNU Lesser General Public License v3.0, inherited from the original VOICEVOX engine repository. For more details, see [LGPL_LICENSE](LGPL_LICENSE).



Below is the original README.md.
---

<div align="center">

<img alt="LOGO" src="https://cdn.jsdelivr.net/gh/fishaudio/fish-diffusion@main/images/logo_512x512.png" width="256" height="256" />

# Bert-VITS2

VITS2 Backbone with multilingual bert

For quick guide, please refer to `webui_preprocess.py`.

简易教程请参见 `webui_preprocess.py`。

## 请注意，本项目核心思路来源于[anyvoiceai/MassTTS](https://github.com/anyvoiceai/MassTTS) 一个非常好的tts项目
## MassTTS的演示demo为[ai版峰哥锐评峰哥本人,并找回了在金三角失落的腰子](https://www.bilibili.com/video/BV1w24y1c7z9)

[//]: # (## 本项目与[PlayVoice/vits_chinese]&#40;https://github.com/PlayVoice/vits_chinese&#41; 没有任何关系)

[//]: # ()
[//]: # (本仓库来源于之前朋友分享了ai峰哥的视频，本人被其中的效果惊艳，在自己尝试MassTTS以后发现fs在音质方面与vits有一定差距，并且training的pipeline比vits更复杂，因此按照其思路将bert)

## 成熟的旅行者/开拓者/舰长/博士/sensei/猎魔人/喵喵露/V应当参阅代码自己学习如何训练。

### 严禁将此项目用于一切违反《中华人民共和国宪法》，《中华人民共和国刑法》，《中华人民共和国治安管理处罚法》和《中华人民共和国民法典》之用途。
### 严禁用于任何政治相关用途。
#### Video:https://www.bilibili.com/video/BV1hp4y1K78E
#### Demo:https://www.bilibili.com/video/BV1TF411k78w
#### QQ Group：815818430
## References
+ [anyvoiceai/MassTTS](https://github.com/anyvoiceai/MassTTS)
+ [jaywalnut310/vits](https://github.com/jaywalnut310/vits)
+ [p0p4k/vits2_pytorch](https://github.com/p0p4k/vits2_pytorch)
+ [svc-develop-team/so-vits-svc](https://github.com/svc-develop-team/so-vits-svc)
+ [PaddlePaddle/PaddleSpeech](https://github.com/PaddlePaddle/PaddleSpeech)
+ [emotional-vits](https://github.com/innnky/emotional-vits)
+ [fish-speech](https://github.com/fishaudio/fish-speech)
+ [Bert-VITS2-UI](https://github.com/jiangyuxiaoxiao/Bert-VITS2-UI)
## 感谢所有贡献者作出的努力
<a href="https://github.com/fishaudio/Bert-VITS2/graphs/contributors" target="_blank">
  <img src="https://contrib.rocks/image?repo=fishaudio/Bert-VITS2"/>
</a>

[//]: # (# 本项目所有代码引用均已写明，bert部分代码思路来源于[AI峰哥]&#40;https://www.bilibili.com/video/BV1w24y1c7z9&#41;，与[vits_chinese]&#40;https://github.com/PlayVoice/vits_chinese&#41;无任何关系。欢迎各位查阅代码。同时，我们也对该开发者的[碰瓷，乃至开盒开发者的行为]&#40;https://www.bilibili.com/read/cv27101514/&#41;表示强烈谴责。)

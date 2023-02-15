# Applied Natural Language Processing in the Enterprise

이것은 Ankur A. Patel 및 Ajay Uppili Arasanipalai의 O'Reilly Media 출판물인 _Applied Natural Language Processing in the Enterprise_의 저장소입니다. 여기에서 학습자의 편의를 위해 여기 게시된 GitHub에 책의 모든 소스 코드를 찾을 수 있습니다.

환경 설정 및 예제 코드 실행을 시작하려면 아래 단계를 따르십시오.

## Setup

필요한 모든 라이브러리 및 의존성을 설치하기 위하여 다음 명령을 실행하십시오:

```
pip install nlpbook
```

그러나 추천하는 접근 방식은 의존성 충돌을 자동으로 처리하는 플랫폼 간 언어 독립적 패키지 관리자인 'conda'를 사용하는 것입니다.

아직 설치하지 않은 경우 OS에 따라 [Python 3.8의 Miniforge 배포판](https://github.com/conda-forge/miniforge#download)을 설치합니다. Windows를 사용하는 경우 Miniforge 배포판 대신 [Python 3.8의 Anaconda 배포판](https://www.anaconda.com/products/individual)을 선택할 수 있습니다.

'conda'가 설치되면 다음 명령을 실행합니다.:

```
conda install -c nlpbook nlpbook
```

또는 이 책의 환경을 시스템의 나머지 부분과 격리된 상태로 유지하려면(적극 권장) 다음 명령을 실행하십시오.

```
conda create -n nlpbook
conda activate nlpbook
conda install -c nlpbook nlpbook
```

그런 다음 환경으로 돌아가고 싶을 때마다 'conda activate nlpbook'을 실행하십시오. 환경을 종료하려면 'conda deactivate'를 실행하십시오.

다음으로 spaCy 모델을 설치합니다.

```
python -m spacy download en_core_web_sm
python -m spacy download en_core_web_lg
python -m spacy download en_core_web_trf
```

## 환경 직접 설치하기

이 책의 코드를 빠르게 시작하고 실행하기 위한 환경 설정에 관심이 있다면 이 저장소의 루트에서 다음 명령을 실행하십시오.(저장소를 먼저 설정하는 방법은 아래의 "코드 가져오기" 섹션을 참조하세요.).

```
conda env create --file environment.yml
conda activate nlpbook
```
'pip'를 통해 모든 의존성을 가져올 수도 있습니다.:

```
pip install -r requirements.txt
``` 

## 코드 받기

공개적으로 발표된 모든 코드는 이 저장소에 있습니다. 시작하는 가장 간단한 방법은 Git을 사용하는 것입니다.:

```
git clone https://github.com/bupark82/nlpbook.git
```

Windows 또는 아직 'git'이 설치되지 않은 다른 플랫폼을 사용 중인 경우 [Git 클라이언트](https://git-scm.com/downloads)를 가져와야 할 수 있습니다.

## 데이터 받기

다음으로 AWS S3에서 데이터를 다운로드합니다(데이터 파일이 너무 커서 Github에 저장하고 액세스할 수 없음).

```
aws s3 cp s3://applied-nlp-book/data/ data --recursive --no-sign-request
aws s3 cp s3://applied-nlp-book/models/ag_dataset/ models/ag_dataset --recursive --no-sign-request
```

## 이 저장소에 구성된 구조

이 책의 각 장에는 이 프로젝트 저장소의 루트에 해당 노트북이 있습니다. XX장의 이름은 'chXX.ipynb'입니다. 부록의 이름은 'apXX.ipynb'입니다.
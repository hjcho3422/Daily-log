# 25.04.27
1. 주말에 진행한 내용
    1. SNC-API 다운로드 및 빌드
        - SNC-API 자체가 오래전에 개발된 내용이라 우분투 18.04 도커를 활용하여 빌드 하였음
        - pybind 사용을 위해 python-3.10을 사용하여 build 함
        - test 결과 큰 이상이 없는 것 같음
    2. cnnx2snc
        -


# 24.11.01
1. 주말에 해야 할 일
   1. ONNX Runtime 실행해 보자 (Pytorch → ONNX Model 변환 및 내부 구조 확인)
      - Pytorch와 ONNX Model 내부 구조 비교해 보자
2. 기타 자료
    1. The Deep Learning Compiler: A Comprehensive Survey (https://arxiv.org/pdf/2002.03794)
    2. A survey on large language model (LLM) security and privacy: The Good, The Bad, and The Ugly
    3. FLOPs란? 딥러닝 연산량에 대해서... (https://kimbg.tistory.com/26)

# 24.10.07
1. Qualcomm AI 3종 세트 (https://www.qualcomm.com/developer/artificial-intelligence#overview)
   1. Qualcomm® Neural Processing SDK
   2. Qualcomm® AI Engine Direct SDK
   3. AI Model Efficiency Toolkit (AIMET)

2. Neural Processing SDK와 AI Engine Direct SDK 차이점은 무엇일까?

# 24.10.06
1. aimet 실습
    1. aimet build 방법
    - python3.11 이상에서 build 수행 함 (3.10은 실패, 3.12까지 해봄)
    - 필요 라이브러리 설치

    ```
    sudo apt-get install ccache libjasper-dev libopenblas-dev libatlas-base-dev python3-pybind11

    sudo apt-get install liblapacke-dev

    python3 -m pip install torch torchvision torchaudio
    ```

    - numpy.disutils 호환성을 위해 numpy 다운그레이드 버전 설치
    ```
    pip uninstall numpy
    pip install numpy==1.22.4
    ```

    - numpy version 확인 & numpy.disutils 확인 & torch version 확인
    ```
    python -c "import numpy; print(numpy.__version__)"

    python -c "from numpy import distutils; print(distutils.__file__)"

    python -c "import torch; print(torch.__version__)"
    ```

    - log file을 남기면서 cmake 수행
    ```
    cmake .. 2>&1 | tee cmake_log_$(date +"%Y%m%d_%H%M%S").txt
    ```

    2. aimet example 실행 방법

2. 정리 필요함

### Tip
1. jupyter notebook kernel 설치 및 등록
    ```
    pip install jupyter ipykernel

    python -m ipykernel install --user --name=aimet_env --display-name="AIMET Environment"
    ```
2. PYTHONPATH 설정 (이 부분은 언제 필요한지 모르겠음) & 확인
    ```
    export PYTHONPATH=$PYTHONPATH:/home/test/projects/aimet/build/artifacts:/home/test/projects/aimet/TrainingExtensions/common/src/python:/home/test/projects/aimet/TrainingExtensions/torch/src/python

    import os
    print(os.environ.get('PYTHONPATH'))
    ```

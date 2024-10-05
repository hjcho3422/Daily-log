# 24.10.06
### 정리해야 할 것
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

2. 

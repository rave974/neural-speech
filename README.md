```
description: 
    working instructions for tts/asr repos
    and for installing in virtual environments

requirements (do not apply if individual requirments are provided):
    ubuntu 18.04.5 lts 
    python 3.6.9
    python3-pip
    cuda+cudnn (detailed instructions)

instructions:
    for terminal:
        sudo apt update  
        sudo apt upgrade
        sudo apt install nvidia-driver-460
    to make and activate virtual environment:
        python3 -m venv <name>
        cd <name>
        source bin/activate
        easy_install -U pip
        pip install -U pip setuptools
```

```
tts
detail:
    neural tts uses encoder and vocoder. 
    encoder makes spectrogram from text and the vocoder makes audio from spectrogram
    both encoder and vocoder require it's own trained model to work 

encoder:
    tacotron2
        github.com/nvidia/tacotron2 (includes waveglow vocoder)
        -
        (make and activate tacotron2 virtual env.)
        git clone --recursive https://www.github.com/nvidia/tacotron2
        cd tacotron2
        -
        (in requirements.txt, delete numpy==1.13.3 and tensorboard==1.15.0)
        pip install torch==1.4.0 torchvision==0.5.0
        pip install -r req* numpy==1.16 numba==0.48 tensorboard==2.5.0

```

```
asr
```

```
extra
```
    

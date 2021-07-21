```
description: 
working instructions for tts/asr repos
and for installing in virtual environments

requirements (may vary):
ubuntu 18.04.5 lts 
python 3.6.9
python3-pip
cuda+cudnn (detailed instructions)

instructions for terminal:
sudo apt update  
sudo apt upgrade
sudo apt install nvidia-driver-460
```

```
tts
detail:
    neural tts uses encoder and vocoder. 
    encoder makes spectrogram from text and the vocoder makes audio from spectrogram
    both encoder and vocoder require it's own trained model to work 

encoder:

tacotron2 - github.com/nvidia/tacotron2 (includes waveglow vocoder)
    python3 -m venv tacotron2
    cd tacotron2
    source bin/activate
    easy_install -U pip
    pip install -U pip setuptools
    -
    git clone --recursive https://www.github.com/nvidia/tacotron2
    cd tacotron2
    pip install torch==1.4.0 torchvision==0.5.0
    nano req*
    (replace numpy==1.13.3 with numpy==1.16)
    pip install -r req* numba==0.48



```

```
asr
```

```
extra
```
    

```
description: working instructions for tts/asr repos

requirements (might vary):
ubuntu 18.04.5 lts 
python 3.6
python3-pip
cuda+cudnn (detailed instructions)

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

encoder
    tacotron2 - github.com/nvidia/tacotron2 (includes waveglow vocoder)
        git clone --recursive https://www.github.com/nvidia/tacotron2
```

```
asr
```

```
extra
```
    

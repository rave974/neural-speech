
complete instructions for tts/asr repos  
[donate](test)

**content**
- tts
  * melspec generators
    * tacotron2 (nvidia)
  * vocoders
    * end to end  
    * seq to seq  
- asr  

**first time set-up (ubuntu 18.04.5 lts)**  
```
sudo apt update;sudo apt upgrade -y  
sudo apt install wget git python3 python3-pip python3-venv nvidia-driver-460 -y
# (cuda+cudnn)
```


**how to make v. env**
```
# (replace name with your project name)
mkdir name
python3.6 -m venv name/env  
source name/env/bin/activate 
pip install -U pip setuptools wheel  
cd name
```

**tacotron2 (nvidia)**  
[source](https://github.com/nvidia/tacotron2)
```
# (make v. env)
pip install torch==1.4.0 torchvision==0.5.0 #cuda 10.1 (update 2)
export CUDA_HOME=/usr/local/cuda #if apex setup gives error
git clone https://github.com/NVIDIA/apex
pip install --global-option="--cpp_ext" --global-option="--cuda_ext" ./apex
git clone https://www.github.com/nvidia/tacotron2
cd tacotron2
git submodule init; git submodule update
# (in requirements.txt delete numpy==1.13.3)
pip install numpy==1.16 numba==0.48 tensorboard==2.5.0 jupyter
pip install -r req*

```  
inference
```
# (download waveglow and tacotron checkpoints)  
# (write in terminal: "jupyter notebook" and navigate to "inference.ipynb")  
# (adjust checkpoint paths and run)
```
train
> prepare dataset and filelists
```
wget https://data.keithito.com/data/speech/LJSpeech-1.1.tar.bz2 (inside tacotron2 git cloned folder)   
tar -xvf *.tar.bz2  
sed -i -- 's,DUMMY,LJSpeech-1.1/wavs,g' filelists/*.txt 
```
> train single gpu if you have 1 gpu
```
python train.py --output_directory=outdir --log_directory=logdir --hparams=fp16_run=True,batch_size=1
```

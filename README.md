
complete instructions for tts/asr repos  

**first time set-up**  
&emsp;&emsp;ubuntu 18.04.5 lts  
&emsp;&emsp;&emsp;&emsp;sudo apt update;sudo apt upgrade -y  
&emsp;&emsp;&emsp;&emsp;sudo apt install wget git python3 python3-pip python3-venv nvidia-driver-460 -y  
&emsp;&emsp;&emsp;&emsp;cuda+cudnn

**how to make v. env**   
&emsp;&emsp;mkdir &lt;name&gt;  
&emsp;&emsp;python3.6 -m venv &lt;name&gt;/env  
&emsp;&emsp;source &lt;name&gt;/env/bin/activate  
&emsp;&emsp;pip install -U pip setuptools  
&emsp;&emsp;cd &lt;name&gt;

**index**
- [encoders](#encoders)
   * [tacotron2](#tacotron2-(nvidia))
- [vocoders](#vocoders)

## encoders
### tacotron2 ([nvidia](https://github.com/nvidia/tacotron2))
&emsp;&emsp;(make v. env)  
&emsp;&emsp;pip install torch==1.4.0 torchvision==0.5.0 #cuda 10.1  
&emsp;&emsp;git clone https://github.com/NVIDIA/apex  
&emsp;&emsp;pip install --global-option="--cpp_ext" --global-option="--cuda_ext" ./apex  
&emsp;&emsp;git clone https://www.github.com/nvidia/tacotron2  
&emsp;&emsp;cd tacotron2  
&emsp;&emsp;git submodule init; git submodule update  
&emsp;&emsp;(in requirements.txt delete numpy==1.13.3)  
&emsp;&emsp;pip install numpy==1.16 numba==0.48 tensorboard==2.5.0 -r req* jupyter  
&emsp;&emsp;inference  
&emsp;&emsp;&emsp;&emsp;(download waveglow and tacotron checkpoints)  
&emsp;&emsp;&emsp;&emsp;(write in terminal: "jupyter notebook" and navigate to "inference.ipynb")  
&emsp;&emsp;&emsp;&emsp;(adjust checkpoint paths and run)  
&emsp;&emsp;train    
&emsp;&emsp;&emsp;&emsp;wget https://data.keithito.com/data/speech/LJSpeech-1.1.tar.bz2 (inside tacotron2 git cloned folder)   
&emsp;&emsp;&emsp;&emsp;tar -xvf *.tar.bz2  
&emsp;&emsp;&emsp;&emsp;sed -i -- 's,DUMMY,LJSpeech-1.1/wavs,g' filelists/*.txt  
&emsp;&emsp;&emsp;&emsp;python train.py --output_directory=outdir --log_directory=logdir --hparams=fp16_run=True,batch_size=1

## vocoders

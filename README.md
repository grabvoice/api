This is a reimplementaion of the neural vocoder in [DIFFWAVE: A VERSATILE DIFFUSION MODEL FOR AUDIO SYNTHESIS](https://arxiv.org/pdf/2009.09761.pdf).

## Usage: 

- To continue training the model, run ```python distributed_train.py -c config_${channel}.json```, where ```${channel}``` can be either ```64``` or ```128```. 

- To retrain the model, change the parameter ```ckpt_iter``` in the corresponding ```json``` file to ```-1``` and use the above command.

- To generate audio, run ```python inference.py -c config_${channel}.json -cond ${conditioner_name}```. For example, if the name of the mel spectrogram is ```LJ001-0001.wav.pt```, then ```${conditioner_name}``` is ```LJ001-0001```. Provided mel spectrograms include ```LJ001-0001``` through ```LJ001-0186```.


- Note, you may need to carefully adjust some parameters in the ```json``` file, such as ```data_path``` and ```batch_size_per_gpu```.

## Pretrained models and generated samples:
- [channel=64 model](https://github.com/philsyn/DiffWave-Vocoder/tree/master/exp/ch64_T50_betaT0.05/logs/checkpoint)
- [channel=64 samples](https://github.com/philsyn/DiffWave-Vocoder/tree/master/exp/ch64_T50_betaT0.05/speeches)
- [channel=128 model](https://github.com/philsyn/DiffWave-Vocoder/tree/master/exp/ch128_T200_betaT0.02/logs/checkpoint)
- [channel=128 samples](https://github.com/philsyn/DiffWave-Vocoder/tree/master/exp/ch128_T200_betaT0.02/speeches)

login into the GPU:
ssh xiao@phoneticsrv3.lcs.tcd.ie

xiao4074

ssh xiao@134.226.88.174


DiffWave-Vocoder
git clone https://github.com/philsyn/DiffWave-Vocoder.git

python inference.py -c config_64.json -cond LJ001-0001


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
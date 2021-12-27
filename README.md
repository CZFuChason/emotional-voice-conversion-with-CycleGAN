# Emotional Voice Conversion by using CycleGAN

Dependencies
-------

  `Python 3.5`

  `Numpy 1.14`

  `Tensorflow 1.8`

  `ProgressBar2 3.37.1`

  `LibROSA 0.6`

  `FFmpeg 4.0`

  `PyWorld`

  `sklearn`

  `pycwt`

  `sprocket-vc`

 ` scipy`

  `glob`

Usage
---------

1. `train.py`

This script is to train CycleGAN with spectrum features.

2. `train_f0.py`

This script is to perform CWT on F0, then train CycleGAN with CWT-F0 features.

3. `convert_separate.py`

This script is to convert speech from the source using trained CycleGAN to convert spectrum and CWT-F0 features separately.


# Instruction

1. **To train CycleGAN with spectrum features, please run the code:**</br>
```Bash
$ python train.py  --num_f 128 \
                --train_A_dir './data/neutral/'  \
                --train_B_dir './data/target/' \
                --model_dir './model/' --model_name 'model.ckpt' --random_seed 0  \
                --validation_A_dir './data/test_neutral/' --validation_B_dir './data/test_target/' \
                --output_dir './validated/' --tensorboard_log_dir './log/' 
```

2. **To train CycleGAN with CWT-F0 features, please run the code:** 
```Bash
$ python train_f0.py
                --train_A_dir './data/neutral/'  \
                --train_B_dir './data/target/' \
                --model_dir './model/' --model_name 'model.ckpt' --random_seed 0  \
                --validation_A_dir './data/test_neutral/' --validation_B_dir './data/test_target/' \
                --output_dir './validated/' --tensorboard_log_dir './log/' 
```


The codes are based on CycleGAN Voice Conversion: https://github.com/leimao/Voice_Converter_CycleGAN


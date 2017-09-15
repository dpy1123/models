
如果有module not found error，每次新开启terminal都要export一下
```
# From tensorflow/models/
export PYTHONPATH=$PYTHONPATH:`pwd`:`pwd`/slim
```


train face-detect-model
```
# from tf_models
python3 object_detection/train.py \
     --logtostderr \
     --pipeline_config_path=./object_detection/dd/models/ssd/ssd_mobilenet_v1.config \
     --train_dir=./object_detection/dd/models/ssd/train
```

eval
```
# From the tensorflow/models/ directory
python3 object_detection/eval.py \
    --logtostderr \
    --pipeline_config_path=./object_detection/dd/models/ssd/ssd_mobilenet_v1.config \
    --checkpoint_dir=./object_detection/dd/models/ssd/train \
    --eval_dir=./object_detection/dd/models/ssd/eval
```

```
tensorboard --logdir=./object_detection/dd/models/ssd/train
```
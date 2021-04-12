本项目用于将HuggingFace提供的Roberta的Torch版本的模型转化为Tensorflow1.X版本的ckpt格式。

- roberta_config.json: Roberta模型信息在这里，本项目中为base版本参数，large版本的参数可参考HuggingFace中的模型信息
- requiments.txt: 必要的第三方模块信息，其中tensorflow版本为1.14.0

### 使用方法

本项目演示Roberta base版本模型的转化，操作步骤如下：

- 将HuggingFace中的Roberta base版本的Torch模型`roberta-base`下载好放在当前目录
- 运行`convert_pytorch_checkpoint_to_tf.py`脚本，生成的Tensorflow1.X版本的ckpt格式的模型文件夹为`tf-roberta-base`

### 目录结构

```
.
├── convert_pytorch_checkpoint_to_tf.py
├── modeling.py
├── requirements.txt
├── roberta-base
│   ├── config.json
│   ├── dict.txt
│   ├── merges.txt
│   ├── pytorch_model.bin
│   ├── README.md
│   ├── tokenizer.json
│   └── vocab.json
├── roberta_config.json
└── tf-roberta-base
    ├── checkpoint
    ├── roberta_base.ckpt.data-00000-of-00001
    ├── roberta_base.ckpt.index
    └── roberta_base.ckpt.meta

3 directories, 16 files
```

### 参考文献

1. Transfering RoBERTa checkpoint to Tensorflow: [https://github.com/vickyzayats/roberta_tf_ckpt](https://github.com/vickyzayats/roberta_tf_ckpt)

`注意`: 本项目是roberta_tf_ckpt的改进版，修改信息如下：

1. 增加requiments.txt，提供Python运行环境；
2. 原项目为roberta large版本，本项目为roberta base版本；
3. 更加详细的操作说明以及文档示例
4. 修改了原有脚本`convert_pytorch_checkpoint_to_tf.py`的bug，同时避免传参运行，设置默认值直接运行


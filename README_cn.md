# MiniCPM
[英文版](https://github.com/OpenBMB/LLMFarm-MiniCPM/blob/main/README.md)

代码基于[LLMFarm](https://github.com/guinmoon/LLMFarm). 需要注意的是，运行在ios上的是量化后的模型，可能会有一些精度损失。

# ios上部署[MiniCPM](https://github.com/OpenBMB/MiniCPM)说明
第一种直接下载我们转换好的[模型](https://openbmb.oss-cn-hongkong.aliyuncs.com/model_center/mobile/ios/MiniCPM/minicpm-q4_1.gguf)，可以跳过后面模型转换和量化

第二种从huggingface上下载原始模型，并按下面步骤进行转换和量化。

## 下载hf模型
## 模型格式转换和量化
1. git clone https://github.com/OpenBMB/llama.cpp.git
2. cd llama.cpp && make -j8
3. python3 convert.py ${hf_model_dir} --vocab-type hfft --outtype f32
4. ./quantize ${hf_model_dir}/ggml-model-f32.gguf ${output_dir}/minicpm-q4_1.gguf q4_1
   

## 编译安装
1. 用xcode打开当前目录
2. 配置开发者账号
3. 设备选择mac或者手机
4. 编译安装
<img width="1365" alt="image" src="https://github.com/OpenBMB/LLMFarm-MiniCPM/assets/24504497/b44cfaf5-64c6-4eb1-a0e9-aaaa9d24cacc">


## 开始对话
1. add chat："select model" 选择量化后的模型
2. Settings template: 选择CPM
3. save后开始对话

<img width="897" alt="image" src="https://github.com/OpenBMB/LLMFarm-MiniCPM/assets/24504497/46ace145-c35f-44f9-ad67-91ab84ee401e">
<img width="395" alt="image" src="https://github.com/OpenBMB/LLMFarm-MiniCPM/assets/24504497/d1a6bc6b-4497-4eda-8980-f3101dc92a01">
<img width="893" alt="image" src="https://github.com/OpenBMB/LLMFarm-MiniCPM/assets/24504497/51e4de49-ed3f-4d76-86d3-12a9cf805dc6">


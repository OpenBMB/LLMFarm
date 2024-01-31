#ios上部署[MiniCPM](https://github.com/OpenBMB/MiniCPM)说明

## 下载hf模型
## 模型格式转换和量化
1. git clone https://github.com/zkh2016/llama.cpp.git
2. make -j8
3. python3 convert.py ${hf_model_dir} --vocab-type hfft --outtype f32
4. ./quantize ${hf_model_dir}/ggml-model-f32.gguf ${output_dir}/minicpm-q4_1.gguf q4_1

## 编译安装
1. 用xcode打开当前目录
2. 配置开发者账号
3. 设备选择mac或者手机
4. 编译安装

## 测试
1. add chat："select model" 选择量化后的模型
2. Settings template: 选择CPM
3. save后开始对话


# MiniCPM
[中文版](https://github.com/OpenBMB/LLMFarm-MiniCPM/blob/main/README_cn.md)

Based on [LLMFarm](https://github.com/guinmoon/LLMFarm), we run MiniCPM on ios devices.
Note that the models run on ios are quantized to 4-bit and may lose some performance. The original models can be found [here](https://github.com/OpenBMB/miniCPM).

# Deploy [MiniCPM](https://github.com/OpenBMB/MiniCPM) on IOS
The first method is to directly download our converted [model](https://openbmb.oss-cn-hongkong.aliyuncs.com/model_center/mobile/ios/MiniCPM/minicpm-q4_1.gguf)，You can skip the subsequent conversion steps.

The second method is to download the original model from the huggingface and follow the steps below to convert and quantify it.

## convert model
1. downloading model
1. git clone https://github.com/OpenBMB/llama.cpp.git
2. cd llama.cpp && make -j8
3. python3 convert.py ${hf_model_dir} --vocab-type hfft --outtype f32
4. ./quantize ${hf_model_dir}/ggml-model-f32.gguf ${output_dir}/minicpm-q4_1.gguf q4_1

## compile
1. Open this project with Xcode
2. Setting Siging & Capabilities
3. Select a device My MaC or your iphone
4. run
<img width="1365" alt="image" src="https://github.com/OpenBMB/LLMFarm-MiniCPM/assets/24504497/b44cfaf5-64c6-4eb1-a0e9-aaaa9d24cacc">


## chat
1. add chat
2. select a model
3. Set template: CPM
4. Start chat
<img width="897" alt="image" src="https://github.com/OpenBMB/LLMFarm-MiniCPM/assets/24504497/46ace145-c35f-44f9-ad67-91ab84ee401e">
<img width="395" alt="image" src="https://github.com/OpenBMB/LLMFarm-MiniCPM/assets/24504497/d1a6bc6b-4497-4eda-8980-f3101dc92a01">
<img width="893" alt="image" src="https://github.com/OpenBMB/LLMFarm-MiniCPM/assets/24504497/51e4de49-ed3f-4d76-86d3-12a9cf805dc6">


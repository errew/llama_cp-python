# llama_cp-ppython
自己编译备份


去年使用Comfyui的插件，遇到llama-cpp无法加载.gguf模型，当时放弃使用该插件。
现在又遇到一个关于Qwen-3的量化模型的插件，又是类似的加载问题。
找不到适配的llama-cpp文件的版本，不得以自己编译一个。

我的电脑是4080s、CUDA13.0、python3.12.10所以不保证这个文件适用所有的接近的环境。

G:\ComfyUI_windows_portable>.\python_embeded\python.exe -c "import llama_cpp; print(llama_cpp.llama_print_system_info())"
ggml_cuda_init: GGML_CUDA_FORCE_MMQ:    no
ggml_cuda_init: GGML_CUDA_FORCE_CUBLAS: no
ggml_cuda_init: found 1 CUDA devices:
  Device 0: NVIDIA GeForce RTX 4080 SUPER, compute capability 8.9, VMM: yes
b'CUDA : ARCHS = 890 | USE_GRAPHS = 1 | PEER_MAX_BATCH_SIZE = 128 | CPU : SSE3 = 1 | SSSE3 = 1 | AVX = 1 | AVX2 = 1 | F16C = 1 | FMA = 1 | LLAMAFILE = 1 | OPENMP = 1 | REPACK = 1 | '

其核心参数是 ARCHS = 890，未设置复杂的CMAKE_ARGS，可兼容NVIDIA 40系列显卡。
30系列显卡无法使用。
无法调用50系显卡特有的新特性，50系列要达到最优化需要重新编译。


纯当娱乐。




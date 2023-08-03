## 环境依赖配置
1. [Python3.10](https://www.python.org/downloads/) 安装时记得配置环境变量
2. [git](https://git-scm.com/download/win)  安装时记得配置环境变量
3. [cuda](https://developer.nvidia.com/cuda-toolkit-archive)

查看适用cuda版本：在cmd中输入
````cmd
nvidia-smi
````
4. 觉得下载慢可以开代理/VPN

## 换源
1. pip换源

经测试，此处使用阿里源，清华源有缺失。
````cmd
pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/
python -m pip install --upgrade pip
````

2. git使用代理

（加速下载，此步可以不做）[详见](https://zhuanlan.zhihu.com/p/625628413#:~:text=%E5%9C%A8%E7%BB%88%E7%AB%AF%E4%B8%AD%E8%BF%90%E8%A1%8C%E4%BB%A5%E4%B8%8B%E5%91%BD%E4%BB%A4%EF%BC%9A%20git%20config%20--global%20http.proxy%20http%3A%2F%2F%3C%E4%BB%A3%E7%90%86%E6%9C%8D%E5%8A%A1%E5%99%A8%3E%3A%3C%E4%BB%A3%E7%90%86%E7%AB%AF%E5%8F%A3%3E%20%E4%BE%8B%E5%A6%82%EF%BC%8C%E5%A6%82%E6%9E%9C%E4%BB%A3%E7%90%86%E6%9C%8D%E5%8A%A1%E5%99%A8%E4%B8%BA%20proxy.example.com,%EF%BC%8C%E7%AB%AF%E5%8F%A3%E4%B8%BA%208080%20%EF%BC%8C%E5%88%99%E5%91%BD%E4%BB%A4%E5%BA%94%E4%B8%BA%EF%BC%9A%20git%20config%20--global%20http.proxy%20http%3A%2F%2Fproxy.example.com%3A8080)


## stable diffusion webui安装
1. git clone项目文件
````cmd
% 此步为切换盘符，若想安装在C盘无需执行 %
cd D:
git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git
````
等待git clone结束即可，命令行别关，后面还有用😎。

2. 下载基础模型

以下任选一个
* [anything](https://huggingface.co/xyn-ai/anything-v4.0/blob/main/anything-v4.0.ckpt)
* [ChilloutMix](https://pan.baidu.com/s/1gwAj3j65BdahlVX43fsm2g?pwd=mbio)

3. 创建并开启环境
之前不关cmd是方便接下来操作
````cmd
cd stable-diffusion-webui
webui-user.bat
````
之后等执行结束，在浏览器中打开 [127.0.0.1:7860]()

## 启用xformers（可选）
用记事本编辑`stable-diffusion-webui`下的`webui-user.bat`
````cmd
@echo off

set PYTHON=
set GIT=
set VENV_DIR=
% 此处添加--xformers即可 %
set COMMANDLINE_ARGS=--xformers

call webui.bat
````

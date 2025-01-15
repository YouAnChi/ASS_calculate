# 文本相似度评估工具

## 项目概述
这是一个用于评估文本相似度的Python工具，主要用于比较Excel文件中两列文本的语义相似度。该工具使用了先进的ACGE文本嵌入模型来计算文本之间的相似度。

## 环境要求
- Python 3.9.6（必需）
- pip（Python包管理器）

## 依赖包说明
项目使用以下主要依赖包：
- sentence-transformers (2.2.2)：文本向量化核心库
- openpyxl (3.1.2)：Excel文件读写处理
- numpy (1.24.3)：数值计算和向量运算
- torch (>=2.0.0)：PyTorch深度学习框架
- transformers (>=4.30.0)：Hugging Face转换器库
- tqdm (>=4.65.0)：进度条显示
- scikit-learn (>=1.2.2)：科学计算工具

## 使用 pyenv 安装 Python 3.9.6（推荐方法）

### Windows 系统
1. 安装 pyenv-win
   ```bash
   # 使用 PowerShell 安装
   Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"
   ```

2. 安装 Python 3.9.6
   ```bash
   # 查看可用的 Python 版本
   pyenv install --list

   # 安装 Python 3.9.6
   pyenv install 3.9.6

   # 设置全局 Python 版本（可选）
   pyenv global 3.9.6
   ```

3. 创建虚拟环境
   ```bash
   # 进入项目目录
   cd 项目路径

   # 确保使用 Python 3.9.6
   pyenv local 3.9.6

   # 创建虚拟环境
   python -m venv venv

   # 激活虚拟环境
   .\venv\Scripts\activate
   ```

### macOS 系统
1. 安装 pyenv
   ```bash
   # 安装 Homebrew（如果没有）
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

   # 安装 pyenv
   brew install pyenv

   # 配置 shell 环境
   echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
   echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
   echo 'eval "$(pyenv init -)"' >> ~/.zshrc
   source ~/.zshrc
   ```

2. 安装 Python 3.9.6
   ```bash
   # 安装依赖（确保 Python 编译成功）
   brew install openssl readline sqlite3 xz zlib tcl-tk

   # 安装 Python 3.9.6
   pyenv install 3.9.6

   # 设置全局 Python 版本（可选）
   pyenv global 3.9.6
   ```

3. 创建虚拟环境
   ```bash
   # 进入项目目录
   cd 项目路径

   # 确保使用 Python 3.9.6
   pyenv local 3.9.6

   # 创建虚拟环境
   python -m venv venv

   # 激活虚拟环境
   source venv/bin/activate
   ```

### Linux 系统
1. 安装 pyenv
   ```bash
   # 安装依赖
   sudo apt-get update
   sudo apt-get install -y make build-essential libssl-dev zlib1g-dev \
   libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev \
   libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl

   # 安装 pyenv
   curl https://pyenv.run | bash

   # 配置 shell 环境
   echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
   echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
   echo 'eval "$(pyenv init -)"' >> ~/.bashrc
   source ~/.bashrc
   ```

2. 安装 Python 3.9.6
   ```bash
   # 安装 Python 3.9.6
   pyenv install 3.9.6

   # 设置全局 Python 版本（可选）
   pyenv global 3.9.6
   ```

3. 创建虚拟环境
   ```bash
   # 进入项目目录
   cd 项目路径

   # 确保使用 Python 3.9.6
   pyenv local 3.9.6

   # 创建虚拟环境
   python -m venv venv

   # 激活虚拟环境
   source venv/bin/activate
   ```

### 验证安装
完成安装后，验证 Python 版本：
```bash
# 确认 Python 版本
python --version  # 应显示 Python 3.9.6

# 确认 pip 可用
pip --version
```

## 详细安装步骤

### Windows系统安装步骤

1. 安装 Python 3.9.6
   - 访问 Python 官方下载页面：https://www.python.org/downloads/release/python-396/
   - 下载 Windows 安装程序 (64位: Windows x86-64 executable installer)
   - 运行安装程序，必须勾选"Add Python 3.9 to PATH"

2. 创建虚拟环境
   ```bash
   # 打开命令提示符（CMD）
   # 进入项目目录
   cd 项目路径

   # 安装虚拟环境工具
   pip install virtualenv

   # 创建Python 3.9.6的虚拟环境
   virtualenv venv --python=python3.9.6

   # 激活虚拟环境
   .\venv\Scripts\activate
   ```

3. 安装依赖
   ```bash
   # 使用国内镜像（推荐，速度更快）
   pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple

   # 或使用默认源
   pip install -r requirements.txt
   ```

### macOS系统安装步骤

1. 使用 pyenv 安装 Python 3.9.6
   ```bash
   # 安装 Homebrew（如果没有）
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

   # 安装 pyenv
   brew install pyenv

   # 安装 Python 3.9.6
   pyenv install 3.9.6

   # 设置本地 Python 版本
   pyenv local 3.9.6
   ```

2. 创建虚拟环境
   ```bash
   # 进入项目目录
   cd 项目路径

   # 创建虚拟环境
   python -m venv venv

   # 激活虚拟环境
   source venv/bin/activate
   ```

3. 安装依赖
   ```bash
   # 使用国内镜像（推荐，速度更快）
   pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple

   # 或使用默认源
   pip install -r requirements.txt
   ```

### Linux系统安装步骤

1. 安装 Python 3.9.6
   ```bash
   # Ubuntu/Debian
   sudo apt update
   sudo apt install software-properties-common
   sudo add-apt-repository ppa:deadsnakes/ppa
   sudo apt install python3.9.6

   # CentOS
   sudo yum install -y python39
   ```

2. 创建虚拟环境
   ```bash
   # 进入项目目录
   cd 项目路径

   # 创建虚拟环境
   python3.9 -m venv venv

   # 激活虚拟环境
   source venv/bin/activate
   ```

3. 安装依赖
   ```bash
   # 使用国内镜像（推荐，速度更快）
   pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple

   # 或使用默认源
   pip install -r requirements.txt
   ```

## 使用方法
1. 准备Excel文件，确保包含以下列：
   - 参考文本列（默认表头：'标注'）
   - 比较文本列（默认表头：'answer'）
   - 结果输出列（默认表头：'ASS'）

2. 配置参数：
   - 模型路径：指定ACGE文本嵌入模型的位置
   - Excel文件路径
   - 批处理大小（默认：50条/批）

## 常见问题解决

### 1. 依赖安装问题
- 如果安装依赖时出现错误，尝试以下解决方案：
  ```bash
  # 更新 pip
  python -m pip install --upgrade pip

  # 使用国内镜像源
  pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
  ```

### 2. 模型下载问题
- 如果模型下载速度慢，可以：
  1. 使用国内镜像
  2. 使用代理
  3. 联系我们获取离线模型包

### 3. 内存问题
- 如果处理大文件时内存不足：
  1. 减小批处理大小（batch_size）
  2. 关闭其他占用内存的程序
  3. 使用更小的数据集进行测试

### 4. Python版本问题
- 必须使用Python 3.9.6，其他版本可能导致兼容性问题
- 如果系统中有多个Python版本，确保使用正确的虚拟环境

## 代码结构说明
1. 时间格式转换函数：处理程序运行时间的显示
2. 文本相似度计算：使用ACGE模型计算文本相似度
3. Excel数据处理：读取和写入Excel文件数据
4. 批量处理模块：高效处理大量数据
5. 异常处理：确保程序稳定运行

## 性能优化建议
1. 使用SSD存储Excel文件
2. 适当调整batch_size大小
3. 确保足够的系统内存
4. 关闭不必要的后台程序

## 技术支持
如遇到问题，请：
1. 检查是否严格按照安装步骤操作
2. 查看是否使用了正确的Python版本
3. 确认所有依赖包是否正确安装
4. 检查Excel文件格式是否正确

## 更新日志
- 2025-01-15：初始版本发布
  - 支持文本相似度计算
  - 支持Excel文件批量处理
  - 添加详细安装文档

## 开发计划
1. 添加图形用户界面
2. 支持更多文件格式
3. 优化处理性能
4. 添加更多相似度算法

## 许可证
MIT License

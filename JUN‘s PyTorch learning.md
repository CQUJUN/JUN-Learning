# JUN‘s PyTorch learning

## 1.环境配置

### 1.1 Anaconda作用

#### 1. **包管理器**

Anaconda 内置了 `conda` 包管理器，能够轻松安装、更新、卸载和管理与数据科学相关的各种库和工具。`conda` 支持 Python 和其他语言（如 R）的包，解决了依赖关系问题，避免了包版本冲突。

#### 2. **虚拟环境管理**

通过 `conda`，Anaconda 提供了强大的虚拟环境管理功能。你可以**为不同的项目创建独立的环境**，这样每个项目可以拥有自己独立的包和依赖，**不会互相干扰**。这对于开发多个项目时尤其有用。

#### 3. **内置数据科学工具**

Anaconda 附带了大量常用的数据科学工具和库，例如：

- **NumPy**：用于数值计算的库
- **Pandas**：用于数据分析的库
- **Matplotlib** 和 **Seaborn**：用于数据可视化
- **SciPy**：科学计算
- **Scikit-learn**：机器学习
- **TensorFlow** 和 **PyTorch**：深度学习框架

#### 4. **Jupyter Notebook**

Anaconda 包含了 **Jupyter Notebook**，一个非常受欢迎的交互式编程环境，特别适合于数据分析、可视化以及机器学习实验。它支持通过网页界面实时执行代码，并且可以轻松分享和展示分析过程。

#### 5. **跨平台支持**

Anaconda 支持多种操作系统，包括 Windows、macOS 和 Linux，使得用户在不同平台上可以轻松地设置和使用数据科学工具。

#### 6. **Anaconda Navigator**

Anaconda 还提供了图形用户界面 **Anaconda Navigator**，帮助用户通过图形化的方式安装包、创建环境、启动 Jupyter Notebook 等工具，而不需要使用命令行。

### 1.2 构建新`conda`环境

使用`conda`指令创建新屋子：

```bash
conda create -n pytorch python=3.6
```

`conda`是指调用`conda`包，`create`是创建的意思，`-n`是指后面的名字是屋子的名字，`pytorch`是屋子的名字 (可以更改成自己喜欢的)，`python=3.6`是指创建的屋子，是`python3.6`版本。

激活新环境

```bash
conda activate pytorch
```

停用该环境

```bash
conda deactivate
```

查看环境中有哪些工具包

```bash
pip list
```


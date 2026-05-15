单细胞数据分析可视化平台 
基于C++/Qt/Crow实现的单细胞数据分析后端服务，支持数据集加载、降采样（Downsample）、细胞扩选（LassoView）及前后端交互。 
项目简介 
本项目为高级语言程序设计大作业，实现了一个轻量级后端 HTTP 服务，用于处理单细胞转录组数据的解析、存储、算法计算与 API 接口服务。 
依赖库 
本项目依赖以下开源库,可自行在github下载： 
后端： 
Qt 6：用于数据结构、文件操作、线程安全与跨平台支持 
CrowCpp：轻量级 C++ HTTP 服务器框架，提供 RESTful API 
nlohmann/json：JSON 数据解析与序列化 Asio：网络I/O支持（Crow 依赖） 
HighFive:HDF5 文件读写库，用于解析 .h5ad 单细胞数据集 H5AD 解析相关库：支持单细胞数据集 .h5ad 格式读取 
前端： 
React Plotly.js Axios 
项目结构 
plaintext / 
├── source_code/ 后端源代码 
├── frontend/ 前端UI界面 
├── resources.qrc Qt 资源文件 
├── CMakeLists.txt 编译配置 
├── sc_sampled.zip 数据集压缩包（解压后使用） 
├── README.md 项目说明 
└── C++大作业报告.pdf 课程实验报告 
数据集说明 
数据集已打包为 sc_sampled.zip，使用前请解压，将 .h5ad 文件放入程序运行目录即可加载。 
功能模块 
数据集解析与管理（H5adReader + DatasetStore） 
核心数据结构（AnnDataContainer） 
降采样算法（Downsample） 
细胞扩选算法（LassoView） 
JSON 文件工具（JsonUtils） 
HTTP 服务与前后端通信（http_server） 
API 接口说明 
/api/datasets：获取数据集列表 
/api/datasets/{id}/summary：获取数据集摘要信息 
/api/datasets/{id}/analysis-jobs：提交分析任务 
/api/analysis-jobs/{id}/recover-selection：降采样细胞选择还原 
运行说明 
编译环境：Qt 6.5.3 + C++17 
编译工具：CMake / MinGW / MSVC 
运行前请解压数据集 sc_sampled.zip 
编译项目 创建 build 
目录： mkdir build cd build 
生成工程： cmake .. 
编译： cmake --build . 
编译完成后运行程序： Windows：LassoServer.exe 
Linux：./LassoServer 
启动后端服务后，前端可通过 HTTP 接口:http://localhost15114/连接使用 
功能使用流程 
上传或加载 .h5ad 数据集 查看UMAP可视化结果 使用Downsample进行降采样 使用Lasso Tool进行细胞选择 使用LassoView进行细胞扩选 执行 Recover Selection 还原扩选结果 
声明 
前端框架由团队提供
本项目仅用于南开大学高级语言程序设计课程大作业，仅供学习与交流使用。
# Lasso3.0final

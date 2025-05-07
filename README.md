# B1-11ER
B1-11ER  is a thinking machine that improves many aspects of the mind and creativity
视触觉多模态信息在末端智能中的应用  
Tacchi框架  
https://docs.taichi-lang.cn/docs/cloth_simulation  
训练步骤  
    安装 Tacchi 和仿真器。  
    创建或导入机器人、物体模型。  
    编写少量代码进行手动或简单脚本控制下的抓取模拟，验证 Tacchi 集成是否正常工作  
大规模仿真数据生成 (环境: 需要高性能计算)  
    编写自动化脚本控制仿真，生成大量不同物体、姿态、抓取策略下的视触觉数据及标签。  
    此步骤对计算资源要求极高，无法在 1050Ti 或 Colab 上完成大规模数据生成。 需要考虑租用云服务器（如 AWS, GCP 的 GPU 实例）或使用高性能工作站。  
多模态融合网络模型设计与训练  
    编写数据加载、预处理代码。  
    定义网络架构（PyTorch 或 TensorFlow）。  
    编写训练、验证、评估代码。  
仿真环境下的策略验证  
    编写代码加载训练好的模型，并集成到仿真控制循环中。  
    运行基于模型预测的闭环抓取仿真实验。  
    评估仿真性能。可以在性能尚可的工作站上运行。  
Sim-to-Real 迁移与真实机器人实验 (环境: 真实机器人平台 + 控制电脑)  
    编写与真实机器人、相机、（未来可能的）触觉传感器接口的代码。  
    实现 Sim-to-Real 迁移策略。  
    在真实机器人上运行抓取实验并收集真实数据进行评估或微调。  
    此步骤需要在真实机器人平台和连接的控制电脑上进行。  
多任务与知识迁移验证 (环境: 同上)  
    设计和执行多任务序列及知识迁移实验。  
传感器设计指导分析 (环境: 工作站/笔记本)  
    分析实验数据和模型，提取设计低成本传感器的关键信息。  
B1_root/  
├── simulator/  
│   ├── sim_env.py          # 仿真环境初始化、加载、步进  
│   ├── robot_control.py    # 机器人运动控制接口 (IK, joint control)  
│   ├── object_manager.py   # 物体生成、放置、属性管理  
│   ├── tacchi_interface.py # Tacchi API 调用、数据读取  
│   └── data_recorder.py    # 数据记录与保存  
├── data/  
│   └── raw/                # 原始仿真数据存储  
├── scripts/  
│   └── generate_dataset.py # 数据生成主脚本  
└── utils/  
    └── data_utils.py       # 数据格式转换、加载工具  

# B1-11ER
B1-11ER  is a thinking machine that improves many aspects of the mind and creativity
视触觉多模态信息在末端智能中的应用  
Tacchi框架  
https://docs.taichi-lang.cn/docs/cloth_simulation  
文件框架grasp-system/  
├── simulation/            # 物理仿真核心  
│   ├── lsmpm_solver.py    # 多尺度粒子求解器  
│   └── sensor_model.py    # 触觉/视觉传感器模型  
├── networks/              # 多模态网络  
│   ├── fusion_transformer.py   
│   └── meta_controller.py    
├── hardware/              # 硬件接口  
│   ├── tactile_driver.py  # 触觉阵列驱动  
│   └── hand_controller.py # 灵巧手控制  
├── datasets/              # 数据管理  
│   ├── auto_generator.py  # 自动数据生成  
│   └── real_capture/      # 真实抓取数据集  
└── scripts/               # 实用工具  
    ├── train.py     # 训练脚本  
    └── vis_toolkit.py     # 可视化工具  

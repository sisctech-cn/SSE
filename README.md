# SSE
SiSCTECH Security Engine, encryption and decryption of information

# 介绍
SSE是由北京芯启科技有限公司（SiSCTECHnology CO.,LTD）所开发的信息加解密IP系列，基于其中的核心模块，我们还提供芯片SoC架构“靖”级别的设计服务，以及进一步提供端侧的PCBA硬件方案。

SSE包括多款高性能加解密算法IP，支持在其基础架构上进行灵活多样的扩展开发设计服务。例如，基于AES与DMA或SAR-T6的紧耦合设计，我们将为您打造出性能价格比十分理想的软件可重构的信息处理安全方案。

在此我们将SSE的C model开放上来，它是对应各个加解密算法的硬件RTL设计实现的C语言模型，具有功能一致且有时钟精确度的特点，可以作为模拟器使用，便于所有人下载、评估，也可基于此model修改使之构成您的统一软硬件调试环境，推动您的系统开发进程。

该套SSE IP（AES加解密，DES加解密，M1加解密，M2加解密，M4加解密，HASH加解密，ZUC加解密）的特征为：
+ 低功耗，高性能，可配置
+ 专用DMA
+ 流水线设计
+ 通用总线接口


# 运行说明
C model操作流程，便于上手运行。

在release目录中，有压缩打包好的发布文件包sisc_security.tgz

目录结构：
-----------
    ├── release                 #   
    │   ├── *.tgz               # package for public   
    |   |   ├── cmodel          # 
    |   |   |   ├── *           # dir for each algorithm.
    |   ├── SSE-run_manual.docx
    ├── README.md                                 
    ├── LICENSE                                   

环境：
-----------
在linux服务器上运行,运行和结果信息都将在屏幕输出。也可以输出波形文件。

为了运行，您要依赖以下内容：
+ 开源的GNU，在脚本中调用的是GNU 4.8.5
+ 开源的[Verilator库](https://www.veripool.org/wiki/verilator)
+ 开放的[GTKWave](http://gtkwave.sourceforge.net/)可帮您呈现硬件接口的波形行为

在评估代码中不仅包含了算法的C model，还包含了算法的测试代码示例程序，模拟硬件执行行为。用户可根据自己的需求编写自己的测试代码。

设置：
-----------

步骤：
-----------
您可直接下载sisc_security.tgz

    $ tar -xzf sisc_security.tgz
    $ cd sisc_security/cmodel/sm1
    
您需要编辑test.mk脚本，设置GNU、verilator的本地路径后直接执行

    $ make -f test.mk
    $ ./sm1_top

结果请参考release/SSE-run_manual.docx文档末尾的屏幕输出示意图。测试程序运行完后会输出波形文件dump.vcd。可以打开看波形。

微信公众号：北京芯启科技

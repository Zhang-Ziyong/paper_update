# 计算机视觉领域最新论文 (2026.08.19)

> 每日自动更新计算机视觉领域的最新arXiv论文

> 使用说明: [点击查看](./docs/README.md#usage)

<details>
<summary>分类目录</summary>
<ol>
<li><a href='#slam'>SLAM</a></li>
<li><a href='#sfm'>SFM</a></li>
<li><a href='#image-matching'>Image Matching</a></li>
<li><a href='#sensor-calibration'>Sensor Calibration</a></li>
<li><a href='#sensor-undistortion'>Sensor Undistortion</a></li>
<li><a href='#robot-vlm'>Robot VLM</a></li>
<li><a href='#archive'>归档</a></li>
</ol>
</details>

<h2 id='slam'>SLAM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-18</td><td>Jetson-ORB-SLAM3: Accuracy-Preserving GPU Implementation for Edge Computing Devices<br><a href='http://arxiv.org/pdf/2608.17874'>论文</a></td><td>本文针对边缘设备上视觉惯性SLAM系统因稠密特征提取与回环检测导致的高计算成本问题,提出了Jetson-ORB-SLAM3,采用前端GPU、后端CPU的异构架构,在NVIDIA Jetson Orin Nano上实现精度保持的实时加速。

◆ GPU前端算法级完整复现CPU参考ORB检测器,关键点一致率达94.7%,描述子比特一致率达99.9%,真正实现精度保持而非近似加速。

◆ 通过原生libnvinfer FP16 TensorRT引擎将CosPlace ResNet-50回环检测推理降至2.2ms每查询,较通用ONNX Runtime提升180倍,使学习式地点识别可在7W低功耗设备上与跟踪并发运行。

◆ 在EuRoC、TUM-VI、KITTI三个数据集上验证GPU与CPU实现、嵌入式与桌面平台四种配置轨迹误差一致小于0.10cm,单目惯性模式平均达32FPS,精度与原始ORB-SLAM3相当。</td></tr>
<tr><td>2026-08-18</td><td>Scalix: Uncertainty-Aware Scale-Consistent Monocular SLAM<br><a href='http://arxiv.org/pdf/2608.17553'>论文</a></td><td>Scalix是一种面向移动机器人的实时单目SLAM框架,旨在解决单目视觉固有的尺度模糊问题。该方法将深度学习几何基础模型的预测结果集成到概率因子图优化中,无需依赖惯性测量单元即可实现度量尺度的状态估计。

◆同时为深度模型引入逐像素深度不确定性与逐帧尺度不确定性,有效抑制噪声预测对优化的干扰
◆将尺度预测视为独立测量值纳入因子图,通过多视图数据关联提升跨帧尺度一致性
◆在恒速运动等视觉惯性系统失效的场景下仍能保持鲁棒的尺度估计

在大规模室内外环境的实验中,Scalix在度量尺度和上至尺度基准测试上均达到当前最优性能,同时具备实时运行能力与良好的泛化性。</td></tr>
<tr><td>2026-08-18</td><td>Embodied-Navigator: Point, Think, Memorize, and Align for Efficient Navigation<br><a href='http://arxiv.org/pdf/2608.17512'>论文</a></td><td>该论文针对大视觉语言模型在具身导航中存在的动作空间不自然、推理僵化、记忆低效等问题，提出了TAMP-Nav统一框架。论文的核心创新体现在以下三个方面。

◆ 点（Point）：提出像素到三维的动作范式，将导航重新建模为二维视觉提示任务，让VLM直接在二维像素上选点，再投影到三维坐标交由SLAM控制器执行，从而与VLM的二维预训练先验自然对齐。

◆ 想与记（Think and Memorize）：设计选择性推理与锚点轨迹记忆机制，动态触发链式思维推理，仅在关键节点保留高保真记忆，将冗余轨迹压缩为轻量化的时空指示器，有效保留关键历史信息并增强时空感知。

◆ 对齐（Align）：构建基于群体相对策略优化的两级对齐范式，将全局结果奖励与细粒度过程奖励叠加，对智能体进行密集监督，使其认知规划与物理环境反馈紧密对齐。

实验表明TAMP-Nav在R2R-CE上达到66.2%的成功率，仅需9万条训练轨迹即实现了最先进的性能、运行时效率与样本效率的平衡。</td></tr>
<tr><td>2026-08-17</td><td>ViHaTeleop: A Low-Cost, Lightweight Visual-Haptic Teleoperation System for Dexterous Manipulation Learning<br><a href='http://arxiv.org/pdf/2608.16572'>论文</a></td><td>该论文针对低成本遥操作硬件难以采集接触关键演示数据的问题，提出了ViHaTeleop系统，核心目标是让低成本示教学习在灵巧操作任务中实用化。系统整体仅0.7公斤、成本约550美元，集成了基于SLAM的腕部追踪、相机手部追踪和通过线性谐振致动器（LRA）实现的逐指振动触觉反馈。

◆创新点一：低成本轻量化视觉-触觉遥操作硬件方案，将SLAM腕部追踪、相机手部追踪与LRA逐指触觉反馈统一于一套0.7kg、550美元的设备中。
◆创新点二：多项针对性设计选择，包括LED补光、广角鱼眼手部相机以及触觉感知的重定向约束，以提升接触任务的演示质量与稳定性。
◆创新点三：在Isaac Sim中集成基于轻量深度相机的触觉代理，实现从多模态示教采集到视觉-触觉策略训练的完整仿真-现实流程。
◆创新点四：九名参与者在六项接触关键任务上的用户研究表明，触觉反馈使所有任务成功率提升2.2至15.6个百分点，并在接触清晰度与抓握信心方面获得显著主观增益。
◆创新点五：下游策略训练验证表明，融合触觉信息在插孔等接触关键子任务上较纯视觉策略提升17个百分点。</td></tr>
<tr><td>2026-08-16</td><td>Target Localization and Self-Calibration in a Multistatic Radar System<br><a href='http://arxiv.org/pdf/2608.15501'>论文</a></td><td>本文研究多基地雷达系统中的目标定位与接收机自标定问题,聚焦于平台移动性导致的接收机位姿不确定性这一关键挑战。作者针对执行双基地距离与方位测量的多基地雷达系统,推导了联合目标定位与接收机位姿估计的克拉美罗下界(CRLB),为算法性能提供了理论基准。在此基础上,提出了一种交替加权最小二乘(AWLS)算法,通过迭代优化同时估计目标位置与接收机位姿参数,有效缓解了参数耦合带来的估计偏差。

◆ 推导了多基地雷达系统在双基地距离与方位联合测量下的CRLB,同时覆盖目标定位与接收机位姿估计,为性能评估提供统一理论基准。

◆ 提出交替加权最小二乘算法,实现目标参数与接收机位姿参数的联合优化,在低中噪声水平下估计精度接近CRLB。

◆ 通过蒙特卡洛仿真验证了算法在目标定位精度和接收机自标定方面的有效性,展示了其在协同SLAM和自主机器人网络等场景中的应用潜力。</td></tr>
<tr><td>2026-08-15</td><td>MotionGS-SLAM: Event-Modulated Gaussian Splatting for Motion-Blur Robust SLAM<br><a href='http://arxiv.org/pdf/2608.15024'>论文</a></td><td>MotionGS-SLAM针对运动模糊导致视觉SLAM系统失效的问题，提出了一种全新的解决思路。论文的核心贡献在于将运动模糊去除这一不适定反问题重新建模为适定的前向生成问题，在渲染流程中物理化地建模模糊形成过程。该方法利用事件相机微秒级时间分辨率且不受运动模糊影响的优势，结合3D高斯泼溅技术实现鲁棒的SLAM。

创新点总结如下：

◆ 范式转换：从去模糊的反问题转变为在渲染过程中生成式建模模糊形成的前向问题，将病态问题转化为良态问题。

◆ 事件调制高斯核：提出新颖的事件调制机制，利用事件相机提供的精确运动线索动态调整每个高斯的光栅化方式。

◆ 双重调制机制：在空间维度将2D高斯投影从各向同性圆点转变为沿运动方向的各向异性椭圆笔触（空间调制），在时间维度根据局部速度自适应调整曝光积分采样密度（时间调制）。

◆ 联合优化框架：通过模糊感知的光度约束和事件约束，实现曝光内相机轨迹与三维场景几何的联合优化。

大量实验表明，该方法在严重高速运动条件下，轨迹精度和地图质量均显著优于现有最先进方法。</td></tr>
<tr><td>2026-08-15</td><td>HP2-SLAM: Adaptive Hybrid ICP for Robust and Efficient LiDAR SLAM<br><a href='http://arxiv.org/pdf/2608.14996'>论文</a></td><td>HP2-SLAM是一个面向LiDAR SLAM的极简而鲁棒的框架,旨在同时解决稳健性、精度和效率难以兼顾的核心难题。它针对传统几何方法在平面或重复场景中因标准ICP局限而性能下降的问题,提出了邻域大小自适应的混合ICP策略。

◆ 提出平面感知的自适应阈值机制,根据局部几何结构和密度动态分类对应关系,实现在点对面和点对点残差之间的原则性平衡。

◆ 无需特征工程、学习模块或数据集特定调参,即可在结构化与退化环境中保持稳定的位姿对齐。

◆ 集成子图管理、回环检测和位姿图优化构成完整SLAM流水线,在公开数据集上一致超越强几何基线,同时在普通硬件上保持实时性能,证明精心设计的几何自适应策略能够兼顾泛化性、简洁性与效率。</td></tr>
<tr><td>2026-08-14</td><td>Geometry-Aware Online Mapping for 3D Gaussian Splatting SLAM<br><a href='http://arxiv.org/pdf/2608.14902'>论文</a></td><td>本文针对3D高斯泼溅(3DGS) SLAM系统在线建图时，沿用离线重建的初始化与密度控制启发式方法，在严格逐帧优化预算下表现脆弱的问题，提出在解耦的建图线程中引入几何感知的改进策略。研究指出在线SLAM中光度残差与位姿不确定性存在耦合关系，因此应针对性地设计高斯原语的扩展与精化机制。整体方法在几乎不增加计算开销的情况下持续提升了渲染质量。

◆ 透射率保持的致密化策略，避免新增加的高斯原语破坏场景透射率分布，使增量建图更稳定。

◆ 基于深度与相机内参的尺度感知初始化方法，为高斯原语提供几何上合理的初始尺度，减少离线启发式带来的脆弱性。

◆ 误差引导的致密化机制，将新原语优先放置在高残差区域，使有限的计算与迭代资源聚焦于重建薄弱处。

◆ 通过开源代码促进3DGS-SLAM领域的方法复现与进一步发展。</td></tr>
<tr><td>2026-08-14</td><td>E-S2Feat:Semantic-Guided Spiking Local Feature Detection and Description for Event Cameras<br><a href='http://arxiv.org/pdf/2608.14027'>论文</a></td><td>本文针对事件相机局部特征提取中存在的稀疏性、噪声和有限纹理等问题，提出了一种基于脉冲神经网络的框架E-S2Feat，用于在资源受限平台上实现高精度且高能效的局部特征检测与描述。该方法从特征表示和特征选择两个角度联合优化局部特征学习。

◆ 模块特定的脉冲激活机制：在低比特能效推理下保留细粒度结构线索和判别性信息，提升特征表示的保真度。

◆ 语义引导的特征调制机制：利用语义先验优化关键点响应分布，增强描述符的判别能力，引导模型提取几何稳定性更强、判别性更高的局部特征。

实验表明，该方法在ECD和EDS数据集上的位姿估计精度显著优于SuperEvent等基线方法，理论计算能效相比其人工神经网络对应版本提升约4.8倍，并在TUM-VIE数据集的视觉惯性里程计实验中验证了在完整SLAM系统中的实用价值。</td></tr>
<tr><td>2026-08-10</td><td>A Semantic Communication Approach to Fiducial Marker Processing in 5G-Enabled Edge SLAM<br><a href='http://arxiv.org/pdf/2608.09620'>论文</a></td><td>本文针对5G边缘SLAM中信标标记处理的实时性与计算负载矛盾，提出了一种基于语义分割推理的协作框架。该方法将DeepTag风格的卷积神经网络在机器人端与边缘服务器之间进行切分，利用中间特征图作为面向任务的语义信息在无线链路上传输，避免了传统信标检测流程难以有效划分任务的局限。论文将所提框架集成到ROS2机器人架构中，并在真实5G测试平台上进行了端到端实验验证。

◆ 提出面向5G边缘SLAM的信标标记语义分割推理框架，将检测任务在机器人与边缘服务器间灵活切分。

◆ 以卷积神经网络中间特征作为任务导向的语义信息进行传输，显著降低无线通信负载同时保留关键点估计精度。

◆ 在真实5G测试床上完成系统级集成与验证，定量分析了不同切分点下通信开销与计算精度的权衡关系，为连接机器人系统中深度视觉感知的通信感知部署提供了实用指导。</td></tr>
<tr><td>2026-08-10</td><td>Multi-Submap Implicit Neural SLAM with Local-to-Global Loop Closure for Large-Scale Scene Reconstruction<br><a href='http://arxiv.org/pdf/2608.09146'>论文</a> | <a href='https://github.com/dtc111111/MSN-SLAM}{https://github.com/dtc111111/MSN-SLAM}'>代码</a></td><td>本文针对大规模场景下NeRF-SLAM面临的灾难性遗忘和轨迹漂移难题，提出了一种融合多子图架构与双层回环检测的神经SLAM系统。该系统通过渐进式建图策略动态分配神经子图，在保证高保真重建的同时有效控制显存消耗。

◆ 提出了基于多子图的渐进式建图策略，动态分配子图以维持高保真表征并避免内存爆炸，同时缓解灾难性遗忘问题。

◆ 集成光流跟踪模块以应对剧烈运动场景下的鲁棒位姿估计。

◆ 设计局部到全局的回环闭合框架，利用基础模型提取高性能全局描述符，显著提升不同视角下的重定位精度。

◆ 提出子图间在线蒸馏算法，在后端优化中强制重叠子图边界的几何与外观一致性，确保全局一致的大规模重建。

作者还开发了定制化手持机电平台，在公开基准及自采的大规模室内外数据集上进行了广泛验证，并在车载计算单元上完成实际部署，实验表明该方法在重建质量与定位鲁棒性上均优于现有神经SLAM方法。</td></tr>
<tr><td>2026-08-10</td><td>ROEVO: Robust Organized Edge Feature-based Visual Odometry Using RGB-D Cameras<br><a href='http://arxiv.org/pdf/2608.09112'>论文</a> | <a href='https://github.com/liumingrui814/ROEVO'>代码</a></td><td>本文提出了一种基于RGB-D相机、利用图像边缘特征的视觉里程计系统ROEVO，旨在充分挖掘边缘特征在纹理和结构表达上的潜力。现有边缘视觉里程计方法未能有效利用这些信息，作者通过引入一种新颖的&quot;组织化边缘&quot;特征表示，将分散的边缘像素转化为有序的序列簇，从而更好地保留和利用底层纹理与结构信息。该系统包含针对组织化边缘特性设计的跟踪与联合优化方法，实现了精确高效的位姿估计。实验表明，该方法在室内环境中具有出色的精度和鲁棒性，性能达到或优于当前最先进的方法。

◆ 提出&quot;组织化边缘&quot;特征表示，将离散的边缘像素转化为有序的序列簇，并支持跨帧的边缘级关联以构建共视图。
◆ 在跟踪阶段采用边缘级而非像素级的残差建模方式，实现鲁棒且精确的帧间配准。
◆ 提出一种保持形状的边缘拟合方法，并设计将传统BA问题分解为拟合与配准两阶段的组织化边缘BA优化策略，有效保留结构完整性。</td></tr>
<tr><td>2026-08-09</td><td>EndoMD-SLAM: Endoscopic Gaussian Splatting SLAM under Optical Degradation with Memory and Static-Transient Decomposition<br><a href='http://arxiv.org/pdf/2608.08949'>论文</a></td><td>该论文针对内窥镜高斯泼溅SLAM系统在临床手术中遭遇光学退化（如移动碎屑、冲洗水伪影）时的失效问题，指出传统方法因严格依赖多视角光度一致性，会将伪影错误融入持久三维几何，导致严重跟踪漂移与不可逆的地图损坏。为此，作者提出了EndoMD-SLAM框架，通过专门设计的跟踪与建图机制在退化条件下保持系统稳定。

◆在跟踪端，引入记忆驱动的门控机制，检测不可靠观测后暂停地图更新，并利用历史关键帧进行漂移感知的重定位。

◆在建图端，采用自监督的静态-瞬态分解，将视觉污染物隔离到专用瞬态场，防止伪影与持久解剖地图发生结构性纠缠。

此外，作者还从结肠镜视频中整理了针对退化场景的基准数据集，实验结果表明EndoMD-SLAM在严重退化下仍能保持几何完整性，将绝对轨迹误差降低91%，渲染保真度提升9.9 dB PSNR。</td></tr>
<tr><td>2026-08-09</td><td>EvTrajGS: Accurate and Efficient 3D Gaussian Splatting from Unposed Event Streams<br><a href='http://arxiv.org/pdf/2608.08585'>论文</a></td><td>EvTrajGS提出了一种基于3D高斯泼溅的无位姿事件流重建框架,旨在同时解决现有方法在重建质量与计算效率之间的权衡问题。该方法无需依赖计算昂贵的SLAM式流程,即可从粗略位姿先验出发实现可靠的联合位姿-场景优化。其核心创新包括以下三点:

◆将相机运动建模为连续时间轨迹,以离散相机位姿进行初始化,为位姿精修提供统一表征。

◆将相邻轨迹状态聚合成时间耦合位姿,在联合优化过程中促进时间一致的位姿更新。

◆引入损失重加权的事件采样策略,自适应强调时间维度上重建不足的区间。

大量合成与真实数据集实验表明,EvTrajGS在几何重建质量与位姿估计精度上均超越现有最优方法,PSNR提升3.8 dB,SSIM提高0.1,ATE RMSE降低超过40%,同时保持了较高的计算效率。</td></tr>
<tr><td>2026-08-06</td><td>A Low-Latency ASIC Architecture for Real-Time Line Segment Detection<br><a href='http://arxiv.org/pdf/2608.06439'>论文</a></td><td>本文提出了一种面向实时线段检测的低延迟ASIC架构,基于步进长度算法并结合五项硬件专用优化技术,解决了深度学习方法资源消耗大、经典算法延迟受图像内容影响的问题。该架构采用全流水线设计,每时钟周期处理一个像素,具备确定性低延迟特性。

◆ 基于寄存器的行缓冲与数据复用机制,降低存储访问开销
◆ 无乘法器的MCM(多常数乘法)滤波结构,减少硬件资源
◆ 8类角度量化,简化角度比较逻辑
◆ 类CAM关联存储,实现单周期匹配
◆ 优化的重复线段去除机制,提升输出质量

在45nm CMOS工艺下,该设计在VGA分辨率下达到325 FPS(125 MHz时406 FPS),全高清下48 FPS,功耗仅25.54 mW,面积0.412 mm²。相比基于Line Hough Transform的90nm ASIC实现,功耗降低49%,帧率提升超过1.6倍,非常适合边缘计算等对实时性、低功耗与小面积有严格要求的应用场景。</td></tr>
<tr><td>2026-08-06</td><td>KILVO: Kinematic-Inertial-LiDAR-Visual Odometry with Robust Multimodal Adaptation for Humanoid Robots<br><a href='http://arxiv.org/pdf/2608.05647'>论文</a></td><td>本文提出KILVO，一种面向人形机器人的运动学-惯性-激光-视觉里程计系统。该方法将关节编码器、IMU、LiDAR和相机在异步-顺序混合误差状态迭代卡尔曼滤波(ESIKF)框架下进行紧耦合融合，其中惯性数据用于预测，腿部运动学信息以高频率异步处理以提供本体感受约束，而LiDAR和视觉则按顺序进行外感受更新。

◆提出首个面向人形机器人的四模态紧耦合里程计算法，统一融合关节编码器、IMU、LiDAR与相机，适配平台特性。
◆设计异步-顺序混合ESIKF架构，惯性高频预测、腿部运动学异步处理、LiDAR与视觉顺序外感受更新，兼顾效率与精度。
◆具备多模态自适应能力，可针对单一或多传感器退化与失效进行鲁棒切换，无需额外硬件。
◆开发紧凑的接触估计模块，与状态估计共享信息，无需额外传感器即可辅助里程计精度提升。
在公开数据集与多平台、多步态的真实场景实验中，KILVO在精度、效率和输出频率方面均优于现有融合方法。</td></tr>
<tr><td>2026-08-04</td><td>SLAMFormer-$\infty$: Infinite SLAM Transformer for Unbounded Frontend and Backend Processing<br><a href='http://arxiv.org/pdf/2608.03429'>论文</a></td><td>SLAMFormer-∞是首个支持无显式距离限制的前端与后端统一处理的几何Transformer，它突破了传统SLAM系统对范围扩展性的瓶颈。论文提出用记忆条件来定义输入帧的灵活坐标系和尺度，取代了以第一帧为锚点的传统建模范式，使结构条件表达更加丰富灵活。

◆ 创新点一：提出基于记忆条件的灵活坐标系与尺度定义，摆脱对首帧锚点的依赖，实现无界长程处理能力。

◆ 创新点二：前端在保持局部高效计算的同时，后端能够联合优化长程轨迹与场景几何，实现全局一致性。

◆ 创新点三：在超过17公里的超长轨迹上成功运行，并在大规模数据集的轨迹估计与场景重建任务中取得领先或极具竞争力的性能，展现了出色的泛化能力。</td></tr>
<tr><td>2026-08-03</td><td>CHOW-SLAM: Compact Hybrid Representation with Complementary Overlap Window Optimization for RGB-D SLAM<br><a href='http://arxiv.org/pdf/2608.01914'>论文</a> | <a href='https://github.com/jinjidexiaohuoban/CHOW-SLAM'>代码</a></td><td>CHOW-SLAM提出了一种面向RGB-D SLAM的紧凑混合表示与互补重叠窗口优化框架,旨在解决现有NeRF-based SLAM系统在有限在线资源下难以同时构建空间与时间两类约束的问题。空间层面,该方法将参数化分支与哈希分支按平面与网格进行多尺度组织,并通过统一多输出解码器对齐TSDF与密度诱导的光线终止分布,从而在紧凑参数预算下保持几何与外观的判别性。时间层面,设计互补重叠窗口策略,在固定预算内保留近期帧、选取高重叠局部帧并引入时序分散的历史关键帧,结合损失感知的关键帧插入与BA调度,使优化免受短时重叠或弱关联历史观测的支配。整体流程采用ORB前端进行位姿初始化与跟踪,再以神经渲染优化提升跟踪稳定性。

◆ 提出参数化-哈希(P-H)混合紧凑表示,按平面与网格跨尺度组织,并通过统一多输出解码器对齐TSDF与密度的光线终止分布,在紧凑参数预算下保持几何与外观判别性。
◆ 设计互补重叠窗口优化策略,结合近期帧、高重叠局部帧与时序分散的历史关键帧,并以损失感知的关键帧插入与BA调度自适应调整优化强度。
◆ 集成ORB前端跟踪与神经渲染优化,先进行几何位姿初始化,再通过渲染损失细化位姿,从而提升跟踪稳定性与精度。</td></tr>
<tr><td>2026-08-03</td><td>UniSim-SLAM: Feed-Forward SLAM with Unified Sim(3) Optimization<br><a href='http://arxiv.org/pdf/2608.01706'>论文</a> | <a href='https://vision3d-lab.github.io/unisim-slam/'>代码</a></td><td>UniSim-SLAM 是一套面向几何基础模型的前馈式 SLAM 系统，旨在解决现有方法在长序列下因输入视图差异导致的轨迹漂移和几何不一致问题。系统采用前后端协同架构，前端运行轻量级的两视图关键帧跟踪以保证低延迟，后端则周期性触发多视图子图细化以提供更强的几何约束。

◆ 提出统一多层级 Sim(3) 因子图，联合优化全局关键帧位姿与子图位姿，融合时序两视图里程计边、视图到子图的桥接边以及子图间的连接与尺度约束，使异构局部坐标和尺度下产生的预测能在统一的相似变换空间内保持一致。

◆ 引入基于深度统计量的尺度锚定机制，将多视图子图预测中的尺度信息可靠地传递到全局因子图中，从而在无需标定的情况下获得尺度一致的轨迹。

◆ 在 TUM RGB-D 和 7-Scenes 无标定场景下达到当时最优精度，轨迹误差分别降低 38.5% 和 45.9%，验证了方法的有效性。</td></tr>
<tr><td>2026-08-02</td><td>Stipple: Real-Time Incremental Gaussian Splatting with Visual-Inertial Tracking<br><a href='http://arxiv.org/pdf/2608.00931'>论文</a></td><td>本文提出Stipple方法,将视觉惯性跟踪系统与3D高斯泼溅技术结合,实现了实时增量式的三维场景重建。针对3DGS预处理和训练步骤繁重、难以满足机器人和XR应用实时性需求的问题,作者通过利用Basalt视觉惯性里程计提供的高质量位姿和深度信息,设计了一种新的增量训练策略,避免了大量离线预处理。系统在跟踪线程并行运行重建流程,GPU渲染与跟踪解耦,显著提升了效率。该方法展示了SLAM与3DGS的互补价值,为实时三维重建提供了一条有前景的技术路线。

核心创新点:

◆ 基于Basalt视觉惯性跟踪系统与Brush(GPU无关的Rust实现)构建紧耦合的实时框架,直接复用跟踪线程生成的位姿与深度信息,大幅减少3DGS传统预处理开销。

◆ 提出增量式训练策略,替代3DGS中耗时的全局优化步骤,使得高斯参数可随新数据持续更新,适合在线重建场景。

◆ 将跟踪与重建并行化,设计高效的流水线使训练在跟踪线程运行的同时同步进行,实现真正的实时三维重建。

◆ 引入多种实际工程优化,包括跨平台GPU抽象和内存管理改进,使整个管道能够在资源受限的机器人或XR设备上实时运行。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-18</td><td>Confining density functional approach to the QCD phase diagram at low temperatures and thermal twin stars<br><a href='http://arxiv.org/pdf/2608.18038'>论文</a></td><td>本文构建了基于密度泛函理论的温密核物质状态方程,通过Maxwell构造在恒定熵每重子条件下将核物质(DD2模型)与夸克物质(禁闭密度泛函)相耦合,适用于超新星爆发、中子星合并及Q球宇宙学演化等场景。

◆ 提出DDf-SFM与DD2-χCDF两套混合状态方程模型,系统研究含与不含色超导情形下的等熵混合星

◆ 发现有限温度下当熵每重子超过临界值时,DDf-SFM模型出现&quot;热孪生星&quot;第三族分支解,而色超导模型及零温情形则不存在

◆ 揭示热孪生星对应的临界熵与Seidov引力不稳定性判据密切相关,并将其作为大质量蓝超巨星超新星可爆性的新判据

◆ 据此排除强色超导模型,同时探讨解禁闭起始密度对色超导的敏感性,并与Danielewicz核物质流约束进行了对比验证...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-18</td><td>Initialization-Free Bundle Adjustment Revisited: A Controlled Experimental Study<br><a href='http://arxiv.org/pdf/2608.18028'>论文</a> | <a href='https://github.com/simonwebertum/InitFreeBA.git'>代码</a></td><td>本文重新审视了无需初始化的光束法平差(InitFree BA),指出当前研究仅关注优化成功率而忽略了低OSE目标函数值能否产生有效的度量三维重建。作者构建了统一评估框架,集成C++实现的OSE算法与Blender合成数据生成器,提供精确真值与可控的相机配置及观测密度。实验揭示了被忽视的&quot;优化-重建差距&quot;现象:具有相似OSE值的射影解在度量升级后可能产生显著不同的欧式重建。研究进一步识别出初始化先验、路标点观测密度与度量升级稳定性是影响重建成功的关键因素,表明InitFree BA的核心挑战不仅是优化目标函数,更在于获得可稳定升级的射影重建。

◆ 提出统一的InitFree BA评估框架,包含C++实现与Blender数据生成器
◆ 首次系统揭示&quot;优化-重建差距&quot;现象,证明低OSE值不等于有效度量重建
◆ 识别出三个关键因素:初始化先验、观测密度、度量升级稳定性
◆ 提供开源基准与代码,推动该方向未来研究...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-15</td><td>Robust structure from motion for aerial-ground images via detector-free feature matching and multi-view track refinement<br><a href='http://arxiv.org/pdf/2608.15251'>论文</a></td><td>本文针对空地图像集成三维重建中因视点、尺度和旋转剧烈变化导致的特征匹配难题,提出了一种结合旋转鲁棒无检测器匹配网络与多视图轨迹优化的增量式SfM框架。核心创新包括:◆ 旋转感知特征提取模块,采用全向状态空间块(OSS Block)沿八个对称方向选择性扫描,建模长程空间依赖并合成旋转不变特征图。◆ 多尺度注意力变换,利用四叉树注意力构建层次化token金字塔,以线性复杂度隔离高关联区域并过滤无关区域。◆ 双向特征匹配,设计对称由粗到精的对齐策略,通过互最近邻约束计算双向Softmax置信度矩阵,并用MLP回归亚像素级坐标偏移。◆ 多视图轨迹优化,采用集成索引结构评估局部空间邻近性,将离散的子轨迹链接到最高置信度锚点,确保ISfM流程中特征的稳定可重复性。在真实空地数据集上的实验表明,该方法在5°位姿误差AUC指标上较LoFTR提升93.9%,在ISfM重建精度上提升27.6%至32.7%,为空地图像高精度集成三维重建提供了可靠方案。</td></tr>
<tr><td>2026-08-12</td><td>MV2: Multi-View Multi-Vehicle Driving Dataset for Novel View Synthesis<br><a href='http://arxiv.org/pdf/2608.12442'>论文</a> | <a href='https://mv2-dataset.github.io/'>代码</a></td><td>本文针对真实驾驶场景中可微渲染与新视角合成（NVS）面临的稀疏视角、动态物体和单一轨迹等难题，提出了多视角多车辆（MV2）数据集与基准测试。

◆核心创新点包括：首次引入由汽车、踏板车和无人机三种载具同步采集的驾驶数据，各载具沿不同但同步的轨迹行驶，使得在一个载具的相机流上训练、在另一载具上测试成为可能，从而支持大幅视角变化下的NVS评估。

◆所有序列通过Structure-from-Motion注册，并利用人工像素级对应标注验证相机位姿，确保数据质量，最终构建了包含50个高质量场景、12000张图像的基准。

◆在现有NVS与相机位姿估计方法的基准测试中发现，NVS性能随视角差异增大而显著下降，且前馈式位姿估计器明显落后于基于优化的方法，凸显了MV2作为驾驶NVS严格测试床的价值。</td></tr>
<tr><td>2026-08-06</td><td>Confidence matters: Leveraging Multi-view Geometric Priors for GS-based Reconstruction<br><a href='http://arxiv.org/pdf/2608.06117'>论文</a></td><td>本文针对3D高斯溅射(3DGS)在几何重建尤其是高镜面物体上表现欠佳的问题，系统研究将预测的法线和深度图等几何先验融入3DGS框架的方案。

◆研究发现多视图几何预测器（如视觉几何接地Transformer VGGT）显著优于单视图方案，关键在于多视图模型天然附带置信度图，可对每像素预测进行自适应加权。

◆提出基于置信度的先验融合策略，将VGGT输出的法线、深度及其置信度作为软约束嵌入3DGS优化过程，使模型在高不确定性区域保持鲁棒。

◆在标准基准上的大量实验表明，该方法在重建质量上获得一致提升，并对含镜面物体的复杂场景带来尤为显著的增益。

该工作揭示了多视图几何先验及置信度机制是突破3DGS几何重建瓶颈的关键路径。</td></tr>
<tr><td>2026-08-05</td><td>VLAff: Vision-Language-Affordance Model for Unified Actionable Affordances<br><a href='http://arxiv.org/pdf/2608.05215'>论文</a></td><td>本文针对从人类视频学习机器人操作技能中存在的身体差异问题，提出了一套基于自我中心视频的可操作可供性学习框架。研究者利用三维结构恢复和手部网格重建技术，从人类视频中提取出视觉可供性、抓取可供性和轨迹可供性三种与身体无关的交互表征。

◆提出统一的可供性提取框架，将人类视频转化为包含交互位置、抓取方式和运动路径的完整可供性表示。

◆构建大规模数据集EgoAffordance，包含20.4万条片段、560万视觉可供性以及1160万抓取与轨迹可供性标注。

◆设计基于视觉-语言大模型的基础模型VLAff，通过跨模态关联学习统一预测三类可供性，并结合三维场景信息直接生成可执行动作。

◆在视觉可供性预测任务上达到最优性能，并成功应用于零样本机器人操作和可供性引导的机器人学习等实际场景。</td></tr>
<tr><td>2026-08-03</td><td>Loggia dei Lanzi: AI Thermography Enhancement Comparisons through 3D Photogrammetry<br><a href='http://arxiv.org/pdf/2608.02404'>论文</a></td><td>本文以佛罗伦萨领主广场的佣兵凉廊为研究对象,于2025年12月使用FLIR T1020高清热像仪开展热成像调查,成功揭示了隐藏在灰泥层下的被封堵开口和材料过渡区域等建筑特征。在光束法平差(SfM)摄影测量流程中,系统比较了三种分辨率层级的图像——原生分辨率、FLIR硬件像素移位超分辨率(UltraMax)以及AI超分辨率模型,定量评估了不同增强方式对特征点检测和连接点生成的影响。

◆首次在文化遗产热成像摄影测量工作流中,直接对比硬件微扫描(FLIR UltraMax)与AI超分辨率的实际效果差异。

◆提出基于三档分辨率层级的定量评估方法,验证超分辨率细节能否转化为更密集、更精确的三维热模型。

◆将研究数据整合进交互式三维档案框架及城市级扩展现实叠加应用,实现研究成果的开放共享与沉浸式展示。

◆公开发布完整数据集,为人工智能与遗产热成像这一新兴交叉领域提供可复用的基准资源。</td></tr>
<tr><td>2026-08-02</td><td>Swimm3R: Splatting with Medium-aware SfM for Underwater 3D Reconstruction<br><a href='http://arxiv.org/pdf/2608.00950'>论文</a></td><td>本文提出Swimm3R，一个融合介质感知SfM与水下Beta泼溅的统一框架，旨在解决水下三维重建中因散射和衰减导致的失效问题。该方法将空中几何先验蒸馏到前馈骨干网络，并利用物理回归头同时预测水下图像形成参数、相机位姿以及恢复后的点云。针对水下场景的特殊性，进一步提出Underwater Beta Splatting，用Beta基元扩展高斯泼溅并引入散射感知几何梯度，从而实现稳定的水下几何表征。此外，作者构建了Barbados水下视频数据集用于评估。

◆ 提出统一框架Swimm3R，首次将介质感知SfM与水下Beta泼溅相结合用于水下3D重建
◆ 设计物理回归头，可联合预测水下成像参数、相机位姿及校正后的稠密点云
◆ 提出Underwater Beta Splatting，用Beta基元替代高斯基元并加入散射感知几何梯度
◆ 发布Barbados水下视频数据集，为复杂水下环境评估提供新基准

实验结果表明，Swimm3R在强散射条件下能鲁棒恢复海底几何结构，重建质量较WaterSplatting平均PSNR提升1.47 dB，下游定位任务中RRA@15和RTA@15分别提升2.0和2.4个百分点。</td></tr>
<tr><td>2026-07-29</td><td>VidMap: Exploiting Temporal Structure for Video-Based Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.27194'>论文</a> | <a href='https://github.com/cvg/vidmap'>代码</a></td><td>本文针对无约束视频的相机标定与度量位姿恢复问题,提出VidMap系统,旨在弥合现有SLAM与SfM方法之间的鸿沟。现有SLAM对初始化敏感、容易瞬态失败且通常依赖已知相机标定,而传统SfM虽支持全局优化但对视觉对称性和极端运动鲁棒性不足。本文方法将SLAM的强序列约束与离线SfM的灵活性及全局优化能力相结合,实现对任意长视频的度量重建。

◆利用宽基线稠密图像匹配建立可靠的图像间关联
◆将时间顺序作为一等公民用于可靠的回环检测
◆在全局优化中引入单目度量深度先验以恢复尺度一致性

在多个具有极端运动和视觉对称性的挑战性数据集上的实验表明,无论是否已知相机标定,该方法均显著优于当前最先进的SLAM和SfM方法。</td></tr>
<tr><td>2026-07-29</td><td>3DGBGS: 3D Granular Ball Gaussian Splatting for Compact Novel View Synthesis<br><a href='http://arxiv.org/pdf/2607.26578'>论文</a></td><td>本文针对基于锚点的三维高斯溅射方法中固定体素化难以适应非均匀点云分布的问题,提出3DGBGS框架,将粒度球计算思想引入三维高斯溅射中,实现了对SfM点云的自适应组织表示。方法使用较大的粒度球紧凑表示平滑冗余区域,使用较小的粒度球保留复杂几何和局部细节,从而缓解锚点数量、模型紧凑度与渲染质量之间的权衡矛盾。

◆ 提出Granular Ball Anchor Initialization (GBAI),利用粒度球中心初始化锚点位置,实现紧凑的锚点布局。

◆ 提出Granular Ball Scale Prior (GBSP),利用粒度球半径为高斯生成提供局部尺度先验,提升几何适应性。

◆ 构建3DGBGS端到端框架,在四个基准数据集上将初始和最终锚点数量分别减少37.1%和10.0%,平均模型存储减少9.8%,同时保持相当的渲染质量。</td></tr>
<tr><td>2026-07-28</td><td>Macroscopic wall pressure and microscopic contact load in crowds without egress: social-group cohesion and boundary buffering<br><a href='http://arxiv.org/pdf/2607.25780'>论文</a></td><td>本文针对无疏散密集人群的机械安全风险，构建了耦合弹性重定向模型（ERM）与社会力模型（SFM）的分析框架，填补了传统疏散与避碰评估之外的力学风险研究空白。◆通过引入社会群体内聚力γ_g与墙体缓冲γ_w作为后碰撞参数，分别从宏观壁面线压力P_wall和微观最大碰撞冲量δp_max量化双重风险尺度。◆研究发现P_wall与δp_max之间存在权衡：群体内聚与壁面缓冲虽能降低壁压，但可能在中等等级引发高冲量危险窗口，γ_g→1时局部配对通过动能重分配降低冲量。◆通过有限尺度分析识别出两类相变边界——独立个体在γ_w=0.5处的磁化率跃迁相变，以及分组个体沿(1-γ_w)(1-γ_g)=0.5的磁化率发散相变并终止于临界点。◆这些相变行为仅在ERM与SFM耦合动力学中涌现，为高密度无疏散场所的人群风险缓解提供了机理性指导。</td></tr>
<tr><td>2026-07-27</td><td>Accuracy potential of visual localization exploiting high-end street-level imagery<br><a href='http://arxiv.org/pdf/2607.24409'>论文</a> | <a href='https://fhnw-muttenz-vl-dataset.github.io/'>代码</a></td><td>本文针对视觉定位精度尚未系统评估的空白,提出了一套可扩展的视觉定位流程,并构建了公开的大规模基准数据集以验证其在测量级应用中的精度潜力。

◆ 提出基于高分辨率街景影像的视觉定位流程,直接将精确地理参考影像作为场景表示,结合先验引导的参考候选筛选与在线局部SfM重建加PnP位姿估计,实现了可扩展的高精度定位。

◆ 发布FHNW Muttenz数据集,覆盖10公里连续道路网,包含两次相隔约1.5年采集的高分辨率参考影像与查询序列,使用四种相机在五个场景获取数据,提供亚厘米级真值位姿。

◆ 在该数据集上的实验表明,视觉定位中位精度可达平移1至5厘米、旋转0.05至0.1度,最优条件下分别低至1厘米和0.03度。

研究表明视觉定位能够补充测量级GNSS定位,为消费级设备实现三维地理空间数据采集和全自动地理参考提供了可行路径。</td></tr>
<tr><td>2026-07-20</td><td>Ergodicity of FIRE: star formation variations within and between simulated galaxies<br><a href='http://arxiv.org/pdf/2607.18005'>论文</a></td><td>本文研究了FIRE-2项目高分辨率模拟星系中恒星形成的遍历性,聚焦于星系偏离恒星形成主序(SFMS)的程度,以及集合平均与时间平均的恒星形成历史是否一致。

◆研究发现无论采用何种SFMS定义和恒星形成示踪量,单个星系的SFMS偏差都随时间趋向遍历性行为。

◆该趋势在不同形态星系中均成立,但核球主导的星系比盘主导星系表现出更小的SFMS偏差范围。

◆基于短时标(10^7年)的恒星形成示踪量比长时标(10^9年)能更快地收敛到遍历性。

◆研究还指出当前结论受限于样本规模,高红移演化以及活动星系核的影响有待进一步研究。</td></tr>
<tr><td>2026-07-20</td><td>Stability and Comfort in Mobile Robot-Pedestrian Interactions<br><a href='http://arxiv.org/pdf/2607.17604'>论文</a></td><td>本文针对公共空间移动机器人需保障行人舒适度的问题,为非完整约束移动机器人(NMR)提出了社会感知导航算法,通过理论分析、仿真标定与真实行人交互实验系统验证了其有效性。

◆创新点一:将社会力模型(SFM)与投影碰撞时间社会力模型(TSFM)相结合,显式建模行人的主观安全感受,克服了传统导航算法将行人简单视为动态障碍的局限。

◆创新点二:首次形式化NMR与行人及障碍物的交互过程,并在有界非被动行人假设下严格证明了系统的稳定性,填补了非完整约束机器人社会导航的理论空白。

◆创新点三:构建兼顾舒适度与速度的混合代价函数进行模型标定,并通过问卷统计分析与遥控基线对比,验证了所提算法在改善行人舒适度方面相对于已有方法的显著优势。</td></tr>
<tr><td>2026-07-17</td><td>HETA++: Global Structure-from-Motion with Hybrid Explicit Translation Averaging<br><a href='http://arxiv.org/pdf/2607.15912'>论文</a></td><td>本文提出了一种新的混合显式平移平均框架HETA++,用于全局式SfM,旨在同时利用相对平移和特征轨迹,克服现有方法在共线相机运动下的退化问题以及对异常值的敏感性。

◆首先利用全局相机旋转精化相对平移并剔除全局不一致的相对平移,提升输入数据的可靠性。

◆接着采用基于凸距离的目标函数估计初始相机位置和三维点,再以非双线性角度目标函数进行精化,兼顾了收敛稳定性和几何一致性。

◆针对平移平均阶段相机旋转固定导致精度受限的问题,提出通过有界角度精化和基于重投影的束调整,联合稳健地优化相机旋转与位置。

◆在优化过程中筛选空间分布均衡的特征轨迹,既提升了效率也增强了鲁棒性,最终通过完整束调整获得高精度结果。

大量实验表明,该方法在顺序和无序真实数据集上均优于当前最先进方法,在精度和计算效率方面均表现突出。</td></tr>
<tr><td>2026-07-16</td><td>Immediate 3D Gaussian Splat Reconstruction of Unordered Input with Global Consistency<br><a href='http://arxiv.org/pdf/2607.14481'>论文</a></td><td>本文针对3D高斯溅射(3DGS)重建中乱序输入与即时反馈难以兼顾的问题，提出首个支持乱序图像输入并保持全局一致性的即时重建框架。该方法通过复用视觉位置识别模型与构建共视性图，实现乱序序列的快速匹配与高连通关键帧筛选，并结合GPU优化和精心设计的高斯基元放置策略，保证局部重建的效率与质量。

◆ 提出基于视觉位置识别与共视性图的乱序图像快速匹配方法，并发现高连通关键帧的选择还能进一步提升有序序列的重建质量。

◆ 提出基于共视性图的聚类式回环闭合策略，无需依赖顺序输入即可实现高效的全局一致性优化。

◆ 引入渐进式层次结构，使方法能够扩展到包含数千张图像的大规模场景，同时兼顾效率与视觉质量。</td></tr>
<tr><td>2026-07-15</td><td>SalientGS: Unified SfM-to-3DGS with Importance-Guided MCMC Gaussian Allocation<br><a href='http://arxiv.org/pdf/2607.11285'>论文</a> | <a href='https://github.com/Six-Bit-TX/SalientGS'>代码</a></td><td>SalientGS提出了一种统一的SfM到3D高斯溅射（3DGS）的端到端重建流水线，旨在消除传统3D场景重建中昂贵的SfM预处理和冻结位姿接口的瓶颈。其核心创新在于引入了重要性引导的MCMC高斯分配策略，通过聚合多视图残差来计算每个高斯点的欠拟合度和冗余度信号。系统利用这些信号构建平滑的重要性加权采样分布，使得高斯点的生成和重定位偏向欠拟合区域，从而在不改基础随机梯度朗之万动力学的前提下，将渲染能力从已拟合良好的区域重新分配到欠拟合区域。SalientGS能够在15分钟内完成端到端重建，并在感知质量上达到最先进水平。◆统一了SfM与3DGS流水线，实现了无需外部预处理的高效端到端三维重建。◆通过多视图残差聚合定义高斯点的重要性信号（欠拟合度与冗余度），实现细粒度的容量分配。◆在保留SGLD框架的基础上，以重要性加权采样分布引导MCMC的生灭与重定位过程，避免了底层动力学修改。</td></tr>
<tr><td>2026-07-12</td><td>Mapping Pamir: Multi-Session Visual-Inertial SLAM and 3D Reconstruction of an Underwater Shipwreck<br><a href='http://arxiv.org/pdf/2607.10925'>论文</a></td><td>本文针对水下船骸等复杂环境的多会话三维重建难题，提出了一套基于低成本运动相机的多会话水下建图框架。该框架将SVIn2视觉惯性SLAM与COLMAP SfM相结合，利用SVIn2生成每段会话的相机轨迹与稀疏重建，再通过COLMAP进行全局优化并生成稠密三维模型。

◆ 创新性地融合了潜水电脑的水深数据与视觉惯性信息，增强了水下场景的尺度估计与几何约束。

◆ 提出利用固定位置的标定靶估计不同会话间的坐标变换矩阵，实现了多会话数据的统一配准。

◆ 首次对巴巴多斯近海Pamir沉船的外部与可进入内部进行完整多会话建图，其中第三会话采用双相机不同视场配置以兼顾全局覆盖与细节捕获。</td></tr>
<tr><td>2026-07-17</td><td>NoDrift3R: Raymap-Guided Coupling for Drift-Robust Unposed Feed-Forward 3D Reconstruction<br><a href='http://arxiv.org/pdf/2607.07168'>论文</a> | <a href='https://xiangyu1sun.github.io/NoDrift3R-project-page/'>代码</a></td><td>该论文针对无位姿前馈三维高斯溅射在长序列中因位姿漂移导致重建质量退化的问题，提出了一种几何与外观显式协同的新框架。作者识别出位姿累积漂移是制约性能的主要瓶颈，并指出SfM伪真值引入传感器噪声、纯渲染监督易陷入局部最优等矛盾。

◆ 提出Raymap-Guided Coupling Module（RGC）模块，将高斯中心锚定到光线图诱导的几何上，在统一目标下联合优化RGB重建、光线图一致性与相机正则化，形成几何与外观之间的双向反馈循环。

◆ 设计Dual-Frequency Viewpoint Scheduling策略，结合由易到难的间隔扩展与短间隔对回放，稳定长时序学习过程。

在域内和跨域数据集上的大量实验表明，该方法在渲染质量与位姿估计上均取得一致提升，长序列鲁棒性显著增强，验证了几何-外观显式协同是实现可扩展、无漂移无位姿前馈三维重建的关键。</td></tr>
<tr><td>2026-07-12</td><td>Deep far-UV observations of the ELAIS N1 field using AstroSat: Source catalogue, spectral energy distribution modelling and star formation<br><a href='http://arxiv.org/pdf/2607.06143'>论文</a></td><td>本文利用AstroSat卫星上的紫外成像望远镜(UVIT)对ELAIS N1深场进行了F154W波段(far-UV)的深度观测,总曝光时间达30千秒,通过CCDLAB v3.0进行数据处理,获得了1637个3σ和458个5σ的FUV源目录,极限星等分别为25.69和25.13 mag(AB),为该天区提供了目前最深的FUV测光数据。

◆ 基于多波段交叉匹配,结合光学和红外数据以及光谱/测光红移,采用多波段判据剔除活动星系核(AGN),构建了清洁的恒星形成星系样本。

◆ 使用CIGALE进行SED建模,采用延迟型恒星形成历史(可叠加晚期暴发)、Bruzual &amp; Charlot恒星 population合成、Calzetti消光和SKIRTOR AGN模块,系统地推导了样本的恒星形成率(SFR)、总恒星质量和年轻恒星质量随红移的演化。

研究发现SFR随红移单调上升,符合恒星形成主序(SFMS)的演化趋势,同时年轻质量与总质量比值在0&lt;z≲0.76范围内近似为常数,表明样本中的星系主要以自调节的稳态恒星形成为主,而非星暴主导的演化模式。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-11</td><td>Multi-Level Evidence Aggregation for Robust Facial Phenotype Retrieval in Rare Genetic Disorder Prioritization<br><a href='http://arxiv.org/pdf/2608.11037'>论文</a></td><td>本文针对罕见遗传疾病的面部表型检索任务，提出了一种推理阶段的多层级证据聚合框架。该框架在不修改现有GestaltMatcher-Arc编码器的前提下，从患者和疾病两个层级整合多源证据，核心创新包括：

◆ 嵌入级患者聚合：融合同一患者的多张图像信息，增强个体表征的鲁棒性
◆ 患者加权的疾病质心表示：整合多个确诊患者的证据构建疾病级全局表征
◆ 混合个体-质心评分机制：结合全局疾病证据与局部近邻信息，提升检索判别力

实验在GMDB v1.1.4多个子集上验证，top-1准确率在GMDB-Freq上从38.52%提升至48.82%，GMDB-Rare上从19.38%提升至23.79%，多图像子集提升尤为显著，分别达到60.94%和26.71%。该方法无需重新训练编码器，推动了面部表型检索从孤立单图匹配向多层级证据聚合的范式转变。</td></tr>
<tr><td>2026-08-10</td><td>XFeat Revisited: Reproducibility and Evaluation of a Lightweight Image Matcher<br><a href='http://arxiv.org/pdf/2608.09519'>论文</a></td><td>本文对轻量级图像匹配方法XFeat进行了系统的可复现性研究。研究者基于论文与补充材料重新实现了网络架构，并独立再评估了作者发布的官方预训练权重，揭示出论文、补充材料与公开代码在骨干布局、融合模块和训练损失等方面存在多处实现差异。复现模型在MegaDepth-1500和ScanNet-1500基准上与原版结果相当，部分情况下甚至更优，验证了XFeat在精度与效率上的良好折中。

◆通过架构消融实验，澄清了原始论文未充分论证的设计选择：并行关键点分支对半稠密匹配确实重要，但其优势程度不如原作者声称的显著；而关于单一跳跃连接最佳放置位置的证据则不充分。

◆在下游任务复现中，单应性估计结果与原文高度一致，但Aachen视觉定位即使使用官方权重也低于论文报告，提示评估流程对未明确说明的细节较为敏感。

◆首次将XFeat拓展至零样本跨域和跨模态匹配场景，涵盖视网膜成像、热红外-可见光以及多模态遥感影像，发现其在一般跨域条件下仍具一定有效性，但在严重模态差异下性能急剧退化。</td></tr>
<tr><td>2026-08-06</td><td>A Low-Latency ASIC Architecture for Real-Time Line Segment Detection<br><a href='http://arxiv.org/pdf/2608.06439'>论文</a></td><td>本文针对嵌入式视觉中线段检测对实时性与低功耗的严苛需求，提出了一种基于步长算法的低延迟ASIC架构。该架构采用全流水线设计，每时钟周期处理一个像素，具有确定性延迟，便于系统级集成。在45nm CMOS工艺下综合后，设计在VGA分辨率下可达325 FPS、Full HD下48 FPS，功耗仅25.54 mW，面积0.412 mm²；频率提升至125 MHz时，VGA帧率可达406 FPS。

主要创新点如下：
◆ 基于寄存器的行缓冲与数据复用机制，有效降低存储访问开销
◆ 无乘法器的MCM滤波器设计，显著简化硬件实现
◆ 8类角度量化策略，减少计算复杂度并提升匹配效率
◆ 类CAM关联存储器，实现单周期快速匹配
◆ 优化的重复线段去除机制，提升输出结果质量

相比基于Line Hough变换的90nm ASIC方案，本设计功耗降低49%，帧率提升超过1.6倍，非常适合自动驾驶、视觉SLAM等边缘计算应用。</td></tr>
<tr><td>2026-08-04</td><td>LoRetta: A Foundation Model and Extensive Dataset for Global-Scale Remote Sensing Dense Image Matching<br><a href='http://arxiv.org/pdf/2608.04106'>论文</a></td><td>该论文针对全球尺度遥感影像密集匹配中存在的几何偏移大、重叠区域不完整等难题,将密集匹配重新建模为&quot;定位-配准&quot;两阶段任务,先定位可匹配区域与仿射几何,再在对齐框架内精化密集残差。

◆ 提出任务范式创新:将密集匹配重构为&quot;定位-配准&quot;流程,通过可匹配性感知仿射定位与引导式密集配准的耦合,有效解决大几何偏移与不可匹配区域导致的预测不可靠问题。

◆ 构建基础模型 LoRetta,融合可匹配性感知仿射定位与引导式密集配准,在 LEVIR-GM 基准上以 83.3% AUC 超越最强基线 RoMa v2 1.6 个百分点,1 像素与 2 像素 PCK 分别提升 6.5 与 8.2 点,同时推理延迟降低 47.8%。

◆ 发布 LEVIR-GM 全球基准,涵盖六大洲、五年时序、0.5-1024 米分辨率的 103K 对齐与 827K 增强光学影像对,并首次提供数据集原生可匹配性标注。

◆ 建立稀疏、半密集与密集匹配器的统一评估协议,并通过航天员-卫星、无人机-卫星地理定位实验验证 LoRetta 作为可复用几何对齐器的跨域迁移能力。</td></tr>
<tr><td>2026-08-04</td><td>SGFormer: Structure-Guided Transformer for Robust Local Feature Matching<br><a href='http://arxiv.org/pdf/2608.03423'>论文</a></td><td>该论文针对局部特征匹配中现有无检测器方法(如LoFTR)在大幅视角变化场景下出现的注意力发散问题,提出了一种新颖的结构引导Transformer网络SGFormer。研究发现,标准Transformer的无约束全局注意力机制会使部分高置信度匹配落在重叠区域之外,降低匹配可靠性。

◆提出Triple-Structure-Attention(TSA)模块,利用网络浅层局部特征强化显著结构区域的特征表达,引导后续Transformer阶段将注意力聚焦于具有显著结构的重叠区域。

◆采用半稠密的由粗到精匹配流水线,自适应地更新显著结构附近的注意力,在提升全局建模能力的同时抑制非重叠区域的干扰。

◆在多个具有挑战性的摄影测量基准数据集上的实验表明,SGFormer有效缓解了注意力发散现象,显著提升了匹配精度与鲁棒性。</td></tr>
<tr><td>2026-08-04</td><td>Double Down on Defense: Strengthening Deep Perceptual Hashes against Evasion Attacks without Retraining<br><a href='http://arxiv.org/pdf/2608.03101'>论文</a></td><td>本文针对深度感知哈希在对抗扰动下易被规避匹配的问题，提出了DualShield防御框架。核心思路是在不重训练、不修改原有模型的前提下，通过匹配流程和参考图预处理两个环节增强鲁棒性。

◆ 匹配时引入随机平滑机制，对扰动后的参考-查询图像对聚合决策，理论上可获得约0.3的ℓ2认证鲁棒半径，保证该范围内的查询扰动无法规避匹配。

◆ 发布前对参考图像添加优化得到的、肉眼难以察觉的扰动进行&quot;硬化&quot;预处理，使后续匹配对对抗攻击天然更具抵抗力。

◆ 采用即插即用设计，可与八种主流深度感知哈希及多种数据集兼容，无需访问或修改底层模型结构，显著降低各类自适应白盒、黑盒及图像变换攻击的成功率，同时保持低碰撞率。

该工作表明，通过改进匹配策略和发布前图像硬化，可在不付出重训练代价的前提下有效提升深度感知哈希系统的安全性。</td></tr>
<tr><td>2026-07-30</td><td>Can Synthetic Data Overcome the Generalization Limits of AI-Based Flower and Pod Detection Across Cowpea Breeding Genotypes and Environments?<br><a href='http://arxiv.org/pdf/2607.28796'>论文</a></td><td>该研究针对豇豆育种中AI视觉模型在不同基因型与环境（G×E）组合下泛化能力下降的问题，系统量化了跨地点、跨季节的花朵和豆荚检测性能衰减，发现花朵检测mAP@50从76.3%降至最低50.6%，豆荚检测对分布漂移更为敏感。为规避逐一标注真实图像的高昂成本，作者提出利用程序化3D模型渲染合成图像替代人工标注的思路，但发现纯合成监督因相机成像差异存在域鸿沟。

◆ 创新点一：提出域鸿沟感知的相机真实感增强策略，通过Wasserstein距离对齐真实图像统计量来度量并优化合成数据与真实域之间的分布差异。

◆ 创新点二：引入线性HDR表示方法，在相同域鸿沟下比8位表示获得更大的检测性能提升，揭示了位深对域迁移增益的关键影响。

◆ 创新点三：证明优化后的HDR合成数据仅需配合少量真实图像即可匹配或超越全真实数据基线的空间泛化效果，并在极低样本量下对豆荚检测收益最大。</td></tr>
<tr><td>2026-07-30</td><td>CXR-Retrieve: Compositional Text-to-Image Retrieval in Chest Radiography<br><a href='http://arxiv.org/pdf/2607.27779'>论文</a></td><td>胸部X光影像库通常只配对自由文本报告，难以高效检索，而现有生物医学视觉语言模型主要针对报告-图像匹配优化，无法满足包含联合与否定等组合约束的临床查询。论文针对这一目标错位问题提出了两项核心贡献。

◆构建了CXR-Retrieve组合检索基准，包含5159张MIMIC-CXR-JPG测试图像和145条覆盖单一发现、联合发现及否定表达的查询，相关性由是否满足所有病理断言决定，而非是否匹配配对报告。

◆提出了标签感知的对比微调目标，吸引病理约束兼容的图像-文本对（包括共享的确认缺席），同时显式排斥矛盾对。

◆基于领域内CXR-CLIP检查点微调后，在双病理联合查询上Precision@5提升8.5个百分点，在否定查询上提升22.0个百分点，证明可靠的胸部X光检索需要建模病理的临床断言方式，而不仅仅是哪些病理被提及。</td></tr>
<tr><td>2026-07-29</td><td>VidMap: Exploiting Temporal Structure for Video-Based Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.27194'>论文</a> | <a href='https://github.com/cvg/vidmap'>代码</a></td><td>本文针对无约束视频的相机标定与度量位姿恢复问题，提出VidMap系统，旨在弥合SLAM与SfM之间的差距。传统SLAM受限于因果增量特性，对初始化和瞬态失败敏感，且通常需要已知相机标定；传统SfM虽支持全局优化但缺乏对时间顺序的利用。作者通过结合SLAM的强序列约束与离线SfM的全局优化灵活性，实现了对任意长视频、无标定输入的度量三维重建。

◆结合SLAM的序列约束与离线SfM的全局优化能力，支持无标定长视频的度量重建。
◆引入宽基线稠密图像匹配技术，提升特征关联的鲁棒性。
◆将时间顺序信息作为一等公民用于可靠回环检测。
◆在全局优化中融合单目度量深度先验，提高重建精度。
◆在极端运动与视觉对称等挑战性场景下，显著优于现有SLAM和SfM方法。</td></tr>
<tr><td>2026-07-29</td><td>Robust RPC Bundle Adjustment for Multi-Date Satellite Imagery with Season-Invariant Correspondences<br><a href='http://arxiv.org/pdf/2607.26973'>论文</a></td><td>针对多日期卫星影像中季节、照度等地表变化导致的跨时相匹配难题，传统基于手工特征的RPC光束法平差方法难以获得稳健的同名点。本文提出一种感知外观的RPC精修流水线，将学习驱动的局部特征匹配与全局图像描述子筛选相结合，以提升无GCP条件下多视图相对RPC精修的精度与效率。该流水线在匹配前对图像对进行兼容性筛选，再以学习特征完成对应构建，从而在异时相集合上兼顾了连接的完整性与匹配的可靠性。◆ 采用学习型局部特征匹配获取对季节变化稳健的同名点对应，解决异时相图像间传统手工特征匹配易失效的问题。◆ 引入全局图像描述子选择视觉兼容的图像对，剔除冗余和易错匹配，同时保持匹配图的整体连通性。◆ 在39至42视图的季节多样WorldView-3影像集上验证，方法在几何一致性误差和匹配耗时两方面均优于现有开源基线，使多日期卫星影像的RPC精修更加鲁棒高效。</td></tr>
<tr><td>2026-07-26</td><td>Robust 6-DoF Object Pose Tracking with Built-In Recovery under Occlusions and Rapid Object Motions<br><a href='http://arxiv.org/pdf/2607.23468'>论文</a></td><td>本文针对RGB-D数据下6-DoF物体位姿跟踪中面临的全遮挡和快速运动导致跟踪失败的难题，提出了一种融合学习关键点匹配与优化对齐的鲁棒跟踪方法。该方法在易跟踪场景下达到当前最优精度，同时保持57.6 FPS的实时性能，并在遮挡和快速运动等挑战性条件下表现出最强的鲁棒性。

◆ 提出一种结合学习式关键点匹配与优化式对齐的高效跟踪框架，实现对未见物体的6-DoF位姿估计。

◆ 引入新颖的失败检测与恢复模块，实时监测位姿可靠性，识别跟踪发散或遮挡状态。

◆ 设计全局重检测与位姿估计步骤，对恢复候选进行严格验证后再恢复跟踪，实现自动重初始化。

◆ 发布了一个包含遮挡和快速运动场景的新数据集，用于评估该类挑战性条件下的跟踪性能。</td></tr>
<tr><td>2026-07-21</td><td>NGPS: GPS-Denied Aerial Geo-Localization and 2.5D Reconstruction via Deep Satellite Image Matching and Multi-Rate Sensor Fusion<br><a href='http://arxiv.org/pdf/2607.18936'>论文</a> | <a href='https://github.com/snktshrma/ngps_flight'>代码</a></td><td>本文提出NGPS框架，一种面向高空无人机的视觉地理定位系统，通过深度特征将下视图像与地理参考卫星影像匹配，在GPS拒止环境下实现绝对定位。

◆ 提出自适应置信度加权UKF融合方法，利用RANSAC内点率、重投影误差和匹配置信度动态调制协方差。
◆ 基于VIO速度预测卫星影像搜索区域，实现速度预测式核提取，提升匹配效率与鲁棒性。
◆ 设计异步多速率时间优先级队列，将绝对位姿（1-2Hz）、VIO（10-20Hz）与IMU（100-200Hz）按时间顺序交错融合。
◆ 结合VINS位姿图全局优化与NGPS锚定校正，实时生成2.5D地理参考正射镶嵌图。

在60-150米高度的5组飞行实验中，系统达到2.94米位置RMSE，相较单目VIO提升3.5倍最差情况绝对轨迹误差为6.04米，且可在Jetson Orin NX上实时运行。</td></tr>
<tr><td>2026-07-15</td><td>Breaking Déjà Vu: Independent Auditing of Visual Place Recognition through Vision-Language Reasoning<br><a href='http://arxiv.org/pdf/2607.12818'>论文</a></td><td>本文针对视觉位置识别（VPR）在机器人SLAM应用中因依赖固定阈值而难以应对环境变化、易接受错误闭环的问题，提出了视觉位置识别审计（VPR Auditing）这一独立的后检索验证框架。该方法利用视觉语言模型（VLM）对查询图像和候选图像进行联合推理，实现实例级匹配验证，摆脱了对特定架构置信度、数据集阈值和部署环境先验知识的依赖。

◆ 提出独立审计框架：将验证环节与原始VPR检索解耦，作为后处理模块独立审计检索结果，无需修改现有VPR系统。
◆ 基于VLM的联合推理机制：通过对查询-候选图像对的语义级推理进行匹配评估，具备跨场景泛化能力。
◆ 全面性能提升：在六个基准数据集、五种VPR方法和四种VLM上的实验表明，平均recall@1提升13.6%，误接受率降至12%，精度保持在95%以上，覆盖率超过75%，显著优于现有验证方法。</td></tr>
<tr><td>2026-07-07</td><td>MiLSD: A Micro Line-Segment Detector for Resource-Constrained Devices<br><a href='http://arxiv.org/pdf/2607.06600'>论文</a></td><td>针对MCU级资源受限设备上线段检测的挑战，本文提出MiLSD系统，在亚兆字节内存预算内最大化检测精度，并系统研究表征方式、量化位宽与后处理策略之间的权衡关系。

◆提出F-Clip线段表示方法，将线段建模为中心点结合长度与角度参数，在紧凑全卷积骨干下学习效率优于其他表示形式。

◆系统对比三种输出表示与不同位宽量化方案，发现8位量化基本保持全精度性能，4位量化在角度回归上退化严重，量化感知训练仅能部分恢复。

◆融合子像素解码、测试时增强与轻量级验证器等推理增强技术，将ShanghaiTech Wireframe数据集sAP10从0.25MB模型下的10.6提升至1MB预算下的24.1。

◆首次绘制了嵌入式视觉系统中表征方式、量化位宽、模型容量与后处理策略多维度的精度-内存权衡全景图，为后续微小型线段检测器设计提供参考。</td></tr>
<tr><td>2026-07-06</td><td>Hybrid Deep Learning for Traceability and Classification of Industrial Slate Tiles<br><a href='http://arxiv.org/pdf/2607.04811'>论文</a></td><td>这篇论文针对板岩瓦片工业生产中的实例重识别与产地分类问题,提出了一种轻量级混合深度学习框架,将图像匹配与分类任务统一在单一架构中。研究者构建了一个包含2610张图像、涵盖6个开采场地的板岩瓦片工业数据集,填补了该领域公开数据的空白。在实例匹配分支中,采用XFeat特征提取与LightGlue匹配头相结合,使匹配性能AUC提升15.4%。在分类分支中,通过共享并融合两个骨干网络的特征,相较标准MobileNetV3准确率提升10.9%。实验结果验证了所提方法在工业场景下对自然材料视觉变异的鲁棒性和实用性。

◆ 提出统一的混合深度学习框架,将特征匹配与分类任务融合于单一架构
◆ 利用XFeat与LightGlue组合实现工业级实例重识别
◆ 设计双骨干特征共享与融合机制以提升分类精度
◆ 构建首个板岩瓦片工业数据集(2610张图像,6个产地)</td></tr>
<tr><td>2026-07-03</td><td>A Vision Based System for Guided and Collaborative Reconstruction of Fragmented Documents<br><a href='http://arxiv.org/pdf/2607.03621'>论文</a></td><td>本论文提出了一种基于视觉的协作式碎片文档实时重建系统,用于文化遗产保护中的破损纸质文档复原。系统采用协作机器人配合专门设计的真空吸附装置,能够轻柔精准地定位纸片,对8平方厘米的碎片实现0.57毫米的定位重复精度,有效避免对脆弱文物的损伤。该系统支持两种工作模式:人工操作结合视觉引导,以及机器人全自动定位,为使用者提供灵活的交互选择。研究者系统评估了多种局部特征匹配方法在不同文档类型、旋转缩放及破损程度下的表现,发现无检测器的SE2-LoFTR方法在受损及光学变异的档案材料上表现出最强的鲁棒性。论文的主要创新点可概括如下:

◆ 设计了专用真空吸附末端执行器,使协作机器人能够安全处理易碎的纸质文物碎片,实现毫米级精确定位。

◆ 构建了人机协作的双模式重建框架,支持视觉辅助手动操作与全自动重建灵活切换。

◆ 系统比较了多种特征匹配算法在碎片拼接任务中的性能,验证了SE2-LoFTR对受损和光学退化文档的优越鲁棒性,为实际应用提供了方法选择依据。</td></tr>
<tr><td>2026-07-01</td><td>AnyMatch: Supercharging Universal Multi-Modal Image Matching with Large-Scale Single-View Images<br><a href='http://arxiv.org/pdf/2606.31077'>论文</a></td><td>◆论文提出AnyMatch框架，用低成本、易获取的单视图图像生成多视角、多模态图像匹配训练数据，缓解真实大规模标注数据稀缺问题。
◆方法结合单目深度估计、显式3D重投影、扩散式修复和跨模态图像翻译，同时保证外观多样性与几何一致性。
◆其标注由3D重投影直接产生，避免了传统SfM-MVS流程中的误差累积，更适合训练精确匹配模型。
◆AnyMatch具备强可扩展性，可通过输入图像、相机参数和视角设置控制场景多样性与匹配难度。
◆基于该框架构建的Any-syn数据集显著提升LoFTR、EDM、RoMa等模型在多模态匹配基准上的泛化性和鲁棒性。</td></tr>
<tr><td>2026-06-29</td><td>MF-UAVPose6D: A Model-Free Monocular 6-DoF Pose Estimation Framework for Fixed-Wing UAVs<br><a href='http://arxiv.org/pdf/2606.29697'>论文</a></td><td>◆ 提出MF-UAVPose6D，一个面向固定翼无人机的无模型单目6-DoF位姿估计框架，推理时仅需RGB图像和相机内参，无需CAD模型或关键点先验。
◆ 通过热图引导的中心定位获得稳定目标锚点，提升非合作目标在复杂视角和远距离条件下的检测与定位可靠性。
◆ 设计Perspective-Aware Module建模观测射线先验，使网络更好理解单目成像中的透视几何关系。
◆ 引入Dynamic Topological Sampling，补充机翼、机身、尾翼等弱结构线索，增强对固定翼外形拓扑的利用。
◆ 采用平移与旋转解耦的位姿解码机制，并构建FW-UAV6DPose合成数据集；实验表明该方法在旋转估计、深度恢复和整体位姿评估上兼具精度、效率与鲁棒性。</td></tr>
<tr><td>2026-06-26</td><td>KM-Speaker: Keypoint-Based Style Control for High-Quality Speech-Driven 3D Facial Animation and Dialogue Localization<br><a href='http://arxiv.org/pdf/2606.28568'>论文</a></td><td>◆ KM-Speaker提出一种基于关键点条件的流式生成框架，用参考表演同时实现全局风格引导和逐帧级表情控制。
◆ 该方法面向高质量语音驱动3D面部动画，解决现有可控模型依赖低质量野外数据而损害真实感的问题。
◆ 论文设计了解耦策略，将音频驱动的唇部运动与关键点驱动的上半脸动态分离，提升唇同步与表情控制精度。
◆ 通过全局风格上下文保持机制，模型能在细粒度控制下维持完整面部表现的一致性和连贯性。
◆ 实验表明，KM-Speaker在数据受限场景下仍优于现有方法，尤其在唇同步、风格遵循和对话本地化的时序表情匹配方面表现突出。</td></tr>
<tr><td>2026-07-01</td><td>SOCO: Benchmarking Semantic Object Correspondence in Vision Foundation Models<br><a href='http://arxiv.org/pdf/2605.31597'>论文</a></td><td>本文提出SOCO基准，旨在解决视觉基础模型中结构化对象理解评估协议不一致和部件级监督有限的问题。
◆构建了包含对应类型分类法的语义对象对应基准，在100个类别和超百万对应对上提供一致且具功能意义的关键点标注。
◆引入关键点语言描述，支持对大型视觉语言模型细粒度部件级理解能力的系统评估。
◆揭示视觉骨干网络虽编码强语义结构，但跨类别迁移对应能力差且仅部分捕获部件位置。
◆发现大视觉语言模型擅长文本提示定位但视觉参考跨图匹配较弱，暴露语言接地与视觉对应间的鸿沟。
◆证明对应性能比ImageNet分类性能更能强有力地预测分割、跟踪及3D检测等密集下游任务的表现。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-17</td><td>Calibration-Free Vehicle Speed Estimation: A Monocular Keypoint-Template Approach<br><a href='http://arxiv.org/pdf/2608.16785'>论文</a></td><td>该论文提出了一种无需标定的单目车辆测速框架，能够从普通视频中可靠地估计车速，且不依赖道路特征、相机标定或参照物，显著降低了部署成本。

◆ 基于36关键点车辆模板与逐帧更新的单应性矩阵，将像素位移投影到度量空间，实现无需标定的速度估计。

◆ 提出了两种互补的测速策略：纯关键点跟踪方法与结合密集空间聚合的扭曲光流方法，后者精度更高。

◆ 采用YOLO关键点检测模块，在多源数据集上训练，提升了对不同视角和车辆外观的鲁棒性。

◆ 在VS13和BrnoCompSpeed等公开数据集上，扭曲光流方法MAE分别达到15.0%和9.7%，去除外缘异常后降至11.7%和7.6%。

该工作突破了现有视觉测速方法对道路条件和标定的依赖，为行车记录仪和智能手机等便携设备支持的低成本交通执法与公众参与式监督提供了可行方案。</td></tr>
<tr><td>2026-08-15</td><td>SAGE-OR: Semi-supervised Adaptive Scene Graph Generation for Operating Rooms<br><a href='http://arxiv.org/pdf/2608.15336'>论文</a></td><td>现有手术场景图生成方法依赖密集多模态标注和专用硬件，导致数据成本高昂且现有基准局限于仿真环境。本文提出特征为中心的SAGE-OR框架，在4D-OR基准上以76% F1匹配全监督基线，加入手部增强后提升至86%，与需密集监督的SOTA方法仅差4个百分点。

◆ 将传统&quot;先检测后推理&quot;范式解耦为&quot;表征-推理&quot;范式，利用冻结基础模型将定位信息隐式编码于预计算特征中，完全消除定位监督需求。

◆ 采用基于通用分割提示的半监督策略，通过提示驱动实现无监督上下文增强，可灵活加入手部等未标注实体，仅以提示级修改即可适配新类别。

◆ 部署1500万参数轻量图变换器进行关系推理，训练仅需1.4小时，推理约1ms每帧，峰值内存低于2GB，适合手术室边缘设备运行。</td></tr>
<tr><td>2026-08-10</td><td>CableDex: Cable Length Estimation on Industrial Reels Using a Handheld Device<br><a href='http://arxiv.org/pdf/2608.09392'>论文</a></td><td>CableDex是一种基于计算机视觉的电缆长度自动测量系统，仅需通过手机拍摄单张照片即可估算工业卷盘上的电缆长度，取代了传统耗时且不准确的手工测量方式。该系统整合了相机标定、实例分割、姿态估计和体积计算四个核心模块，能够适应五种不同卷盘类型和多种电缆规格。团队基于1000张人工标注图像训练了实例分割模型，在测试中达到99.5%的mAP50，且推理时间仅5.66毫秒。在75个卷盘上的工业数据验证后，系统实现了4.90%的平均绝对百分比误差，满足行业通常接受的10%误差容限要求。

◆提出端到端的移动视觉测量流程，将相机标定、实例分割、姿态估计与体积计算无缝集成，实现从图像采集到长度估算的全自动化处理。
◆构建高精度实时实例分割模型，在自建数据集上达到99.5%的mAP50，单图推理仅需5.66毫秒，兼顾精度与运行效率。
◆实现跨卷盘类型和电缆规格的强泛化能力，在五种卷盘类型上测量误差仅4.90%，优于行业10%的容差标准。</td></tr>
<tr><td>2026-08-01</td><td>Self Supervised Learning from Automatically Generated Demonstrations for Visual Robotic Manipulation<br><a href='http://arxiv.org/pdf/2608.07553'>论文</a></td><td>本文提出了一种面向视觉机器人操作的自监督学习方法，核心思想是让机器人围绕目标位姿自动生成演示数据，并直接从腕部RGB图像中学习相对位姿修正，从而摆脱传统方法对人工示教和标定的依赖。

在数据采集层面，系统利用ROS 2与Isaac Sim自动生成带有位姿标签的图像-位姿对，无需显式的相机-机器人外参标定，并分别为平面精修和三维粗接近阶段构建了独立数据集。

控制策略上采用由粗到精的两阶段框架，先利用含高度变化训练的三维模型完成物体接近，再使用平面数据训练的模型进行最终对齐。

在仿真实验中，平面精修阶段将最终位姿分散度从9.69毫米降低至5.38毫米；真实UR5e机器人上对三个物体的端到端抓取实验在两种无旋转工况下分别取得66.6%和63.3%的成功率。

主要创新点包括：

◆ 提出机器人自主生成演示数据的自监督流程，无需人工遥操作或示教即可获得标签化训练样本。

◆ 利用系统级同步机制规避显式手眼外参标定，降低了实际部署的工程门槛。

◆ 设计粗到精双网络架构，分别针对三维接近和平面精修任务训练专用模型。

◆ 仅依靠单帧腕部RGB图像直接回归相对平移与旋转，简化感知链路。</td></tr>
<tr><td>2026-08-06</td><td>Toward surface-based registration of a virtual preoperative cutting guide onto the mandible for reconstruction surgery<br><a href='http://arxiv.org/pdf/2608.06599'>论文</a></td><td>本论文提出一种基于表面配准的无标记增强现实方法,将术前虚拟切割导板注册到下颌骨上,以替代传统的3D打印实体导板,降低成本与制作时间,并避免术中灭菌失败的问题。该方法利用HoloLens 2飞行时间相机采集术中部分点云,通过牙齿加权全局配准和非对称点对面ICP精配准两阶段流程,完成CT下颌模型与术中深度数据的刚体对齐,并将导板变换到HoloLens世界坐标系中以实现动态跟踪显示。

◆ 提出面向经口入路下颌重建的无标记AR切割导板注册方案,利用牙齿作为最具辨识度的可见表面特征,扩展了表面配准的适用场景。
◆ 设计两阶段配准策略:牙齿加权截断最小二乘全局对齐结合非对称点对面ICP精配准,无需安装标记点或手动选点。
◆ 建立了包含30个靶点配准误差测点的盲法幻影评估协议,系统评估全暴露、中等暴露和仅牙齿暴露三种条件下的精度。
◆ 报告了不同暴露条件下中位TRE分别为4.05、6.10、7.10 mm,显示延迟0.805秒,为AR替代实体打印导板提供了可量化的可行性证据。</td></tr>
<tr><td>2026-08-05</td><td>Beyond Reprojection Error: Camera Calibration with 3D Targets<br><a href='http://arxiv.org/pdf/2608.05066'>论文</a></td><td>本文提出了一种基于场景光线预测的相机标定框架,突破了传统二维平面标定的局限,适用于三维重建任务。作者推导了重建误差和交点误差两种基于光线的新型度量,结合自助法统计评估不同标定对象和标定流程,用于内外参标定。

主要创新点如下:

◆ 提出基于场景光线预测的标定框架,可灵活集成先进相机模型,并采用广义畸变模型更准确地刻画真实相机的物理效应。

◆ 引入重建误差和交点误差作为新的标定评价指标,证明传统重投影误差可能是三维精度的误导性指标,光线度量提供更全面的评估。

◆ 设计了一种正二十面体标定靶配合环形特征检测器,合成数据上平均交点误差降低约40%,且自助法试验中标定结果更稳定。

实验表明广义畸变模型在标定精度上优于传统模型,但实际数据应用需依赖极高的制造精度。</td></tr>
<tr><td>2026-08-05</td><td>Differential 6-DOF Pose Estimation with Provable First-Order Immunity to Camera Calibration Errors<br><a href='http://arxiv.org/pdf/2608.04673'>论文</a> | <a href='https://github.com/zyoungszu/pami2026'>代码</a></td><td>本文提出一种差分6自由度位姿估计方法，直接由帧间图像位移与已知3D控制点恢复平台运动，避免了传统3D-2D方法对外参标定误差的敏感性。主要创新点包括：
◆通过差分透视投影方程与深度不变性近似，在SE(3)流形上建模运动，无需逐帧独立求解绝对位姿，并支持单目与多相机系统；
◆理论上证明平移外参误差可精确抵消，旋转外参误差仅引入受标定误差、运动幅度和观测几何共同约束的有界扰动，实现一阶标定误差免疫；
◆推导通用可观测性条件、Cramér-Rao下界及无偏一致性估计器，并明确近似有效性的适用边界。
大量合成与真实实验表明，该方法在精度、鲁棒性和效率上均显著优于代表性PnP与广义PnP方法，单目求解器仅需5个控制点即可在0.5像素噪声下达到10.09角秒旋转RMSE和3.70毫米平移RMSE，双目求解器运行时间仅0.27毫秒。</td></tr>
<tr><td>2026-07-27</td><td>Lindblad-Inspired Multi-Timescale Reservoir Computing with Separable Rotation and Dissipation<br><a href='http://arxiv.org/pdf/2608.04028'>论文</a></td><td>本文提出了一种受Lindblad方程启发的多时间尺度回声状态网络，通过将开量子系统动力学原理与结构化状态空间建模相结合，解决了传统储层中信号混合、记忆保持与稳定性耦合在单一随机矩阵中的问题。核心思想是将循环算子分解为精确离散化的阻尼旋转模态，使旋转（控制相位混合）与衰减（控制记忆丧失）成为相互独立的设计变量。

◆ 基于精确离散化阻尼旋转模态构建循环算子，将旋转与衰减解耦为两个独立可调的设计变量，分别控制相位混合与记忆丧失。

◆ 通过正交模混合保持矩阵法向性，使衰减谱直接决定回声状态稳定边界，无需后验谱半径缩放即可获得全局稳定性保证。

◆ 引入受Lindblad开放系统动力学启发的结构化储层设计框架，使混合、记忆、稳定性成为显式且可独立调控的物理量。

实验表明，该方法在十组对齐种子下，在有界NARMA-20上取得最佳固定储层性能，在Lorenz-63上获得最低平均误差，并在多种基准上保持竞争力；消融研究证实旋转增强状态多样性，耗散提供受控遗忘并改善预测条件。</td></tr>
<tr><td>2026-08-03</td><td>CalibBEV: LiDAR-Camera Calibration via BEV Alignment<br><a href='http://arxiv.org/pdf/2608.02309'>论文</a></td><td>这篇论文提出CalibBEV，一种基于鸟瞰图(BEV)对齐的激光雷达与相机外参标定新方法，核心思想是将两种异构传感器数据统一到共享的BEV三维空间表示中，从而实现精确且鲁棒的跨模态标定。

◆ 创新点一：构建统一BEV空间表征，利用模态专用网络分别从图像和点云中提取BEV特征，为跨模态几何对齐提供共同表达基础。
◆ 创新点二：提出两阶段对齐策略，先隐式回归粗标定矩阵，再显式将一种模态的BEV特征对齐到另一种，逐步精化标定结果。
◆ 创新点三：借鉴CLIP对比学习思想设计损失函数，约束两模态BEV特征在统一语义空间中对齐，有效缓解跨模态语义鸿沟。

在KITTI和nuScenes基准上的实验表明，该方法将相对旋转误差分别降低51%和68%，相对平移误差降低80%和91%，全面超越现有基于点-像素匹配的方法，达到当前最优标定精度。</td></tr>
<tr><td>2026-08-03</td><td>Multi-View Unified Camera Fields: Geometry-Shaped Action-Facing Representations for RGB-Only Multi-Camera VLA Policies<br><a href='http://arxiv.org/pdf/2608.01826'>论文</a></td><td>本文提出Multi-View Unified Camera Fields (MVUCF)，一种仅在训练阶段生效的多视角视觉-语言-动作模型框架，旨在解决现有方法将多相机token简单拼接导致动作表征缺乏度量深度且跨视角不一致的问题。其核心思想是在不同相机之间构建共享的、面向动作的潜在场，将几何信息直接注入到动作模块所使用的隐藏状态中。

◆构建跨视角共享的动作导向潜在场，形成几何一致的多视角统一表征。
◆设计坐标查询的深度目标，使度量深度可从隐藏状态中恢复。
◆提出预处理感知的对应目标，对齐不同相机下观测同一物理点的token。
◆训练阶段注入几何，部署时移除深度、校准及辅助头，原始RGB图零额外推理开销。

在GR00T-N1.6设置下，MVUCF在LIBERO上达到98.9%，LIBERO-Plus提升22.4分，并在覆盖触碰、移动放置与接触交互三类动作的六个RoboTwin任务上平均提升23.3分，真实人形机器人实验进一步验证了其RGB-only部署的实用价值。</td></tr>
<tr><td>2026-07-29</td><td>VidMap: Exploiting Temporal Structure for Video-Based Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.27194'>论文</a> | <a href='https://github.com/cvg/vidmap'>代码</a></td><td>本文针对无约束视频的相机标定和度量位姿恢复问题,分析了现有SLAM和SfM方法的局限性:SLAM对初始化敏感且通常需要已知标定,而传统SfM忽略图像时序信息,在视觉对称性和极端运动下鲁棒性差。论文提出VidMap系统,融合SLAM的强时序约束与离线SfM的全局优化灵活性,首次实现对任意长视频进行度量重建而不依赖标定参数。

◆ 将时序顺序作为一等公民用于可靠的回环闭合,克服视觉对称性和极端运动导致的误匹配

◆ 引入宽基线稠密图像匹配技术,提升帧间对应关系估计的精度和鲁棒性

◆ 在全局优化中融合单目深度先验约束,实现无标定视频的度量尺度重建

◆ 综合采用全局捆绑调整策略,兼顾SLAM的因果稳定性和SfM的全局最优性

在多个具有极端运动和视觉对称性的数据集上的实验表明,VidMap在鲁棒性和精度上均显著优于当前最先进的SLAM和SfM方法,无论相机标定是否已知。</td></tr>
<tr><td>2026-07-24</td><td>Metric Surface Reconstruction of Neurosurgical Scenes from Monocular Operating Microscope Images and Microscope Pose<br><a href='http://arxiv.org/pdf/2607.22773'>论文</a></td><td>本文提出了一种基于单目手术显微镜图像与导航系统提供的显微镜位姿数据来恢复神经外科术野度量级三维几何结构的方法。研究团队在体模实验中，利用ZEISS Pentero 800显微镜与Brainlab颅脑导航系统采集同步图像与位姿信息，在内外参标定后采用预训练的Depth Anything 3基础模型进行深度估计，再经点云融合与泊松曲面重建获得三维表面，并与结构光扫描和CT结果进行对比验证。实验结果表明，深度术野体模重建精度在1.95–2.33 mm之间，直接暴露表面体模精度可达1.02–1.52 mm，达到毫米级重建水平。

核心创新点如下：

◆ 提出将常规单目显微镜视频与导航系统位姿数据相结合的无需专用硬件改造的度量级三维重建流程。

◆ 首次将基础深度估计模型（Depth Anything 3）零样本应用于神经外科术野重建，验证了无需任务特定微调的可行性。

◆ 将该方法用于术野暴露的客观量化评估、图像融合及工作空间表征，为未来手术器械设计与术中导航增强提供了技术基础。</td></tr>
<tr><td>2026-07-22</td><td>Calibration-Free 3D Multi-Camera People Tracking for Indoor Environment<br><a href='http://arxiv.org/pdf/2607.22731'>论文</a></td><td>本文针对多相机行人跟踪中传统手动标定效率低下的问题，提出了一种无需标定的统一3D多相机行人跟踪框架。该系统融合了YOLOX无锚框检测、BoT-SORT鲁棒跟踪、OsNet外观特征、HRNet姿态估计以及VGGT视觉几何变换器等多类深度基础模型，实现从原始视频直接推断三维几何结构。

◆ 提出基于VGGT的无标定三维重建方法，直接从视觉数据恢复场景几何，避免对内外参标定矩阵的依赖。

◆ 设计姿态引导的三维提升策略，将头部关键点投影至重建流形上，取代传统地面单应性投影方案。

◆ 引入基于外观-几何联合代价与速度门控的分层聚类算法，实现跨相机的全局身份关联。

◆ 在AI City Challenge 2024数据集上取得53.13%的HOTA分数，为纯视觉三维跟踪建立了强基线。

该工作为大规规模无约束视频档案的自动化三维行人跟踪提供了新的解决思路。</td></tr>
<tr><td>2026-07-23</td><td>TransBiolab: A Real-World Multi-View Dataset of Cluttered Transparent Biomedical Objects<br><a href='http://arxiv.org/pdf/2607.21071'>论文</a> | <a href='https://dualtransparency.github.io/TransBiolab/'>代码</a></td><td>TransBiolab针对自主生物医学实验室中透明塑料器皿的视觉感知需求,发布了一个真实场景的RGB-D数据集,填补了现有透明物体数据集中多目标杂乱堆叠、遮挡与多视角标定联合评估的空白。该数据集包含来自98个场景的161,315帧图像和约103万条实例标注,涵盖15类实验室物品,提供6D位姿、完整与可见掩码、深度图及逐帧相机标定信息。

◆ 首次构建真实世界杂乱堆叠透明生物医学物体的多视角标定数据集,综合了多目标、遮挡与多视角采集的真实实验室操作场景特征。

◆ 沿物体类别、帧内物体数量和相机视角三个难度维度组织数据,便于系统性评估模型在不同操作复杂度下的表现。

◆ 提供大规模细粒度标注(6D位姿、掩码、深度、标定),支撑分割、深度估计与补全、6D位姿估计及多视图推理等多任务基准测试。

◆ 配套发布系统级机器人操作评估流程,使数据集可直接服务于透明器皿抓取与操控等实际应用验证。</td></tr>
<tr><td>2026-07-20</td><td>Two-Stage Extrinsic Calibration of a Static Line-Scanning Lidar with a Rotary Platform<br><a href='http://arxiv.org/pdf/2607.18578'>论文</a></td><td>本论文针对静态线扫描激光雷达与旋转平台组合系统中的外部标定难题展开研究。核心贡献是提出两阶段标定方法，分别在静态和动态条件下自动估计旋转平台轴线相对于激光雷达坐标系的变换关系。该方法解决了工业精密扫描与检测场景中三维点云重建的关键问题，因为任何轴线标定误差都会直接导致物体几何失真。研究通过自制旋转平台与FMCW激光雷达采集的真实数据集进行了系统验证，并深入分析了算法在不同初始条件下的收敛特性。论文特别强调在静态配置下识别旋转轴的精确变换，这是构建高质量三维点云的前提。

◆ 提出两阶段(静态与动态)外部标定框架，自动估计旋转平台轴线在激光雷达坐标系下的变换关系，无需人工精确测量初始位姿。
◆ 在真实FMCW激光雷达与自制旋转平台上进行实验验证，系统评估了算法在不同初始条件下的收敛性与鲁棒性。
◆ 解决了线扫描激光雷达仅能在固定平面内获取距离与方位信息、必须依赖相对运动实现三维感知时的轴线精确标定难题。</td></tr>
<tr><td>2026-07-13</td><td>Why Low-Light Cameras Go Color Blind: Removing Color Bias in Raw Denoising<br><a href='http://arxiv.org/pdf/2607.11090'>论文</a></td><td>本文针对低光条件下的原始图像去噪任务,提出了一种无需相机校准的通用去噪框架。研究发现黑电平误差引起的颜色偏差是导致去噪性能下降和严重色偏的主要原因,这一发现为盲去噪问题提供了新的视角。◆ 提出了一个偏置估计网络,将黑电平误差作为全局特征从噪声输入中预测出来,从而实现相机无关、无需校准的低光原始图像去噪。◆ 在ELD、SID和LRID等多个数据集上取得优于现有盲去噪方法的性能,尤其在颜色校正方面表现突出,在某些情况下甚至可与需要更强监督的方法相媲美。◆ 揭示了广泛使用的SIDD数据集的ground-truth存在显著颜色偏差,会导致训练模型产生不真实的颜色还原。◆ 提出了一种新的ground-truth提取框架,以解决SIDD数据集中的颜色偏差问题,并在修正后的数据集上对现有方法提供了新的基准评测。</td></tr>
<tr><td>2026-07-15</td><td>Unsupervised Detection of Entry and Exit Regions from Vehicle Trajectories for Camera-Agnostic Turning Movement Counts<br><a href='http://arxiv.org/pdf/2607.10949'>论文</a></td><td>本文针对交叉口转向流量计数中人工标注成本高的问题，提出了一种基于车辆轨迹的无监督出入口区域检测流水线。该方法通过聚类轨迹的起点和终点位置，生成持久的空间区域多边形，未来轨迹可通过点-多边形包含关系以线性复杂度进行分类，避免了传统轨迹聚类方法每次重新执行的问题。

◆提出无需人工标注、相机标定或先验几何知识的无监督流水线，仅利用目标检测与多目标跟踪得到的原始轨迹即可识别出入口区域。
◆将区域识别转化为对轨迹起终点的位置聚类，生成持久的区域多边形，显著降低分类计算成本并提升跨视角稳定性。
◆设计包含六个可配置步骤的完整流水线框架，并通过对19152次执行的系统统计分析，识别出三个始终显著的关键参数，给出经验性推荐配置。
◆在印度班加罗尔25个相机（含16个未见过的位置）和UA-DETRAC数据集上实现约3%的中位分类误差，GEH指标符合工程标准。
◆验证了至少60分钟的校准片段结合高峰时段交通选取可进一步提升区域估计质量，证实了方法的实用性。</td></tr>
<tr><td>2026-07-12</td><td>Projection-Domain Sensitivity Analysis of Vertebral DRRs Under Intrinsic Calibration Perturbation<br><a href='http://arxiv.org/pdf/2607.10551'>论文</a></td><td>本文针对椎体透视成像中的几何标定问题,系统评估了内参标定扰动对投影域一致性的影响。研究采用基于CT的椎体模型与受控锥束成像几何,生成真实与扰动标定下的DRR对,通过解剖标志位移、轮廓距离、剪影重叠、图像相似度及2D-3D配准精度等多维指标,定量分析AP与LAT视图下的投影变化。

◆ 提出基于合成框架的投影域标定敏感性分析方法,弥补传统重建域重投影误差指标的不足,为标定鲁棒性评估提供新视角。

◆ 揭示了标定敏感性的强视角依赖性,发现LAT投影在形变与解剖位移上比AP投影更为显著,明确了脊柱成像中多视角标定的差异化要求。

◆ 证实微小内参扰动即可显著降低下游2D-3D配准的旋转对齐精度,建立了标定质量与配准性能之间的直接定量关联,有助于提升图像引导脊柱手术的可靠性。</td></tr>
<tr><td>2026-07-06</td><td>From Fixed to Free Cameras: Calibration-Free View-Robust Vision-Language-Action Model<br><a href='http://arxiv.org/pdf/2607.05396'>论文</a> | <a href='https://alibaba-damo-academy.github.io/CamVLA/'>代码</a></td><td>该论文针对真实机器人部署中相机位置经常变化的问题,指出现有VLA策略依赖显式相机外参,导致在视角变化时脆弱难用,提出策略应自主推断相机位姿而非被告知。针对这一痛点,论文提出CamVLA模型,其核心思想是将操控控制与相机几何解耦。模型同时预测相机坐标系下的末端执行器动作以及6自由度手眼矩阵,通过确定性几何变换将两者合成为机器人基坐标系下的动作。该方法实现了免标定、免深度、单视角,部署时仅需单张单目RGB图像和任务指令。仿真与真实机器人实验均表明,CamVLA在多种未见视角下均能稳定提升任务成功率。

◆ 创新点一:提出相机中心化的动作表征方式,直接在相机局部坐标系下预测末端执行器动作,实现与相机几何的解耦。

◆ 创新点二:联合预测6自由度手眼矩阵,使策略能够自主推断相机相对机器人基座的位姿,无需外部标定。

◆ 创新点三:通过确定性几何变换将姿态无关的动作与相机位姿估计组合,实现真正免标定、免深度、单视角的部署范式。</td></tr>
<tr><td>2026-07-02</td><td>Bridging 3D Gaussians and Semantic Occupancy for Comprehensive Open-Vocabulary Scene Understanding from Unposed Images<br><a href='http://arxiv.org/pdf/2607.01633'>论文</a></td><td>该论文提出COVScene框架，旨在从无位姿的稀疏图像中实现全面的3D场景理解，涵盖可渲染几何、开放词汇语义及自由/占用空间预测。核心思想是将可渲染的高斯原语与密集语义占据场通过可微分体素化在训练计算图中进行耦合，使体素正则化能够反向传播梯度到高斯的不透明度、几何和语义特征。

◆ 提出可微体素化提升机制，将语义高斯在训练图内提升为体素，无需外部相机标定即可实现无位姿重建与体素级正则化协同优化。

◆ 设计语义感知的几何Transformer与多任务高斯解码器，联合预测几何与多任务特征。

◆ 引入几何基础模型蒸馏和占据熵正则化，在没有直接体素监督的情况下提升语义占据预测能力。

◆ 在单一表示中同时支持新视角合成、开放词汇语义查询和语义占据预测三项任务，并在ScanNet和ScanNet++上取得竞争性渲染质量、更好的开放词汇分割与更强的语义占据预测效果。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-18</td><td>Differentiable Voronoi Ray Tracing Beyond Rasterization Speeds<br><a href='http://arxiv.org/pdf/2608.17682'>论文</a></td><td>该论文提出了VoroTracing，一种基于可微分Voronoi光线追踪的实时新视角合成方法，打破了射线渲染无法达到实时速度的传统假设。作者系统分析了影响光线追踪吞吐量的三个关键因素：遍历长度、单元内计算量和内存局部性，并据此对场景表示、优化策略和GPU执行进行了协同设计。

◆ 使用紧凑八面体外观纹理显著降低内存访问开销
◆ 将不透明度集中于表面以促进光线提前终止
◆ 采用固定预算表示，无需剪枝或致密化即可优化
◆ 通过面向一致性遍历的GPU实现提升执行效率

在Mip-NeRF 360数据集上，VoroTracing在RTX 5090上达到623 FPS，吞吐量是此前最快射线方法的3.2倍、3D高斯泼溅的2.8倍，同时保持了具有竞争力的重建质量。更为重要的是，其渲染器仅通过光线生成与采样即可自然支持鱼眼、卷帘快门、运动模糊和景深等复杂相机效应，无需为栅格化管线编写专用扩展，展现了射线渲染在灵活性和速度上的双重潜力。</td></tr>
<tr><td>2026-08-18</td><td>Scanline-Aware Animatable Gaussian Avatars from Rolling-Shutter Videos<br><a href='http://arxiv.org/pdf/2608.17314'>论文</a></td><td>该论文针对滚动快门(RS)视频重建可动画人体化身的问题展开研究。传统方法假设视频帧为全局快门，但RS传感器逐行曝光,导致同一帧内人体不同部位对应不同姿态,将此类视频输入现有方法会引入剪切和抖动伪影,并破坏多视角一致性。

论文提出RS-Avatar方法,核心思想是利用可动画化身本身已具备的子帧渲染能力,将逐行曝光建模为按扫描线合成子帧图像,仅需将原本的模糊平均算子替换为滚动快门合成算子即可。

◆ 创新一:首次将滚动快门物理过程显式建模进3D高斯化身重建,通过扫描线级子帧合成消除RS畸变。
◆ 创新二:构建RS-ZJU基准数据集,基于ZJU-MoCap生成带RS效应的真实感视频用于评测。
◆ 创新三:揭示关键发现,即运动模糊模型虽复用相同子帧机制却无法迁移,甚至低于无视快门的基线,证明算子本身而非子帧机制才是关键贡献。</td></tr>
<tr><td>2026-08-17</td><td>Every copy of Thompson&#x27;s group $F$ in $F$ is undistorted<br><a href='http://arxiv.org/pdf/2608.17193'>论文</a></td><td>这篇论文研究了汤普森群F的子群扭曲问题,该群由单位区间上所有断点为二进有理数、斜率为2的整数次幂的分段线性同胚组成。扭曲度衡量子群的内在字度量与由母群诱导的度量之间的差异,无扭曲意味着这两种度量互相等价。

◆ 证明了F中任何与F同构的子群在F中都是无扭曲的,从而否定了F包含扭曲同构子群的可能性
◆ 解决了由Guba-Sapir和Brin独立提出的关于汤普森群扭曲性的长期未决问题
◆ 发展了处理具有复杂子群结构的群中度量问题的新方法,具有独立的方法论价值

该结果揭示了汤普森群F在子群嵌入方面具有刚性特征,对几何群论中扭曲性的研究具有重要意义。</td></tr>
<tr><td>2026-08-17</td><td>Spatial Temporal Synergy: Balancing Change and Invariance in Text Driven 3D Human Motion Editing<br><a href='http://arxiv.org/pdf/2608.16008'>论文</a></td><td>该论文针对文本驱动的3D人体运动编辑任务,指出现有扩散方法难以平衡文本响应的&quot;变化&quot;与惯性&quot;不变性&quot;,且依赖粗粒度空间约束和刚性均匀时间假设,易导致空间运动失真和物理节奏破坏。为此,论文提出CIME统一框架,将变化与不变性解耦到空间姿态和时间节奏两个维度进行协同建模,在编辑对齐与结构保真度上达到最优性能。

◆ 提出空间-时间解耦的CIME统一框架,将编辑目标分解为空间姿态变化与时间节奏不变性两个互补维度,实现更精细的协同控制。

◆ 设计全监督正负学习机制,融合分层回溯特征监督、细微运动保留和三元组语义对齐,增强空间姿态的文本响应与原始结构一致性。

◆ 引入黎曼非均匀积分流形映射(RNIMM)模块,通过运动学感知的非均匀时间戳,实现编辑序列中高保真的物理节奏复现。

◆ 在MotionFix和STANCE Adjustment数据集上取得编辑对齐和结构保真度的最优性能,验证了所提架构的有效性。</td></tr>
<tr><td>2026-08-16</td><td>Behavioral Participating Insurance: Optimal Investment under Probability Distortion and Aspiration Constraints<br><a href='http://arxiv.org/pdf/2608.15743'>论文</a></td><td>本文研究保险公司在概率扭曲与抱负型偿付能力约束下管理参与型利润分享合同的最优投资问题,整合了非凹有效效用、概率加权和概率基准约束三重理论复杂性。

◆ 运用分位数公式化与凹化技术,在完全和不完全Black-Scholes市场下均给出最优终端财富与交易策略的显式闭式解,且效用类可容纳PHARA族并统一涵盖保险场景中的非凹性。

◆ 揭示概率扭曲弱化锁定行为并引致时间不一致:在反S型扭曲下,保险公司高估上行概率,从而相较无扭曲基准显著提高风险资产配置。

◆ 通过渐近分析与数值算例,刻画由监管阈值和资本约束触发的最优策略制度转换现象。

◆ 将He和Zhou(2016)的&quot;希望-恐惧-抱负&quot;框架推广至概率扭曲与参与型合同并存的保险投资问题,为行为偏好与偿付能力约束下的资产负债管理提供新洞见。</td></tr>
<tr><td>2026-08-15</td><td>UAV Video Deblurring via Motion-Aware Diffusion: A Path to Robust Target Detection<br><a href='http://arxiv.org/pdf/2608.15259'>论文</a></td><td>这篇论文针对无人机视频因快速飞行、振动和相机旋转导致的运动模糊问题，提出了一种基于运动感知扩散模型的视频去模糊方法，旨在提升下游目标检测任务的鲁棒性。

◆创新点一：设计自适应潜在尺度选择器(Adaptive Latent Scale Selector)，根据无人机运动强度动态调整潜在空间分辨率，在细节保留与推理效率之间取得良好平衡。

◆创新点二：提出多帧对齐与可学习门控模块(Multi-Frame Alignment and Learnable Gating)，对前序帧进行 warp 对齐与门控融合，仅保留时序相关信息并抑制错位或无效特征，从而显著提升时间一致性。

◆创新点三：将扩散模型的去模糊能力与运动感知机制深度融合，在恢复质量与计算开销之间实现有效折中。

在真实无人机基准数据集上的大量实验表明，该方法不仅在去模糊性能上优于现有方法，还显著提升了目标检测精度，具有较强的实际部署价值。</td></tr>
<tr><td>2026-08-15</td><td>MotionGS-SLAM: Event-Modulated Gaussian Splatting for Motion-Blur Robust SLAM<br><a href='http://arxiv.org/pdf/2608.15024'>论文</a></td><td>现有视觉SLAM系统在运动模糊导致视觉输入退化时表现崩溃，因为它们试图从降质观测中恢复清晰内容这一不适定逆问题。本文提出MotionGS-SLAM，核心思路是将模糊处理从&quot;去模糊&quot;重构为&quot;前向建模&quot;，在渲染管线中生成式地建模模糊形成过程。

◆ 创新点：利用事件相机微秒级时间分辨率和抗模糊特性，提出事件调制的高斯核，根据精确运动线索动态调整每个高斯的光栅化方式。

◆ 创新点：设计双重调制机制，空间调制将2D高斯投影从各向同性圆点变为沿运动方向的各向异性椭圆笔触；时序调制基于局部速度自适应调整曝光积分采样密度。

◆ 创新点：基于物理建模方案，通过模糊感知的光度约束和事件约束，联合优化曝光内相机轨迹与三维场景几何。

大量实验表明，在严重高运动条件下，该方法在轨迹精度和地图质量上均显著优于当前最优方法。</td></tr>
<tr><td>2026-08-14</td><td>On the Robustness of Temporal Vision-Language Models for Surgical Endoscopy Videos<br><a href='http://arxiv.org/pdf/2608.14262'>论文</a></td><td>本文聚焦于时序视觉-语言模型（TVLMs）在手术内窥镜视频中面对临床真实采集伪影时的鲁棒性问题。研究指出，诸如失焦、烟雾、运动模糊、噪声、烧灼烟雾以及丢包等退化会引入结构化分布漂移，可能损害视频与文本的对齐效果，但现有研究对此缺乏系统评估。

◆ 提出Endo-C6基准：一个包含六种内窥镜真实扰动的高严重度紧凑评测集，并基于公开的胃肠道内窥镜和腹腔镜胆囊切除术视频进行标准化评估。

◆ 全面评测三个最新手术TVLM基线模型，在统一提示协议下完成294次数据集级别的鲁棒性分析，揭示其平均与最差情形下的性能表现。

◆ 提出RobustEndoCLIP：采用VeRA进行少样本参数高效微调，在不改变提示接口的前提下显著提升退化场景下的性能与鲁棒性。

研究发现现成TVLMs在内窥镜特定扰动下会出现严重的最差情形崩溃，而轻量级少样本适配能够有效改善这一问题。Endo-C6有望支持标准化的鲁棒性报告，推动更可靠的临床视觉-语言系统发展。</td></tr>
<tr><td>2026-08-12</td><td>Strain-coupled one-dimensional turbulence for rapid distortion<br><a href='http://arxiv.org/pdf/2608.12048'>论文</a></td><td>本文针对平均应变作用下湍流的快速畸变过程,提出了一种应变耦合的一维湍流(ODT)模型,旨在以较低计算成本同时捕捉线性快速畸变理论与非线性涡动力学的特征。模型将平均应变生成项作为线速度的连续强迫,引入与均匀快速畸变理论一致的能量守恒重分配算子来表征快速压力-应变效应,并通过ODT计算域的膨胀实现尺度压缩,完整描述了畸变过程中组分放大、压力重分配与谱重标度的耦合机制。

◆创新点:将平均应变生成项作为线速度的连续强迫引入ODT框架,实现应变与湍流的直接耦合。
◆创新点:构建能量守恒的快速压力-应变重分配算子,使其与均匀快速畸变理论在原理上一致。
◆创新点:通过ODT计算域的膨胀变换表征尺度压缩效应,从而同时刻画组分放大与谱重标度。
◆创新点:在未畸变湍流关于ODT线呈轴对称条件下,将非局部三维快速压力-应变积分简化为闭合的单线函数。
◆创新点:模型在畸变起始阶段复现快速畸变理论结果,并定量再现Lee和Reynolds(1985)的雷诺应力各向异性趋势,在应变-湍流比约0.8处捕捉到线性谱平移向非线性涡动力学过渡的宽带畸变谱特征。</td></tr>
<tr><td>2026-08-12</td><td>Bridging Event Streams and DiT: Event-Guided Video Frame Interpolation<br><a href='http://arxiv.org/pdf/2608.10479'>论文</a> | <a href='https://joseph-lin-tech.github.io/BridgeEventDiT-VFI/'>代码</a></td><td>本文提出了一种基于适配器的事件引导视频帧插值框架，旨在解决大时间间隔和复杂运动场景下现有扩散模型产生的运动模糊、结构失真和时间不一致问题。核心思路是将事件相机的高时间分辨率运动信息融入预训练图像到视频扩散模型，避免从头训练事件辅助模型的高成本。

◆设计适配器架构，将事件线索以最小改动注入预训练DiT模型，复用已有生成能力同时降低训练成本。

◆利用Image Warped Events（IWE）提供空间对齐的结构引导，并结合双向稀疏光流提供时间对齐的运动引导，二者协同增强扩散过程的生成质量。

◆实验表明该方法在真实和合成基准上均优于现有最优方法，在重建保真度和时间一致性方面均取得提升。</td></tr>
<tr><td>2026-08-11</td><td>CasDeblurGS: Cascaded 2D-to-3D Multi-View Consistency for 3D Gaussian Splatting from Two Blurry Images<br><a href='http://arxiv.org/pdf/2608.10345'>论文</a></td><td>本文针对实际应用中常见的两张运动模糊图像、无输入视角位姿且无需逐场景测试时优化的严苛条件,提出CasDeblurGS级联式3D场景重建框架,突破了现有去模糊方法对多视角冗余与精确位姿的依赖。整体流程将2D局部对应与3D全局引导相结合,先通过遮挡感知的对应点过滤构建局部可靠的光度与几何线索,再在粗略位姿下聚合为无位姿约束的3D高斯表示,并以输入视角的重渲染结果作为密集全局监督,实现去模糊与跨视角一致性的协同优化。

◆ 提出级联式2D到3D框架CasDeblurGS,在仅两张模糊图像且无输入位姿的设定下完成3D高斯重建与去模糊,无需逐场景优化或辅助清晰图像。
◆ 设计遮挡感知的跨视角对应过滤机制,有效剔除因运动模糊与遮挡产生的不可靠匹配,提升局部引导的鲁棒性。
◆ 引入无位姿的中间3D高斯表征与重渲染全局监督,先粗后精地为最终去模糊提供密集、一致的多视角引导。
◆ 在真实与合成Deblur-NeRF场景上PSNR分别提升1.19 dB与2.11 dB,显著改善渲染质量与多视角几何一致性。</td></tr>
<tr><td>2026-08-10</td><td>Motion Artifact-Aware Self-Supervised Representation Learning for 3D Brain MRI Motion Artifact Reduction<br><a href='http://arxiv.org/pdf/2608.10170'>论文</a></td><td>SSRL-MAR是一种面向3D脑MRI运动伪影去除的自监督表征学习框架,旨在解决临床中难以获取配对干净-损坏数据的难题。该方法采用三阶段训练策略:首先通过对比学习在3D patch上提取运动相关表征,再训练运动伪影合成网络模拟真实伪影,最后利用学到的退化模型对干净图像进行自监督监督以完成重建。

◆ 提出无需配对数据或显式运动标签的非配对表征学习框架,直接从图像域实现3D脑MRI运动伪影去除,摆脱对k空间数据或真实配对样本的依赖。

◆ 设计三阶段训练流程,融合对比学习、运动伪影合成与伪影感知生成器,通过自监督闭环实现从合成伪影到干净体素的有效映射。

◆ 在MR-ART真实数据集上经无监督域适应后,PSNR较仅源域监督模型最高提升2.0 dB,且性能逼近需要真实配对数据的oracle监督模型。

◆ 在轻度运动条件下,胼胝体与脑室等结构的体素误差降低超过50%,显著改善神经解剖一致性,可支持大规模神经影像研究中的结构量化分析。</td></tr>
<tr><td>2026-08-11</td><td>Bootstrapping Vision-Language Model for Hysteroscopic Surgical Scene Segmentation<br><a href='http://arxiv.org/pdf/2608.09302'>论文</a> | <a href='https://github.com/viscom-tongji/VLM-hyster'>代码</a></td><td>该论文针对宫腔镜手术场景分割中病灶形态高度相似以及镜面反射、运动模糊、液体遮挡等伪影干扰的难题,提出了首个基于视觉-语言模型(VLM)的宫腔镜手术场景分割方法VLM-hyster,实现了对15类典型结构的像素级定位。

◆ 首次将视觉-语言模型引入宫腔镜手术场景分割任务,利用预训练图像编码器结合Transformer解码器完成密集预测,提升了复杂场景下的视觉特征表征能力。

◆ 设计了类别特定的文本提示,并引入掩码蒸馏分支以过滤与文本相关性低的视觉特征,使模型更聚焦于类别相关区域,有效缓解了病灶间高相似性带来的判别困难。

◆ 构建了一个包含4020张高分辨率图像的多中心宫腔镜手术场景数据集,提供了精细的掩码标注,填补了该领域数据资源的空白。

◆ 大量实验表明VLM-hyster显著优于当前最先进的AI模型,并经妇科医生评估以及多中心、前瞻性验证,证明了其在真实临床应用中的鲁棒性和泛化能力。</td></tr>
<tr><td>2026-08-15</td><td>RMR-P: Road Metadata-Aware Restoration for Pavement Inspection<br><a href='http://arxiv.org/pdf/2608.08957'>论文</a></td><td>RMR-P是一种面向道路病害检测的图像修复网络，旨在从运动模糊、失焦、低光照和噪声退化的路面图像中恢复与病害相关的关键信息。该网络可自动估计图像退化特征，并可选择性地融合外部退化参数作为修复引导条件。研究采用未经任何微调的预训练YOLO11s检测器对修复后的图像直接进行病害检测，在IVCNZ和PCM数据集的8种未见退化条件下，有7种取得了最高的mAP50，例如在IVCNZ运动模糊条件下将mAP50从0.140提升至0.427，PCM失焦条件下从0.060提升至0.233。消融实验表明，各模块对检测性能均有贡献，呈现出互补的增益效果。

◆ 创新点一：提出退化感知修复机制，自动估计输入图像的退化特征，并可灵活融合外部已知退化参数以增强修复效果。

◆ 创新点二：设计细节保持通路，在图像修复过程中优先保留细小裂缝和坑洞边界等病害关键结构信息。

◆ 创新点三：引入任务引导训练策略，使修复网络的优化目标直接对齐下游病害检测任务。

◆ 创新点四：提出&quot;修复即增强&quot;的轻量化检测框架，无需对检测器进行微调或重训练即可提升退化图像上的病害检测性能。</td></tr>
<tr><td>2026-08-09</td><td>ERF-GS: Reconstructing Fast Motion from Disjoint Event-RGB Viewpoints<br><a href='http://arxiv.org/pdf/2608.08531'>论文</a> | <a href='https://github.com/andrewbxy/ERF-GS'>代码</a></td><td>ERF-GS是一种融合事件相机与RGB相机信息的高斯泼溅框架，旨在解决快速运动场景下的动态三维重建难题。该方法利用事件传感器的高时间分辨率来弥补传统RGB视频在捕捉快速运动时的不足。

◆ 将事件信息同时集成到高斯泼溅的优化与致密化阶段，充分发挥事件数据在时空细节捕捉上的优势。
◆ 采用真实仿真训练策略并实现事件学习与RGB输入的解耦，使其能应用于复杂布局、低帧率、严重运动模糊的自然视频。
◆ 支持RGB与事件相机视角分离设置，突破了传统方法要求两相机共置的局限。
◆ 在Neu3D和Nvidia数据集的模糊帧变体上，性能优于4DGS基线和同期工作E-D3DGS。</td></tr>
<tr><td>2026-08-06</td><td>ASTRA: Asynchronous Spatio-Temporal Reconstruction via Trajectory Alignment<br><a href='http://arxiv.org/pdf/2608.02006'>论文</a></td><td>该论文针对动态三维场景重建中多相机时间异步问题展开研究,指出传统基于光度监督的同步方法因纹理缺失和形变耦合两大瓶颈而失效。

为此,作者提出ASTRA框架,核心思想是利用二维运动轨迹作为显式、纹理无关的监督信号来估计时间偏移。

◆ 创新点一:首次引入2D运动轨迹作为纹理无关的显式时间监督,从根本上解决低纹理区域对齐信号消失的问题。

◆ 创新点二:通过将重建3D点的投影运动与观测2D轨迹对齐,实现时间偏移与动态3D表示的联合优化,显式解耦时间误差与几何形变。

◆ 创新点三:设计动态掩码与确信度掩码机制,有效抑制运动模糊区域和不可靠轨迹的负面影响。

◆ 创新点四:在多种动态高斯溅射基模型上验证,在最高25帧的严重偏移下仍保持鲁棒,PSNR提升约1.4dB,时间偏移MAE降低54.0%,同步成功率提升近4倍。</td></tr>
<tr><td>2026-08-03</td><td>When Extreme Darkness Meets Motion Blur: MeanFlow for Unified RAW Restoration<br><a href='http://arxiv.org/pdf/2608.01720'>论文</a></td><td>针对极低光照RAW图像增强中运动模糊与噪声耦合退化的难题，本文提出了一个统一的RAW恢复框架。◆ 构建了首个面向极低光照的SIDED数据集，对原始传感器RAW数据施加可控的运动退化，同时保留真实噪声特性。◆ 设计了统一RAW tokenizer，通过显式的域条件表征校准来对齐极低光照与正常曝光RAW域。◆ 首次将MeanFlow引入极低光照RAW增强任务，仅需单次函数评估即可完成图像恢复。◆ 提出物理引导的精细化模型，在不增加推理开销的前提下强化光照-反射一致性、像素保真度与色彩保持。大量实验表明，该方法在极低光照RAW增强上达到最先进水平，并能鲁棒地处理运动与噪声耦合退化。</td></tr>
<tr><td>2026-08-01</td><td>E2Pano: Learning Event-to-Panorama Image Reconstruction<br><a href='http://arxiv.org/pdf/2608.00694'>论文</a></td><td>E2Pano提出了一种基于几何引导的端到端事件相机到全景图像重建框架,旨在解决现有优化方法计算开销大、传统学习方法缺乏全景几何感知的问题。整体而言,论文通过在管线的几何映射环节保留真实球面坐标,并设计轻量级增强模块与球面Transformer来实现从事件流到高质量全景图像的高效重建,训练完全基于合成数据,但在真实采集数据上展现出良好的迁移能力。

核心创新点如下:

◆ 提出几何引导的事件到全景重建管线,贯穿整个流程保持真实的球面坐标,避免透视投影假设对全景几何的破坏。

◆ 设计轻量级增强模块结合频域监督,有效弥合事件与图像之间的领域差异,提升重建细节质量。

◆ 提出带3D位置嵌入的球面Transformer,实现面向全景结构的光度重建,降低了相对优化方法的计算成本。

◆ 构建PanoScan数据集,包含4370个合成全景场景与30个真实旋转扫描场景,并配套事件流数据,填补了该方向的数据空白。</td></tr>
<tr><td>2026-08-01</td><td>Optical Flow from Photons<br><a href='http://arxiv.org/pdf/2608.00499'>论文</a></td><td>本文针对高速低光场景下传统相机易产生运动模糊和欠曝光的问题，提出首个直接从单光子雪崩二极管(SPAD)光子流估计密集光流的方法QuantaFlow。核心思想是将SPAD表示构建嵌入到迭代光流精化过程中，突破传统固定输入表示的局限，在每次迭代中利用当前光流对源和目标子流内的切片进行粗对齐，再通过光子通量变换构建包含强度与结构线索的多尺度表示，并由自适应多尺度融合在每个像素上平衡光子噪声与残余运动模糊，最终驱动特征扭曲的光流更新。实验表明该方法在合成数据集和真实SPAD数据上均有效且具备良好泛化能力。

创新点如下：

◆ 首个直接从SPAD二值光子流估计密集光流的方法，规避了传统相机在高速低光场景下的运动模糊与欠曝光问题。

◆ 提出将SPAD表示构建嵌入到迭代光流精化框架中，使表示构造与流估计相互引导，缓解了运动感知聚合对预知光流的依赖。

◆ 设计光子通量变换与自适应多尺度融合机制，在像素级平衡光子噪声与残余运动模糊，提升表示质量。

◆ 构建了首个用于SPAD光流训练与评估的合成数据集，填补了该领域数据空白。</td></tr>
<tr><td>2026-07-31</td><td>JADE-GS: Joint Allocation of Deblurring Evidence for Event-Assisted 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2607.14990'>论文</a></td><td>JADE-GS针对3D高斯泼溅(3DGS)在运动模糊场景下的重建难题,提出了一种融合事件相机信息的联合去模糊框架。论文观察到事件双积分(EDI)的解析反演与基于学习的帧-事件联合复原这两种先验在不同区域具有互补性,各有所长。本文的核心思想是将二者的结合建模为空间证据分配问题,通过轻量级的空间先验路由器在像素级预测融合权重,生成额外的监督目标。

◆ 提出空间证据分配框架,将EDI解析反演与学习式复原两种互补先验在像素级进行自适应融合
◆ 设计轻量级空间先验路由器,仅利用模糊帧和事件流即可预测逐像素分配权重
◆ 路由器无需清晰参考图像训练,通过场景一致性与曝光测量作为自监督信号
◆ 优化完成后移除路由器,推理阶段保持原生3DGS渲染,无需生成式解码

实验表明,JADE-GS在基准上取得了领先的感知质量,在真实数据集上保真度最优,且训练开销远低于基于扩散的替代方案。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='robot-vlm'>Robot VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-18</td><td>OVIP-SG: Open-Vocabulary Instance-Preserving Scene Graphs for Mapping and Retrieval of Small, Fine-Grained Objects<br><a href='http://arxiv.org/pdf/2608.17633'>论文</a></td><td>OVIP-SG是一个面向开放词汇场景的实例保持型3D场景图框架，专注于解决小目标和细粒度物体在检测中容易被合并或忽略的难题。

◆ 利用VLM枚举场景特定类别，实现稳健的开放世界物体检测
◆ 采用对称3D IoU关联与面积加权特征融合，有效保留小型独立实例，避免小物体被相邻大物体吞并
◆ 借助VLM推断物体功能，将...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-18</td><td>HODAgent: Towards On-Demand, Responsive Humanoids for Physical World Human Interaction<br><a href='http://arxiv.org/pdf/2608.17584'>论文</a></td><td>本文提出HODAgent，一种面向服务场景人形机器人的System-2具身智能体，重点解决情境意图理解、响应式执行、任务修订和结果验证等核心问题。该系统采用半双工架构，整合环境交互器、规划器、执行器和分层记忆模块，能够在服务过程中保持交互、规划和任务状态的一致性，从而支持运动中接收新请求、保留任务进度、动态修订动作，并基于执行结果进行任务收尾判定。

◆ 设计了半双工System-2架构，通过Env-Interactor、Planner、Executor和分层Memory的协同，实现在执行过程中持续响应新请求、保留与修订任务状态，并依据执行结果进行任务闭合判定。

◆ 提出统一的仿真-真机共享接口，将平台底层控制细节隔离，使同一套策略可在Unitree G1等真实人形机器人上直接迁移部署。

◆ 在164个交互式仿真案例上取得84.8%和91.5%的联合成功率，较基线分别提升9.8和18.9个点，并在多个具身基准测试中提升0.7至9.0个点，真机实验在原子、组合和完整任务上分别达到92%、72%和63.3%的通过率。</td></tr>
<tr><td>2026-08-18</td><td>Embodied-Navigator: Point, Think, Memorize, and Align for Efficient Navigation<br><a href='http://arxiv.org/pdf/2608.17512'>论文</a></td><td>TAMP-Nav是一个面向高效具身导航的统一框架，针对现有VLM导航方法中动作空间与二维预训练先验不匹配、推理调度僵化、记忆管理低效等问题提出了系统性解决方案。论文在R2R-CE数据集上取得了66.2%的成功率，达到了当前最优水平，且仅需9万条训练轨迹即可实现高效学习，展现出优秀的运行效率和样本效率。

◆ 提出像素到三维的动作表征(Point)，将导航任务重新建模为二维视觉提示，VLM只需选择二维像素点，再投影到三维坐标交由底层SLAM控制器执行，使具身执行与VLM固有的二维视觉能力自然对齐。

◆ 设计选择性推理与锚点轨迹记忆机制(Think and Memorize)，动态触发思维链推理，仅在关键节点保留高保真记忆，将冗余轨迹压缩为轻量的时空指示符，在保留关键历史信息的同时增强时空感知。

◆ 构建两级对齐范式(Align)，通过群体相对策略优化将全局结果奖励与细粒度过程奖励叠加，实现密集监督，使智能体的认知规划与物理环境反馈紧密耦合，赋予模型自适应推理能力。</td></tr>
<tr><td>2026-08-18</td><td>EATR-Stereo: Embodiment-Aware Routing of Paired Stereo Evidence for Humanoid Vision-Language-Action Control<br><a href='http://arxiv.org/pdf/2608.17453'>论文</a></td><td>该论文针对人形机器人长时序视觉-语言-动作控制任务,提出EATR-Stereo框架,旨在解决头戴式立体相机中辅助视图信息利用不充分、与本体感知脱节的问题。系统保留主视图原生token通路,通过对同步辅助视图token序列进行查询,构建与主视图对齐的跨视图辅助token(CVATs),避免破坏预训练VLA的视觉表征。

◆ 创新点1:提出主视图对齐的跨视图辅助token机制(CVATs),通过查询辅助视图序列生成与主视图对齐的辅助token,在保留预训练主视觉通路的同时引入立体互补信息。

◆ 创新点2:设计本体感知分段编码器,将机器人构型历史按身体部位分段编码,并以token级别条件化辅助信息的使用,实现对辅助特征的动态选择性路由。

◆ 创新点3:冻结预训练视觉-语言模型,仅通过路由的辅助流增强语言与主视觉上下文,保证与既有VLA表征的兼容性。

在33自由度物理人形机器人、37维本体状态、9组配置的搜索-接近-抓取-放置-返回任务中,完整任务成功率60.0%、抓取100.0%、阶段80.0%;严重单侧遮挡下恢复率达80%,显著优于无本体路由的CVAT基线30%,验证了选择性立体证据路由对空间定位与长时序可靠控制的有效性。</td></tr>
<tr><td>2026-08-18</td><td>Prism-GRPO: Faster VLA Policy Optimization via Splitting Same-outcome Groups<br><a href='http://arxiv.org/pdf/2608.17423'>论文</a></td><td>论文指出GRPO用于视觉-语言-动作策略强化学习时，二元成功奖励会使大量同结果组优势为零而被丢弃，从而浪费昂贵的机器人采样预算。为此提出Prism-GRPO方法，在二元结果奖励基础上引入加权轨迹级执行质量分数，将同结果组拆分为质量谱系以恢复训练信号，同时确保所有成功仍严格优于所有失败。

◆提出通用轨迹级执行质量评分机制，信号可来自仿真接触、执行动作或视觉观察，无需任务特定的过程奖励
◆理论上证明该方法不会增加采样组因零优势被丢弃的概率，并推导出保持任务成功局部上升方向的梯度对齐条件
◆在四个RoboTwin任务中以最多减少56%采样达到目标成功率，同时抑制奖励作弊捷径，干净行为可直接零样本迁移至真实机器人...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-17</td><td>PDDL-ART: Autonomous Symbolic Abstraction From Demonstration For Long-Horizon Robotic Manipulation Using Vision-Language Models<br><a href='http://arxiv.org/pdf/2608.17146'>论文</a></td><td>PDDL-ART提出了一种基于视觉语言模型(VLM)的框架，仅需单个专家演示、自然语言任务描述和高层动作库，即可自主生成任务特定的PDDL域与问题描述，无需领域模板、动作签名或微调。系统通过多阶段纠错流水线(涵盖语法、语义和执行三个层面)确保生成描述既语法正确又语义对齐。核心创新在于符号谓词落地机制，利用VLM的工具调用能力引入几何与时间推理，使模型能够评估从图像中无法直接判断的关系谓词，并由模型自主决定何时调用工具及如何解读结果。

◆提出无需领域知识或微调的VLM驱动的PDDL自动生成框架，仅从单一专家演示即可构建长时域任务规划。

◆设计语法-语义-执行三级纠错流水线,确保生成描述在多层面与演示任务保持一致。

◆创新性地将VLM工具调用与符号谓词落地结合,引入几何和时间推理处理视觉无法直接判别的关系谓词。

◆VLM自主决定工具调用时机与结果解读,实现真正自适应的规划抽象。

在引擎维护和家庭场景的复杂长时域任务中,PDDL-ART平均成功率达93.3%,显著优于78.3%的基线VLM规划器。</td></tr>
<tr><td>2026-08-17</td><td>PROBE: Manipulation-Grounded Visual Question Answering with VLM Agents<br><a href='http://arxiv.org/pdf/2608.17129'>论文</a></td><td>本文针对家庭机器人在杂乱环境中回答关于被遮挡物体的问题,提出了&quot;操作基础视觉问答&quot;(MG-VQA)这一新任务范式,要求模型通过主动操作物体来揭示被遮挡目标并作答。作者构建了包含三个核心组件的PROBE框架,系统性地解决了该任务的基准测试、训练与部署问题。在PROBE-Bench上的实验显示,具备工具调用能力的智能体方法在所有任务类型上一致优于仅依赖感知的基线方法,平均提升8.0%。

本文的核心创新点如下:

◆ 首次形式化定义MG-VQA任务,聚焦于动态场景中&quot;操作-推理&quot;的闭环问题,弥补了现有VQA研究在主动操作方面的空白。

◆ 提出高保真桌面模拟器PROBE-Sim,支持抓取与推动等机器人操作工具,并基于此构建包含150个任务、6类问题的评估基准PROBE-Bench。

◆ 设计PROBE-Agent微调方法,采用混合数据策略从强大的教师模型蒸馏成功轨迹,使开源小模型平均提升11.5%,并具备对未见物体和新任务的正向迁移能力。

◆ 通过真实桌面环境的部署实验,验证了所提方法的sim-to-real迁移有效性。</td></tr>
<tr><td>2026-08-17</td><td>VLCP: Vision Language Control Policy Closed-Loop Code Replanning for Robot Manipulation<br><a href='http://arxiv.org/pdf/2608.16978'>论文</a></td><td>该论文提出VLCP方法，让冻结的视觉语言模型直接编写Python控制函数作为机器人操控策略，无需任何微调或演示数据。区别于现有方法在固定策略或子任务层面反应，作者选择在控制代码层面实现闭环重规划。每K步VLM基于多视角RGB、关节状态和状态增量重新观察场景并改写控制函数，使失败在单回合内被捕捉并修正。在57项MuJoCo/RoboVerse任务上，VLCP以零训练方式达到35.1%总体成功率，相比单次查询提升十倍，27.3%的回合内恢复率有效弥补抓取失败。系统通过84%缓存命中率和每回合仅约10次紧凑查询保持低成本，并将控制模块累积为跨回合可复用的技能库。

◆ 冻结VLM直接生成Python控制函数策略，零微调零演示
◆ 控制代码层面闭环重规划，每K步改写策略修正失败
◆ 回合内失败恢复机制，27.3%恢复率显著优于开环方法
◆ 高效推理设计，84%缓存命中+仅约10次查询/回合
◆ 跨回合技能库持久化，供后续回合提示调用...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-17</td><td>When State Becomes an Attack Surface: State-Semantic Injection in LLM-Driven Embodied Agents<br><a href='http://arxiv.org/pdf/2608.16806'>论文</a></td><td>本文针对基于大语言模型的具身智能体，提出了一种名为&quot;状态语义注入&quot;(State-Semantic Injection)的新型攻击范式。研究指出，具身智能体在任务规划中严重依赖从环境感知中提取的内部状态信息，这些信息构成了一个被长期忽视的攻击面，攻击者可借此劫持智能体的决策过程。

◆核心创新在于将攻击视角从传统的用户提示转移到智能体的环境状态语义，首次将&quot;状态&quot;明确定义为LLM具身智能体的攻击面，突破了已有研究以用户输入为主的安全假设。

◆提出了系统化的状态语义注入攻击框架，通过篡改场景描述、物体属性和空间关系等状态信息，污染智能体对环境的内部表征，进而劫持其任务推理与行为决策链路。

◆在多种LLM驱动的具身智能体基准上进行了实验验证，证明了该攻击在任务劫持、行为误导等方面的有效性与广泛适用性。

◆该工作揭示了从纯文本生成到物理执行链路过渡中的新型安全风险，为具身智能安全研究开辟了重要方向。</td></tr>
<tr><td>2026-08-17</td><td>Neurosymbolic Embodied Agents<br><a href='http://arxiv.org/pdf/2608.16794'>论文</a></td><td>本文提出一种神经符号具身智能体，将长视野家务任务分解为任务导向的视觉探索和受限符号规划两个阶段。视觉语言模型通过探索从自我中心观察中获取符号化的目标相关谓词与实例绑定，PDDL转移模型约束解码使动作在环境动力学下可执行，再以蒙特卡洛树搜索结合领域无关启发式评估可执行延续。在VirtualHome和ALFWorld上，4B至27B开源模型均超过90%成功率，且失败可自动归因于状态获取阶段。

◆将感知与规划解耦为两阶段，无需专门训练即可定位失败于状态获取而非计划生成。
◆通过PDDL转移模型约束解码，从结构上保证计划的可执行性，解决语言模型输出违反环境动力学的问题。
◆揭示约束解码与树搜索的互补性：单独使用解决率不足三分之一，组合则超过95%，证明二者不可互换。
◆以小模型显著超越27B直接视觉策略，且生成token和所需图像数远少于扩展思考或直接交互方法。</td></tr>
<tr><td>2026-08-16</td><td>AlloEgo-VLM: Disambiguating Allocentric and Egocentric Reference Frames in Vision-Language Models<br><a href='http://arxiv.org/pdf/2608.15605'>论文</a></td><td>本文针对视觉语言模型在空间语义理解中面临的参考框架歧义问题展开研究，指出自然语言描述空间关系时常常省略显式的参考框架（自我中心或他人中心），导致现有VLM产生不一致甚至错误的响应。作者构建了一个名为AlloEgo-View的新数据集，包含图像、查询和视角特定答案的三元组，采用结构化空间表示方法，标注了场景描述、参考对象与目标对象、它们的朝向、参考框架及视角类型。基于该数据集，作者提出了AlloEgo-VLM框架，通过监督微调可轻松集成到现有VLM中，实现对参考框架的消歧。最后在NVIDIA Isaac Sim仿真机器人平台上验证了其在开放性物体搜索任务中的实际可行性，实验表明当前VLM在处理视角特定查询时存在明显局限，而AlloEgo-VLM展现出强大的消歧能力。

本文的核心创新点如下：

◆ 构建了首个专门用于参考框架消歧的视角特定数据集AlloEgo-View，采用结构化空间表示方法，涵盖参考对象、目标对象、朝向、参考框架及视角类型的细粒度标注。

◆ 提出了AlloEgo-VLM消歧框架，通过监督微调可灵活集成到现有VLM中，在查询模糊的情况下也能准确区分自我中心与他人中心参考框架。

◆ 将该框架部署到基于NVIDIA Isaac Sim的具身机器人平台，在开放性物体搜索任务中验证了从仿真到现实应用的可行性。</td></tr>
<tr><td>2026-08-16</td><td>CrossView: Can Vision-Language Models Reason Across Cameras?<br><a href='http://arxiv.org/pdf/2608.15539'>论文</a> | <a href='https://utaustin-swarmlab.github.io/CrossView'>代码</a></td><td>本文指出当前视频理解基准主要针对单摄像头场景，而真实世界中的自动驾驶、安防监控、机器人等多摄像头网络需要处理跨视角推理这一根本性不同的问题。作者发现现有视觉语言模型在多摄像头推理上能力不足，主要体现在上下文随视角数量扩展、部分摄像头可见的遮挡处理、视角重要性判断以及跨视角证据融合等方面的挑战。为此，研究团队提出了CrossView基准，涵盖自动驾驶、安防监控、自我/他者视角视频和机器人四个领域的跨摄像头视频问答任务。在对GPT-5.2等专有模型和Qwen3-VL等开源模型的评估中，所有模型准确率均较低，开源模型差距尤为明显。实验表明模型性能与其联合处理多视角的能力密切相关，验证了多摄像头视频推理是视觉语言模型面临的关键新挑战。

◆首次系统性地提出多摄像头视频推理任务，指出其与单摄像头问题的本质区别，包括跨视角上下文整合、遮挡处理和证据融合等独有挑战。

◆构建了首个多领域跨摄像头视频问答基准CrossView，覆盖自动驾驶、安防监控、第一人称/第三人称视频和机器人四大应用场景。

◆全面评估了专有模型与开源模型在多摄像头推理任务上的表现，揭示了现有模型在该方向上的显著能力缺陷。

◆发现模型性能与联合处理多视角的能力强相关，为多摄像头视频理解研究提供了新的评估标准和方向指引。

◆开源了完整的数据集和代码，为后续研究提供了可复现的基准平台。</td></tr>
<tr><td>2026-08-15</td><td>FloodReasonBench: Benchmarking VLM Reasoning Segmentation for Embodied Flood Response at the Edge<br><a href='http://arxiv.org/pdf/2608.15410'>论文</a></td><td>本文提出FloodReasonBench基准，专门用于评估边缘设备上具身洪水响应场景中视觉语言模型的推理分割能力，填补了现有基准在特定领域与资源约束方面的研究空白。其核心贡献包括：

◆构建了首个面向真实洪水场景的推理分割数据集FloodResponseSeg，涵盖响应相关的目标类别与任务语义。

◆从任务与系统两个层面系统刻画了推理分割管线在轻量级视觉编码、层次化分割推理及压缩中间表示等条件下的性能特征。

◆发现通用预适应设置下精度呈现显著的分区依赖性波动，而洪水自适应目标负载设计空间则表现出更紧凑且稳定的精度范围。

◆在NVIDIA Jetson AGX Xavier边缘平台上实测了推理分割精度、延迟、能耗与通信开销之间的多维权衡，为质量约束下的边缘运行点选择提供了实证依据。</td></tr>
<tr><td>2026-08-15</td><td>Remember Smarter: Visual History Compressor and Hyperbolic Experience Space for Robotic Memory<br><a href='http://arxiv.org/pdf/2608.15269'>论文</a></td><td>Remember Smarter（RS）是一种面向长时程机器人策略的即插即用记忆模块，通过视觉历史压缩与双曲经验记忆两条互补分支，实现紧凑的历史观测访问与可复用经验管理。

◆视觉分支采用双向空间Mamba与因果时序Mamba对多视角patch历史进行压缩，并通过残差交叉注意力将记忆暴露给面向动作的隐状态，同时保持VLM视觉token流不变。

◆经验分支将成功的最终层VLM状态存入Poincare VAE空间进行层次化组织，并以异步方式将检索到的经验转换为测地线提示token，不阻塞动作推理过程。

◆整体模块具有即插即用特性，无需修改原有VLA架构的核心结构，便于集成到现有系统中。

将RS适配到pi0后，在LIBERO-Plus基准上的总成功率从53.6%大幅提升至70.6%，并在真实机器人实验中验证了其在记忆保留与经验利用方面的显著性能提升。</td></tr>
<tr><td>2026-08-13</td><td>MLLM-Routed Heterogeneous Ensembles for Robust Cross-Dataset Image Classification<br><a href='http://arxiv.org/pdf/2608.13463'>论文</a></td><td>该论文针对图像分类模型在跨域、跨难度任务中泛化能力不足的问题，提出了ARMDIL框架——一个基于多模态大语言模型（MLLM）的自适应路由异构集成系统。该方法利用MLLM智能体动态分析每张图像的特征，并将其路由到最合适的视觉骨干网络。集成成员涵盖了卷积神经网络（ResNet）、自监督表征学习器（SSL）以及视觉-语言模型（VLM）等多种架构，并在统一标签空间下联合训练。

创新点如下：

◆ 提出基于MLLM智能体的动态路由机制，无需专门的路由训练即可将图像分配到最匹配的视觉模型

◆ 构建了融合CNN、SSL与VLM的异构模型集成，在多个跨域数据集上展现差异化互补能力

◆ 实现统一标签空间的跨数据集联合训练，有效缓解分布差异带来的泛化难题

◆ 通过提示词修改即可快速整合新信息，显著提升模型的可扩展性与适应性

◆ 利用MLLM的自然语言推理痕迹增强决策可解释性，便于分析路由依据与模型行为

总体而言，ARMDIL在跨数据集图像分类任务中表现优于单一专用模型，性能与经过专门训练的路由系统相当，同时具备更高的灵活性和透明度，为通用视觉系统的发展提供了新思路。</td></tr>
<tr><td>2026-08-13</td><td>BrainWAM: Action-Space Coordination of Semantic Priors and Predictive Dynamics for Autonomous Driving<br><a href='http://arxiv.org/pdf/2608.12854'>论文</a></td><td>这篇论文提出了BrainWAM框架，旨在解决自动驾驶中语义先验与预测动力学难以统一融合的问题。作者指出现有端到端方法要么偏重VLA的语义推理，要么偏重WAM的预测式世界建模，而简单的token级联合注意力会因注意力分配失衡导致语义捷径压制预测信号。受神经科学中功能特化系统协调的启发，BrainWAM将两类能力解耦为两条专门化的动作导向通路，并在紧凑动作表征层进行对齐融合，同时设计了异步整流流推理以解耦视频与动作的去噪过程。实验表明，BrainWAM在NAVSIM v1和v2基准上均达到最优性能，验证了该统一规划思路的实用价值。

◆ 将语义推理与预测世界建模解耦为两条专门化的动作导向通路，在动作表征层而非token层实现协调融合，避免注意力分配失衡问题。
◆ 引入异步整流流推理策略，将视频去噪与动作去噪并行解耦，在保留预测上下文的同时显著缩短推理延迟。
◆ 借鉴神经科学中大脑功能特化系统协同工作的机理，为多模块自动驾驶规划器提供生物启发的结构化设计范式。</td></tr>
<tr><td>2026-08-13</td><td>Spatial Memory Agent: Experience-Grounded Procedure Memory for Spatial Intelligence<br><a href='http://arxiv.org/pdf/2608.12743'>论文</a></td><td>针对冻结VLM智能体在空间推理上的自进化难题,该论文提出空间记忆智能体(SMA),这是一种基于经验的可重用程序记忆框架,通过验证器引导的反思将成功经验提炼为可迁移教训,并在只读部署阶段结合语义过滤与可靠性分数检索记忆来辅助冻结模型推理。该方法不依赖外部空间工具或参数更新,在五个空间基准与四种基础VLM的二十次评估中均取得最高宏观平均,验证了冻结模型空间自进化的可行性与通用性。

◆ 提出验证器引导的反思机制,自动从可验证空间经验中蒸馏出紧凑且可复用的经验教训
◆ 引入迁移可靠性分数(TRS),依据后续检索的访问证据对每条教训的迁移可信度进行持续校准
◆ 设计语义过滤与相似度-TRS联合排序的记忆检索机制,无需外部专家工具即可引导冻结模型推理
◆ 在五个代表性空间推理基准和四种不同规模基础VLM上实现参数更新无关的自进化路径,并在多数评估中取得最佳准确率...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-12</td><td>Can Vision-Language Models Assess Proxemic Risk from Egocentric Robot Images?<br><a href='http://arxiv.org/pdf/2608.12515'>论文</a></td><td>本文系统评估了三种开源视觉语言模型（InternVL、Qwen-VL、SmolVLM）在机器人第一人称视角下对接近风险进行分类的能力，将图像划分为四个危险等级。实验对比了三种提示策略和两轮QLoRA微调的效果，结果表明未微调时模型表现仅接近基线水平，微调带来的整体提升有限，但Qwen-VL配合高级提示在识别高危场景时召回率显著优于其他模型。◆本文首次针对机器人自我中心视角的接近风险评估任务，对多种开源VLM进行系统性基准评测。◆提出并比较了不同提示策略与QLoRA微调在细粒度危险分类中的组合效果。◆创新性地通过人物定位分析揭示了正确分类与空间定位能力之间存在解耦现象，模型即使不关注相关区域也能给出有效标签。◆研究发现针对性提示与微调可显著提升特定模型对高危场景的检测能力，为安全导航应用提供了实用启示。</td></tr>
<tr><td>2026-08-12</td><td>HandEdit: A Unified Benchmark for Egocentric Human-to-Robot Dexterous Hand Image Editing<br><a href='http://arxiv.org/pdf/2608.12122'>论文</a></td><td>HandEdit针对具身AI中灵巧手操作数据稀缺这一核心难题，提出将丰富的第一人称人类手部视频转化为机器人灵巧手图像，从而实现从人类数据到机器人数据的大规模迁移。论文的核心思路是构建一个统一的、以具身为条件的图像编辑数据集和基准，弥补人类与机器人数据在外观、关节结构和视角上的巨大差异。

◆ 构建了大规模具身感知图像编辑数据集HandEdit，包含超过2亿编辑实例，源自5个多样化源数据集，覆盖26种URDF配置（13种手部、13种手-臂组合）。

◆ 建立了统一基准协议，设有Hand-only和Hand-Arm两条评估轨道，支持URDF条件下的标准化评测。

◆ 设计了多维度评估指标体系，融合通用相似度指标、VLM判别指标以及具身感知指标，对11个代表性图像编辑基线模型进行了全面评估。

◆ 为图像编辑与机器人学交叉研究提供了关键资源，既推动了具身感知编辑模型发展，又使从人类视频中进行可扩展的灵巧机器人学习成为可能。</td></tr>
<tr><td>2026-08-12</td><td>G0.5: One Autoregressive Stream for Robot Reasoning and Action<br><a href='http://arxiv.org/pdf/2608.11739'>论文</a></td><td>该论文提出了G0.5模型,挑战了当前视觉-语言-动作(VLA)模型将预训练VLM与独立训练的流匹配动作专家耦合的主流范式,认为这种方式使VLM仅充当上下文编码器而非决策者。

◆一个统一的自回归Transformer解码器在单一目标下同时输出推理token和动作token,使预训练VLM的能力直接迁移到物理行为控制中。

◆可学习的跨具身动作分词器将异构机器人动作映射到共享词汇表,实现了多种机器人平台的统一表征。

◆原生思维链流将任务分解、物体定位和动作提示与动作token交错输出,支持通过提示直接调节动作粒度、任务时长和分布外场景处理。

◆视觉记忆模块通过视觉编码器注入多秒级历史信息,增强了对长时序任务的感知能力。

G0.5在7个独立测试场景中均达到SOTA,包括真实机器人微调(76.7% vs π_0.5的53.3%)、2025 BEHAVIOR挑战赛长时序家务任务(31.4%)以及DROID零样本迁移(82.5%)等,显著优于现有方法。</td></tr>
</tbody>
</table>
</div>

<div align='right'><a href='#top'>↑ 返回顶部</a></div>

<h2 id='archive'>归档</h2>

> [点击查看所有历史论文归档](./docs/archive.md)


<h2>GitHub 实验室仓库监控</h2>

<h3>HKU-MARS (港大火星实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5074</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4521</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2440</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1629</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1618</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1477</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1307</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1285</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1044</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1007</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>933</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>807</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>782</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>746</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>732</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>721</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>661</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>652</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>627</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>606</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>601</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>566</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>565</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>525</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>505</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>450</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>447</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>356</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>346</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>268</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>266</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>255</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>239</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>228</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>223</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>213</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>207</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>185</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>147</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>145</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>121</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2865</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1663</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1364</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1049</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>878</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>702</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>663</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>654</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>597</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>574</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>573</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>568</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>552</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>518</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>502</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>464</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>453</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>449</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>313</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>301</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>285</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>266</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>258</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>224</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>207</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>202</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>184</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>177</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>168</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>160</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>156</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>138</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>137</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>132</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>130</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>111</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>108</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>106</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>105</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>102</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>101</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.08.19

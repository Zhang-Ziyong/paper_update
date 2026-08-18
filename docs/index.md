# 计算机视觉领域最新论文 (2026.08.18)

> 每日自动更新计算机视觉领域的最新arXiv论文

> 使用说明: [点击查看](./docs/README.md#usage)

<details>
<summary>分类目录</summary>
<ol>
<li><a href='#slam'>SLAM</a></li>
<li><a href='#sfm'>SFM</a></li>
<li><a href='#image-matching'>Image Matching</a></li>
<li><a href='#obstacle-avoidance'>Obstacle Avoidance</a></li>
<li><a href='#navigation'>Navigation</a></li>
<li><a href='#motion-planning'>Motion Planning</a></li>
<li><a href='#sensor-calibration'>Sensor Calibration</a></li>
<li><a href='#sensor-undistortion'>Sensor Undistortion</a></li>
<li><a href='#vlm'>VLM</a></li>
<li><a href='#archive'>归档</a></li>
</ol>
</details>

<h2 id='slam'>SLAM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-08-14</td><td>Geometry-Aware Online Mapping for 3D Gaussian Splatting SLAM<br><a href='http://arxiv.org/pdf/2608.14902'>论文</a></td><td>本文针对3D高斯溅射（3DGS）SLAM系统在在线建图场景中直接沿用离线重建启发式策略，导致在严格的逐关键帧优化预算下表现脆弱的问题，提出了一套几何感知的在线建图改进方法。核心思路是将初始化与致密化启发式在解耦的3DGS-SLAM框架中重新设计，使有限计算资源更合理地分配到新增高斯原语上。实验表明，该方法在渲染质量上取得稳定提升，且计算开销可忽略不计，揭示了在线SLAM中光度残差与位姿不确定性之间的紧密耦合关系。

◆ 透射率保持的致密化方法（transmittance-preserving densification），避免新增高斯破坏原有渲染一致性
◆ 基于深度与相机内参的相机感知尺度初始化（camera-aware scale initialization），使新增高斯初始形状与观测几何匹配
◆ 误差引导的致密化策略（error-guided densification），将新原语集中于高残差区域以提升建图效率...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-08-02</td><td>Look Up and Look Back: Hidden Attention and Latent Orientation in a Frozen Foundation Model for Panoramic SLAM<br><a href='http://arxiv.org/pdf/2608.00925'>论文</a></td><td>本文针对单目全景SLAM中相机倾斜、尺度漂移和错误回环等问题，提出HALO-SLAM方法，核心贡献在于挖掘冻结全景几何基础模型的内部隐式线索。◆发现中间token隐式编码相机帧下的重力方向，无需IMU即可实现球面正立规范化。◆发现跨视图注意力可作为潜在回访地点的兼容性线索，并据此设计代价感知的三阶段级联回环检测（DBoW2事件检索+注意力兼容性过滤+稠密几何验证）。◆利用对称子图增强生成像素对齐的3D-3D对应，估计稳健的Sim(3)约束并与顺序约束联合优化。在5个真实全景基准的125条序列上达到100%成功率，ATE较最佳ERP原生基线降低30-88%。</td></tr>
<tr><td>2026-07-29</td><td>VidMap: Exploiting Temporal Structure for Video-Based Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.27194'>论文</a> | <a href='https://github.com/cvg/vidmap'>代码</a></td><td>本文针对无约束视频的相机标定与度量位姿恢复问题，提出VidMap系统，旨在弥合SLAM与SfM两大主流方法之间的鸿沟。现有SLAM方法对初始化敏感、依赖已知标定，而传统SfM忽略图像时序且难以应对视觉对称与极端运动。VidMap融合了SLAM的强时序约束与离线SfM的全局优化灵活性，实现了对任意长且未标定视频的度量重建。系统利用宽基线稠密图像匹配技术，并以时序信息作为可靠的闭环检测核心线索，同时在全局优化中引入单目深度先验以恢复真实尺度。实验表明，该方法在极端运动和视觉对称等挑战性场景下，显著优于当前最先进的SLAM与SfM方法。

◆ 提出混合框架，将SLAM的时序约束与SfM的全局优化相结合，实现未标定长视频的鲁棒度量重建。
◆ 将时序顺序作为闭环检测的一等公民，提升对称场景与极端运动下的关联可靠性。
◆ 引入宽基线稠密图像匹配，增强跨帧对应关系的精度与覆盖范围。
◆ 在全局优化中融入单目度量深度先验，无需已知标定即可恢复真实尺度。</td></tr>
<tr><td>2026-07-28</td><td>HiFi-UMI: Learning Deployable Manipulation Policies from High-Fidelity UMI Data Alone<br><a href='http://arxiv.org/pdf/2607.25895'>论文</a></td><td>HiFi-UMI提出了一种便携式机器人操作数据采集系统，旨在解决高质量与可扩展性难以兼得的瓶颈问题。系统通过协同设计轨迹精度、夹爪间相对位姿、时钟同步与视场，实现了无需外部追踪设施下3毫米的工作空间末端执行器精度。

◆采用头戴式离线立体惯性SLAM，并直接利用原生（而非重建）的夹爪间相对位姿，保证运动学一致性。
◆通过共享的微秒级GPIO触发器实现多相机硬件级时间同步，显著优于传统软件同步。
◆每只手配置两枚广角相机，覆盖约200度视场，最大限度减少遮挡并提升感知鲁棒性。
◆首次实现&quot;零真机后训练&quot;，仅凭HiFi-UMI数据微调即可在真实机器人上部署，并在多种VLA与世界-动作模型上达到与同域遥操作相当的性能。
◆开源HiFi-UMI-2K数据集，包含2000小时微秒同步、超广角演示数据，每条轨迹经仿真回放自动重建与验证，为机器人学习社区提供大规模高保真资源。</td></tr>
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-07-11</td><td>Navigating the Crowd: Non-linear MPC with Social Forces Dynamics for Human-Aware Robot Navigation<br><a href='http://arxiv.org/pdf/2607.10374'>论文</a></td><td>本文针对人机共融环境中机器人安全且符合社会规范的导航问题，提出了SFM-NMPC框架，将社会力模型(SFM)与非线性模型预测控制(NMPC)深度融合。其核心思想是在优化循环内嵌入对周围行人运动轨迹的预测，使控制器能够联合预测人与机器人在预测时域内的运动，从而实现具有社会意识的规划。

◆将社会力模型集成到NMPC的动态模型中，在优化循环内直接预测行人轨迹，实现人机轨迹的联合优化。

◆设计了针对性的社会成本函数，引导优化过程产生尊重个人空间、符合人类舒适度要求的行为。

◆在增加模型复杂度的同时，通过高效求解实现20Hz的实时控制，满足实际部署需求。

◆在拥挤环境仿真中验证了方法在社会合规性指标上优于现有先进方法，并通过消融实验证明了嵌入式SFM动力学和社会成本项的贡献。</td></tr>
<tr><td>2026-07-10</td><td>DGSfM: Depth-Guided Scale-Aware Global Structure-from-Motion<br><a href='http://arxiv.org/pdf/2607.09507'>论文</a> | <a href='https://github.com/sithu31296/DGSfM'>代码</a></td><td>本文提出DGSfM,一种深度感知的全局SfM流水线,旨在解决传统全局SfM在基线估计噪声和视图图约束弱时定位不稳定、以及视觉模糊对产生虚假边导致重建退化的问题。论文的核心思路是引入单目深度图作为可扩展先验,同时保留显式多视图优化。

◆ 提出深度感知的相对位姿求解器,将原本尺度模糊的极线约束转化为尺度感知的相对位姿约束,使全局定位摆脱对噪声基线估计的依赖。

◆ 通过视图图过滤和基于深度一致性的匹配剪枝,抑制在极线几何下看似合理但实际错误的边和匹配,提升鲁棒性。

◆ 设计全局尺度平均和深度引导的位姿-点初始化策略,将各图像的单目深度图对齐到统一重建尺度,并为全局定位与光束法平差提供稳定初值。

在ETH3D和IMC2021上的实验表明,DGSfM在稀疏和稠密匹配前端下均持续优于强基线全局SfM方法,在位姿精度上取得显著提升。代码已开源,具有较好的实用价值。</td></tr>
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

<h2 id='obstacle-avoidance'>Obstacle Avoidance</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-17</td><td>Orbit-Planner: Towards Latent World Models for On-Orbit Obstacle Avoidance of Satellite Agents<br><a href='http://arxiv.org/pdf/2608.16651'>论文</a> | <a href='https://github.com/ZhijianLi2003/Orbit_Planner'>代码</a></td><td>本文针对卫星在轨避障任务中传统规划器依赖预定义地图、难以适应动态环境的问题,提出了Orbit-Planner,一种两阶段潜在世界模型方法。该方法通过学习动作条件的航天器动力学,在潜在空间中执行长时域未来状态推演,从而摆脱对固定环境假设的依赖。

◆ 提出了两阶段潜在世界模型框架,在潜在空间中进行动作条件的航天器动力学推演,无需预定义地图即可预测未来状态。
◆ 设计了物理探针(Physics Probe)模块,能够从想象的潜在轨迹中解码恢复物理状态变化,连接了潜在表征与物理可解释性。
◆ 在Isaac Sim闭环避障导航实验中取得91.7%的高成功率,验证了方法在动态在轨场景中的有效性和长时域规划能力。</td></tr>
<tr><td>2026-08-17</td><td>Arm-Aware Guided Dexterous Grasp Generation with Arm-Agnostic Grasp Models<br><a href='http://arxiv.org/pdf/2608.16351'>论文</a> | <a href='https://arm-aware-dexgrasp.github.io/'>代码</a></td><td>本文针对现有灵巧抓取方法在考虑机械臂约束时效率低或泛化性差的问题，提出了一种无需重训练的机械臂感知抓取生成框架，仅在推理阶段结合机械臂与场景信息。作者将问题建模为手部姿态与机械臂构型的联合优化，并推导出机械臂相关约束的闭式梯度，从而实现高效求解。◆理论创新：证明基于梯度的优化等价于引导式扩散采样过程，能够将近可行样本推向可行区域。◆方法创新：利用预训练的无机械臂依赖的扩散模型，通过采样引导实现机械臂感知，避免针对特定机械臂重新训练，提高了泛化能力。◆实验优势：在10k物体和6种受限场景下，生成可行抓取的概率显著优于现有拒绝采样和重训练方法。</td></tr>
<tr><td>2026-08-16</td><td>Some Modifications to Our End-to-End UAV Planner<br><a href='http://arxiv.org/pdf/2608.15741'>论文</a></td><td>针对YOPO一阶段规划器存在的软约束优化缺陷（安全代价与平滑、目标项竞争、非凸性及多项式表达力有限），本文提出四项有效改进。◆ 采用两段MINCO轨迹参数化，以时间换取平滑度而不改变空间轨迹形状，丰富轨迹表达。◆ 将多模态预测提升为跨越不同同伦类别的运动基元，每个基元作为同伦锚点将轨迹约束在可行盆内，无需显式安全飞行走廊或前端搜索。◆ 对速度与加速度施加障碍函数惩罚并加入曲率相关速度限制（梯度仅作用于速度），实现杂乱环境与急转弯处的自适应减速。◆ 将得分回归替换为排序损失，避免小分数误差导致候选集重排序。综合以上改进，模型获得了更丰富的轨迹表达、更安全的避障能力与更直接的飞行路径。</td></tr>
<tr><td>2026-08-14</td><td>A Temporal Barrier Framework for Collision Avoidance in Multi-Agent Autonomous Aerial Vehicles<br><a href='http://arxiv.org/pdf/2608.14239'>论文</a></td><td>本文针对动态、不确定且可能存在对抗性的多智能体空中飞行器协同场景,提出了一种基于时间维度的碰撞规避新框架。核心思想是将安全约束从传统的距离或速度空间转移到时间空间,使控制器具有前瞻性的风险感知能力。在三维独立追踪和编队飞行长时域仿真中,该方法相比高阶距离型CBF基线,在碰撞率减半的同时将航点推进量提升至两倍,验证了时间屏障在安全与效率权衡上的显著优势。

◆ 提出对抗性碰撞时间(aTTC)风险度量:在假设周围智能体具有对抗意图的前提下,量化其最快到达本体的剩余时间,直接刻画最坏情况下的碰撞紧迫性。

◆ 将aTTC嵌入控制屏障函数框架,定义时间型障碍函数aTTC-CBF,取代传统距离/速度型CBF,实现本质上的&quot;前瞻式&quot;安全约束。

◆ 设计可微神经网络代理模型,使aTTC在标准CBF二次规划中可实时计算,兼顾理论严格性与工程可部署性。</td></tr>
<tr><td>2026-08-13</td><td>Control Barrier--Value Functions under Partial Observability: Safety Guarantees via Conformal Prediction<br><a href='http://arxiv.org/pdf/2608.13819'>论文</a></td><td>本文针对部分可观测的非线性控制系统，将控制屏障-值函数(CBVF)框架从全状态可观测推广到基于状态估计的控制场景。核心思路是利用共形预测为估计误差提供用户指定错盖概率下的概率边界，并将该边界纳入估计空间的安全分析，从而在真实系统状态上获得有限时域的随机安全保障。针对控制与扰动仿射的系统，作者进一步设计了一种基于二次规划的在线安全滤波器，实时求解以强制满足CBVF安全条件。文章还通过部分可观测避障仿真验证了所提框架的可行性。

◆ 将CBVF框架从完全可观测系统扩展到部分可观测系统，结合估计器实现安全控制综合。
◆ 引入共形预测方法，为状态估计误差提供具有概率保证的分布无关边界。
◆ 在估计空间中建立CBVF安全证书，并推导真实系统状态下的有限时域概率安全保证。
◆ 针对仿射系统提出QP在线安全滤波器，可实时强制执行CBVF安全条件。</td></tr>
<tr><td>2026-08-13</td><td>Safety-Critical Control for Quadrotor UAVs via Decentralized Navigation Functions<br><a href='http://arxiv.org/pdf/2608.13507'>论文</a></td><td>本文针对四旋翼无人机集群在学习模型不确定性下的安全关键控制问题展开研究。由于导航函数产生的参考力是全驱动的,而四旋翼只能沿机体竖直轴产生推力,作者设计了推力-姿态实现方案,将参考力转化为可行的控制输入,并量化了实现误差。

◆ 提出了分散式导航函数与四旋翼欠驱动特性之间的推力-姿态桥接方法,有效解决了全驱动参考力到实际控制输入的转换问题。

◆ 建立了实现动力学与参考动力学之间的误差量化分析框架,为后续安全保证提供了理论基础。

◆ 设计了聚合鲁棒高阶控制屏障函数二次规划安全滤波器,以最小代价修正名义推力,在高概率意义上保证两两碰撞避免。

◆ 将学习模型的不确定性纳入安全约束,通过鲁棒设计实现了在不确定性条件下的安全保障。该方法将分散式导航函数的协同规划能力与控制屏障函数的安全性保证相结合,为实际四旋翼集群的安全协同飞行提供了可行方案。</td></tr>
<tr><td>2026-08-13</td><td>Predictive Relative-Velocity Steering for Safe Robotic Manipulator Teleoperation in Dynamic Environments<br><a href='http://arxiv.org/pdf/2608.13284'>论文</a></td><td>本论文针对遥操作机器人在动态环境中因网络延迟或操作者注意力有限而难以及时避障的安全问题，提出了一种轻量化、模块化的主动避碰框架。该框架直接在末端执行器速度指令层面运行，通过预处理点云后基于碰撞时间（TTC）并结合超调保护来预测潜在碰撞，并利用罗德里格旋转公式旋转相对速度向量方向来改变运动轨迹。

◆ 提出基于速度指令级的轻量化模块化避碰框架，无需重构整个遥操作流水线，便于集成。

◆ 引入带超调保护的TTC预测机制，有效补偿点云处理延迟对实时性的影响。

◆ 采用罗德里格旋转公式仅改变相对速度方向而保持幅值不变，缓解了传统人工势场法在狭窄空间中常见的死锁问题。

◆ 通过多场景仿真与真实机器人实验验证，方法在末端避碰成功率上优于基线方法。</td></tr>
<tr><td>2026-08-12</td><td>IoT-Enabled Autonomous Maritime Navigation in Smart Ports: A Curriculum-Guided Shared Policy Learning Framework<br><a href='http://arxiv.org/pdf/2608.11597'>论文</a></td><td>该论文针对智能港口中物联网设备在部分可观测、密集交通条件下的自主导航难题，提出了一种课程引导的共享循环策略强化学习框架。该框架采用集中式离线训练与完全船端在线执行的边缘智能范式，兼顾部署可扩展性与实时决策可靠性。共享循环策略的设计使多个智能体能够复用同一网络参数，从而提升时序推理能力与训练稳定性。课程学习策略通过由易到难的训练任务安排，使智能体逐步适应复杂的高密度港口环境。实验结果表明，该方法在导航可靠性、避碰性能以及对未见密集场景的泛化能力方面均显著优于基线方法。

◆ 提出课程引导的强化学习框架，通过渐进式难度调度提升训练稳定性与复杂环境适应能力。
◆ 设计共享循环策略，实现多智能体参数共享与时序推理增强，便于大规模边缘部署。
◆ 采用集中训练与船端执行的IoT边缘智能架构，兼顾离线优化与实时自主决策需求。</td></tr>
<tr><td>2026-08-10</td><td>Whole-Body Planning for Humanoids Navigating Confined Spaces via Self-Collision Avoidance References<br><a href='http://arxiv.org/pdf/2608.10220'>论文</a></td><td>本文针对仿人机器人在高度受限空间中的运动规划难题，提出了一个三阶段全身运动规划框架。该框架在运动学可达的刚体体积空间内直接进行路径规划，避免了传统基于粒子抽象样条方法在密集障碍物和自碰撞约束下陷入局部最优的问题。研究将可微碰撞避免集成到可达性约束公式中，生成体积感知的引导轨迹，驱动全阶轨迹优化器在长时间跨度内求解。

◆ 提出三阶段全身运动规划框架，在运动学可达刚体体积上直接构建规划问题，规避了传统粒子抽象的局限性。

◆ 融合可微碰撞避免与可达性约束，合成体积感知引导，提升长时间跨度全阶轨迹优化的收敛质量。

◆ 以优化后的全身规划作为高质量参考，训练残差强化学习策略，实现对参考轨迹的鲁棒在线跟踪。

◆ 在Unitree G1平台上通过三项超过NIST应急标准的基准测试，在受限比Cr&lt;1.5的极端狭窄空间内，成功完成12至18秒、涉及复杂手脚接触的任务，而标准基线方法均失败；学习策略在大量域随机化的物理仿真中仍能稳定跟踪参考计划。</td></tr>
<tr><td>2026-08-10</td><td>Satellite Trajectory Optimization via Proximal Policy Optimization for Space Debris Avoidance<br><a href='http://arxiv.org/pdf/2608.09628'>论文</a></td><td>本文针对低地球轨道和地球同步轨道日益严峻的卫星碰撞规避问题,提出了一种基于近端策略优化(PPO)强化学习的自主避碰策略,并配套开发了开源高保真度航天动力学仿真器。在1000次确定性GEO场景测试中,该智能体实现了97.5%的避碰成功率,显著优于基于规则的方法(20.7%)和脉冲式delta-v规划器(27.5%)。

◆ 基于PPO的端到端强化学习策略,直接从状态映射到规避动作,无需依赖手工规则或预规划轨迹,具备自主决策能力。

◆ 构建开源高保真度航天动力学仿真平台,融合牛顿二体动力学、太阳与月球第三体摄动、燃料消耗模型以及可配置碎片场,贴近真实在轨环境。

◆ 采用课程学习与多目标塑形奖励函数,从生存时长、投影脱靶距离到delta-v消耗进行综合引导,提升策略收敛质量与燃料经济性。

◆ 建立了完全确定性的评估流水线,包括共享随机种子、逐回合日志记录与遥测数据导出,确保实验可复现并便于分析对比。</td></tr>
<tr><td>2026-08-10</td><td>Model-Based Systems Engineering Framework for SysML-Driven Design of Autonomous UAVs<br><a href='http://arxiv.org/pdf/2608.09547'>论文</a></td><td>该论文针对自主无人机这一复杂信息物理系统,提出了一种基于模型的系统工程(MBSE)设计框架,以SysML作为形式化设计骨干,通过需求层、功能分解层、逻辑架构层和物理/软件分配层四个相互关联的层次,系统化地结构化无人机开发过程。框架综合运用需求图、活动图、块定义图、内部块图、状态机图和参数图等多种SysML图,捕获无人机系统的功能、结构、行为、接口和性能等多维特性,并将逻辑架构系统化映射到ROS 2软件架构。

◆ 创新点一:构建四层关联的SysML驱动MBSE设计框架,贯通从利益相关者需求到物理/软件分配的全链路形式化建模,解决传统文档式开发中需求模糊、接口不一致和追溯性弱的问题。
◆ 创新点二:建立SysML模型元素到ROS 2组件的明确映射规则,即块对应节点、流端口与连接器对应话题、请求-响应交互对应服务、目标导向行为对应动作,实现系统模型与软件实现之间的无缝桥接。
◆ 创新点三:以自主起飞、航点导航、悬停稳定、障碍规避、返航和应急处理等典型任务场景为实例验证框架有效性,支持在仿真或物理部署前完成需求分配、接口定义、子系统职责划分和验证规划。</td></tr>
<tr><td>2026-08-10</td><td>UnsDrive: Towards Robust End-to-End Autonomous Driving in Unstructured Scenes<br><a href='http://arxiv.org/pdf/2608.09098'>论文</a></td><td>针对无结构矿山场景下端到端自动驾驶面临的弱路网结构、地形遮挡和视野退化等挑战，本文提出了UnsDrive系统。

◆ 基于多帧可见性线索构建未知感知的占据表征，显式建模占据、自由与未知三类空间，为规划提供更可靠的环境表达。

◆ 设计了基于流匹配的多模态轨迹规划器，并引入占据轨迹一致性损失和不确定性感知轨迹评分器，惩罚进入不可通行或未观测区域的轨迹，提升部分可观测条件下的驾驶安全性。

◆ 构建了面向矿区的闭环仿真平台MineLoop，可评估不规则路形、低能见度、重型车辆交互以及矿区特定工况约束。

在开放与闭环实验中，UnsDrive在轨迹精度、避碰能力和长时序驾驶鲁棒性上均优于强基线方法，验证了显式未知空间推理对无结构矿区自动驾驶的重要价值。</td></tr>
<tr><td>2026-08-07</td><td>CoCoNav: Conformal Control for Safe Robot Navigation in Crowds<br><a href='http://arxiv.org/pdf/2608.07751'>论文</a></td><td>CoCoNav是一个面向人群场景下机器人安全导航的框架,旨在解决行人运动预测不确定且易变所带来的规划难题。该方法通过在线保形校准(conformal calibration)动态调整轨迹误差边界,使系统能够自适应预测误差的漂移。核心创新在于提出了一种基于保形控制的比例-积分控制器,按预测时域分别调节误差包络,以维持长期的统计覆盖率,既不过于保守也不冒进。框架采用&quot;先松弛后验证&quot;(relax-then-verify)的规划策略,通过软约束MPC生成名义轨迹并配以应急机动,再由运行时验证环节判断其是否满足校准后的安全边界,从而保证求解可行性。

◆ 提出基于保形控制的比例-积分(PI)校准器,按预测时域在线自适应调整轨迹误差边界,有效跟踪非平稳预测误差的统计覆盖率。
◆ 设计&quot;先松弛后验证&quot;的规划架构,通过软约束MPC分离名义轨迹生成与安全验证,显著提升求解可行性并支持应急机动。
◆ 仿真与四足机器人实验表明,CoCoNav在避碰成功率、任务完成与导航效率之间取得了优于现有基线的综合平衡。</td></tr>
<tr><td>2026-08-07</td><td>Real-time Whole-Body Motion Planning for Mobile Manipulators Carrying Arbitrarily Shaped Payloads via Kinematically-Coupled SVSDF<br><a href='http://arxiv.org/pdf/2608.07005'>论文</a></td><td>本文针对移动机械臂在狭窄环境中搬运大型非凸负载的实时全身运动规划问题，提出了一套完整的规划框架。框架采用三层结构：前端基于链式分解的核函数碰撞检测方法，能够真实保留机械臂与负载的几何形状，并利用紧凑存储和位级查询实现快速检测。

◆ 提出链式分解的核函数碰撞检测前端方法，在紧凑存储和位级快速查询的支持下，精确保留机器人与任意形状负载的真实几何特征，避免过度简化。

◆ 设计中端预处理阶段，将前端路径转化为平滑可行轨迹，在无碰撞时直接执行以跳过耗时的后端优化，从而提升实时性。

◆ 提出运动学耦合稀疏体素距离场（KC-SVSDF），沿运动学链传播避障梯度，生成一致的全身逃逸方向，实现高效的轨迹优化。

通过消融实验、与现有方法的对比基准以及差速驱动移动机械臂的真实场景验证，表明该框架能够在复杂环境中可靠地搬运大型非凸负载通过狭窄通道。</td></tr>
<tr><td>2026-08-06</td><td>Design and Evaluation of a Touchscreen-Based Teleoperation Interface for Robotic Manipulators<br><a href='http://arxiv.org/pdf/2608.06219'>论文</a></td><td>本文针对核工业等复杂环境下表面接触任务的遥操作需求，设计并评估了一种基于触摸屏的机器人遥操作界面。◆创新点一：将连续手指运动直接映射为机械臂运动，提供比传统摇杆更精细的速度控制能力。◆创新点二：将控制与可视化集成于同一界面，使操作者能够更自然、直观地完成表面交互任务。◆创新点三：开展20人跨国家远程用户研究，综合运用运动学、生理与行为数据，对触摸屏、摇杆及单击自主模式三种控制方式进行多维度评估。实验结果表明，触摸屏界面使任务完成时间中位数从5.38分钟降至2.50分钟（减少53.5%），正弦路径覆盖率达90.7%（优于摇杆的84.1%），且认知负荷NASA-TLX评分由52降至43，显著优于摇杆控制。该研究为遥操作表面任务提供了一种易实现、性能优越且有效降低操作员认知负荷的解决方案。</td></tr>
<tr><td>2026-08-05</td><td>From Transparent Labware Segmentation to Collision Avoidance: A Real-Time Edge-Aware Perception Pipeline<br><a href='http://arxiv.org/pdf/2608.04769'>论文</a> | <a href='https://github.com/havishamy/TransYOLO_3D'>代码</a></td><td>本文针对透明实验室玻璃器皿因折射、镜面反射和缺乏稳定内部纹理而难以被传统分割方法准确识别的问题，提出了一种面向实时机器人碰撞规避的边缘感知实例分割与三维感知流水线。

◆ 提出了一种将轻量级边缘检测分支与一阶段实时实例分割主干相结合的框架，通过边缘引导注意力融合和无参数SimAM模块增强网络对透明物体边界轮廓的感知能力。

◆ 构建了包含3485张图像、21个类别的真实实验室玻璃器皿实例分割数据集LabGlass-IS，填补了透明器皿专用数据集的空白。

◆ 实现了Boundary F-score达到97.80的领先精度，超越FastSAM框架18.93个BF点，同时保持7.1ms的推理速度，参数量仅为最接近竞品的2.85%。

◆ 通过掩码质心的多视图三角化获取三维位置信息，构建保守的包围体碰撞约束，在真实机器人实验中实现93.3%的碰撞规避成功率。</td></tr>
<tr><td>2026-08-05</td><td>OmniRouting: A Semantic-Coupled Multimodal Benchmark for Constraint-Aware Spatial Reasoning in PCB Routing<br><a href='http://arxiv.org/pdf/2608.04434'>论文</a></td><td>本文提出OmniRouting,这是首个面向印刷电路板（PCB）布线推理的大规模基准,旨在评估大语言模型在严格几何、拓扑和电气约束下的复杂布线能力。该基准包含1681个工业级原理图耦合的PCB设计,涵盖板型几何、人类工程师布放的可布线元件、封装、焊盘位置、网络表、叠层信息及布线约束等真实数据。

◆ 首次构建大规模工业级PCB布线推理基准,填补了LLM在电子设计自动化（EDA）约束感知布线任务上的评估空白。

◆ 设计四类互补任务:几何布线推理、设计规则感知布线推理、电气功能推理以及工具增强的智能体布线,全面覆盖PCB布线的多维度挑战。

◆ 揭示了当前多模态大模型在路径规划、设计规则遵循和电气功能保持方面的显著不足,为未来研究提供了重要诊断依据。

◆ 将开源全部基准数据、评估代码及工具接口,推动PCB布线智能化和EDA领域LLM研究的可复现发展。</td></tr>
<tr><td>2026-08-04</td><td>Accelerating Human-Aware Robot Trajectory Generation via Diffusion and Consistency Distillation<br><a href='http://arxiv.org/pdf/2608.03159'>论文</a></td><td>本文针对非冗余机械臂在人类-机器人交互环境中难以同时满足碰撞避免、自碰撞避免及运动学约束的问题，提出了一种基于扩散模型和一致性蒸馏的约束运动规划框架。该方法利用RRT和RRT*算法生成满足约束的轨迹数据集，并以此训练扩散模型，通过引导采样实现约束满足的轨迹生成。为降低迭代扩散采样的推理时间，进一步引入一致性蒸馏技术。此外，损失函数中加入关节加权急动度正则化项，通过惩罚关节加速度的突变来提升轨迹平滑性。仿真结果表明，一致性模型能在100毫秒内生成150条候选轨迹，同时保持较高的任务成功率，并显著降低关节和末端执行器的急动度。

◆ 首次将扩散模型与RRT/RRT*结合用于非冗余机械臂的约束运动规划，通过引导采样直接生成满足碰撞和自碰撞约束的关节空间轨迹，突破了传统零空间次任务方法的局限。
◆ 引入一致性蒸馏技术，将扩散模型的迭代采样过程压缩为单步生成，使150条候选轨迹的生成时间控制在100毫秒以内，满足实时规划需求。
◆ 提出关节加权急动度正则化损失项，有效抑制关节加速度突变，显著提升生成轨迹的平滑性，有利于HRI场景中的安全性和舒适性。</td></tr>
<tr><td>2026-08-04</td><td>CUDA MPC: A GPU-Native Solver for Model Predictive Control<br><a href='http://arxiv.org/pdf/2608.03051'>论文</a></td><td>论文针对模型预测控制(MPC)在快速动态、高维或长视野场景下在线优化开销过大的问题,提出GPU原生求解框架CUDA MPC。

◆ 该框架将优化算法、执行模型与内存架构进行协同设计,采用沿视野并行的ADMM分裂策略,实现整个迭代求解在GPU设备上完成。
◆ 设计融合式CUDA内核,中间优化变量始终驻留在片上低延迟共享内存中,大幅减少全局内存访问与主机干预。
◆ 通过局部原子标志同步协议仅在相邻视野块之间进行通信,显著降低核函数调度开销。

实验结果表明,CUDA MPC能在0.1秒采样周期内完成100秒前瞻的避障停车优化问题,并在10智能体集中式协同任务中成为唯一兼顾实时性与无碰撞约束的求解器;相比基于张量框架的同一ADMM分裂实现,融合内核最高可获得965倍加速。</td></tr>
<tr><td>2026-08-04</td><td>Grasp Execution Without a Planner: Configuration-Space Grasp Distance Fields with Certified Safety &amp; Guaranteed Quality<br><a href='http://arxiv.org/pdf/2608.00600'>论文</a></td><td>本文针对多指抓取执行中规划轨迹易受扰动失效、需频繁重规划的问题，提出无需规划器的抓取距离场（GDF）方法。核心思想是在机械臂-手的构型空间上构建抓取候选构型的平滑softmin距离场，控制器直接沿负梯度方向以静止反馈律驱动抓取执行，从而完全消除了轨迹规划、存储与抓取选择环节。

◆ 提出构型空间抓取距离场（GDF），通过softmin聚合N个抓取候选构型，并证明其与真实集合距离的偏差上界为log N/ρ。

◆ 将控制命令通过CBF-CLF二次规划滤波，约束自碰撞、工作空间、物体与障碍物保持安全距离，并以松弛变量显式报告受阻情况，证明闭环安全集前向不变。

◆ 针对手-物接触切换非光滑问题，在预抓取构型处采用滞回切换抓取闭合与保持模式，并设计力矩质量CBF将实际抓取的力闭合裕度约束在保持起始时刻的规定容差内。

◆ 在固定基座机械臂与Unitree G1人形机器人上完成仿真验证，在50个物体中成功抓取并提起46个，已执行抓取中位保留94%的合成质量裕度，每个20ms控制步仅耗时0.09ms求解QP。</td></tr>
</tbody>
</table>
</div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-17</td><td>How Sampling Strategy Affects Imbalance Mitigation in LiDAR Segmentation: A Study of Structured vs. Random Point-Based Architectures<br><a href='http://arxiv.org/pdf/2608.16673'>论文</a></td><td>针对LiDAR点云语义分割中的类别不平衡问题，本文在DALES、S3DIS、STPLS3D三个数据集上系统比较了六种重加权方案和五种不平衡感知损失，并结合KPConv与RandLA-Net两种架构进行全面基准测试。研究发现传统的逆频率加权在某些场景下会使性能下降高达12%，颠覆了其在2D视觉中的传统认知。
◆ 首次系统性地揭示了采样策略（结构化vs.随机）与不平衡缓解方法之间的复杂交互作用机制。
◆ 通过损失景观分析，发现结构化采样下不平衡比率决定景观几何，而随机采样下景观对数据集几何高度敏感。
◆ 证明均匀权重在结构化采样架构中与复杂损失差距小于2%，但在随机采样中差距可达4.6%。
这些发现表明采样策略、不平衡程度与数据采集特性三者共同决定了有效的不平衡缓解方案，为不同点云架构下的策略选择提供了实用指导。</td></tr>
<tr><td>2026-08-15</td><td>LAPF: LLM-Agent-Based Path Finder Using the UAVScenes Dataset<br><a href='http://arxiv.org/pdf/2608.15175'>论文</a></td><td>本文针对无人机在复杂城市场景下自主导航的难题，提出了基于LLM智能体的路径规划框架LAPF。现有优化、机器学习和强化学习方法泛化性差，而现有LLM辅助方法缺乏智能体功能，在记忆、规划和工具交互方面存在局限。LAPF在UAVScenes数据集上进行验证，通过闭环认知架构实现了从感知到动作的端到端自主决策。实验结果表明，LAPF在开放场景和障碍物场景中分别达到97.1%和98.1%的路径效率，显著优于纯CoT提示方法，且无任何钳位事件，表现出优异的近目标稳定性。

◆ 构建集成感知、记忆、规划和动作模块的闭环认知架构，扩展了LLM辅助导航的智能体能力。

◆ 引入先验导航经验与思维链推理机制，使智能体能够基于历史信息和逻辑推理进行路径决策。

◆ 将每个检测到的危险与有界、度量中性的修正动作精确耦合，实现动态航点优化与环境反馈的持续融合。</td></tr>
<tr><td>2026-08-15</td><td>Beyond Overt Reactions: Analyzing Subtle User Emotional Response to Unexpected In-Vehicle System Behavior<br><a href='http://arxiv.org/pdf/2608.15048'>论文</a></td><td>本文聚焦于全自动驾驶汽车意外行为引发的用户微妙情绪反应，弥补了现有数据集多关注强烈情绪和外部交通状况的研究空白。研究通过驾驶模拟器，结合语音交互与平板次要任务情境，系统性地诱导并采集了用户面对车辆意外行为时的惊讶、困惑与挫败感反应。通过整合视频、音频和心率多模态数据，深入分析了面部表情、言语和生理层面的细微行为模式，揭示了复杂交互场景下用户反应的复杂性与多变性。这些发现强调了车辆需要具备识别乘客微妙行为并自适应调整的能力，为改善自动驾驶用户体验提供了重要的设计依据。

创新点：
◆ 构建了首个针对全自动驾驶场景下用户微妙情绪反应的多模态数据集，整合面部、语言与生理信号
◆ 在次要任务与语音交互并存的情境下研究意外事件引发的细微情绪变化，更贴近真实人车交互场景
◆ 揭示了微妙情绪行为模式与规律，为车辆自适应识别乘客状态提供新思路...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-14</td><td>Spatiotemporal Tube-Based Safety-Certificate for Autonomous Navigation of Articulated Vehicles<br><a href='http://arxiv.org/pdf/2608.14531'>论文</a></td><td>本文针对铰接车辆（如牵引半挂车、拖挂AGV、公路列车等）的自主导航难题，提出了一种基于时空管道的安全证书规划方法。核心思想是综合考虑铰接车辆各连接单元的运动学特性与摆动约束，为牵引车规划一条经过认证的路径，确保被牵引的整列挂车在允许修正范围内始终行驶于道路安全管道内。

◆ 提出时空管道规划框架，将挂车摆动约束与运动学耦合关系纳入统一规划，生成可证明安全的牵引车参考路径。
◆ 引入基于允许修正量的安全证书机制，使规划结果在修正范围内具备形式化安全保障。
◆ 针对多类型铰接车辆（半挂车、全挂车、AGV列车等）提供通用规划方案。
◆ 在复杂路况的卡车-挂车仿真中得到验证，证实方法在狭窄道路场景下的可行性与安全性。</td></tr>
<tr><td>2026-08-14</td><td>PILOT: Privileged Imitation Learning for End-to-End Motion Planning of Autonomous UAVs under Partial Observability<br><a href='http://arxiv.org/pdf/2608.14082'>论文</a></td><td>本文提出PILOT框架,一种面向部分可观测条件下视觉端到端无人机运动规划的特权模仿学习方法,通过双目标损失函数将计算密集的最优控制专家策略蒸馏到轻量级学生策略中,并在仿真实验中实现超过80%的计算开销降低,性能接近特权专家。

◆ 提出约束感知的特权模仿学习框架,通过双目标损失函数将最优控制专家的安全性与动力学约束知识蒸馏至学生策略,使神经网络在无形式保证的情况下仍倾向于满足约束。

◆ 设计基于时序卷积网络(TCN)的时空感知融合模块,融合历史深度图像与里程计信息推断任务相关的潜在上下文,以无持久地图记忆的方式增强空间感知能力。

◆ 构建轨迹参数化层将网络输出映射为结构化轨迹,在训练阶段显式施加连续性、动力学一致性及障碍物软惩罚,鼓励对未见观测的约束满足。

◆ 在四旋翼与固定翼飞机上的仿真以及室内外零样本实飞部署,验证了方法的跨平台泛化能力与工程实用性。</td></tr>
<tr><td>2026-08-13</td><td>Towards Socially Compliant Navigation in Deep Reinforcement Learning via Proxemics-Based Reward Modeling<br><a href='http://arxiv.org/pdf/2608.12917'>论文</a></td><td>本文针对拥挤环境中机器人导航的社会合规性问题,指出现有深度强化学习方法多侧重任务目标而忽视社交规范。为此,论文提出一种基于空间关系学的奖励函数设计,通过将霍尔个人空间理论建模为径向高斯混合场,并在机器人视野内计算局部社会代价。

◆ 提出基于霍尔空间关系学的径向高斯混合场模型,将行人个人空间编码为连续可微的代价场,提升社会信号的可解释性。

◆ 设计密集型社会奖励函数,兼顾导航效率与人际交互规范,弥补了任务导向奖励对社会合规目标表达不足的问题。

◆ 所提奖励可模块化集成到多种深度强化学习导航框架,具备良好通用性。

实验在多种人群密度与场景下进行评估,结果显示该方法在社会性指标上获得稳定提升,同时保持与基线奖励模型相当的导航性能,验证了方法的有效性与泛化能力。</td></tr>
<tr><td>2026-08-12</td><td>Motion-as-Prompt: Enhancing Motion Reasoning in Multimodal Large Language Models via Motion-Guided Cross-Frame Visual Prompting<br><a href='http://arxiv.org/pdf/2608.11655'>论文</a> | <a href='https://github.com/SunVictor23/MaP'>代码</a></td><td>本文针对多模态大语言模型在视频运动推理任务中因稀疏均匀采样导致关键运动信息丢失的问题展开研究。现有方法在处理长视频时往往忽略采样帧之间的细微位移和交互，限制了模型对物体运动、碰撞及因果关系的理解。

◆ 提出Motion-as-Prompt（MaP）框架，通过恢复稠密点轨迹并选择运动信息丰富的关键帧，将相邻采样帧间的运动轨迹直接标注在视觉输入上，使原本隐藏的位移、方向变化和物体交互变得对模型可见。

◆ 该方法采用轨迹引导的跨帧视觉提示策略，无需对MLLM进行训练或修改架构，仅作为即插即用的提示机制增强模型对运动的感知能力。

◆ 在CLEVRER和Something-Something-v2数据集上的实验表明，MaP显著提升了GPT-5.5等模型的运动推理准确率，分别获得4.2%和8.9%的提升，且不损害非运动类任务的性能，展现了良好的通用性与鲁棒性。</td></tr>
<tr><td>2026-08-12</td><td>IoT-Enabled Autonomous Maritime Navigation in Smart Ports: A Curriculum-Guided Shared Policy Learning Framework<br><a href='http://arxiv.org/pdf/2608.11597'>论文</a></td><td>该论文针对智能港口中IoT使能的自主海事设备在部分可观测、高密度通航环境下的可靠导航问题展开研究,提出了基于课程引导与共享循环策略的强化学习框架。该框架在边缘智能范式下采用集中训练、完全本地执行的策略,兼顾了部署可扩展性与端侧实时决策能力。实验在多个真实港口仿真环境中验证,所提方法在导航可靠性、避碰性能及训练稳定性方面均优于基线方法,并对未见的高密度场景具有良好泛化能力。

◆ 提出课程引导强化学习框架,通过渐进式任务难度调度提升策略在密集交通场景下的学习效率与稳定性。

◆ 设计共享循环策略结构,融合时序推理能力,有效应对部分可观测条件下的状态估计难题,同时支持跨任务规模化部署。

◆ 构建集中离线训练与全本地执行的IoT边缘智能范式,解耦训练成本与推理时延,适配资源受限的海上嵌入式平台。

◆ 在多个高保真港口环境中系统验证,证明方法对未见高密度场景具备强泛化能力,具备工程落地实用价值。</td></tr>
<tr><td>2026-08-09</td><td>Not an A11y: How Android Accessibility Exposes Mobile AI Agents to Indirect Prompt Injection<br><a href='http://arxiv.org/pdf/2608.08939'>论文</a></td><td>本文揭示了基于Android无障碍（A11y）树和视觉截图的自主移动AI代理框架存在系统性的间接提示注入安全漏洞。研究发现，恶意攻击者可以通过不可见的对抗性提示使MobileRun和Mobile-Use等代理放弃原始目标、突破上下文边界并执行未授权设备操作。

◆ 首次系统性地证明了Android无障碍元数据与视觉输入结合会引入间接提示注入漏洞，导致目标劫持、上下文漂移和未授权操作等多种攻击场景。

◆ 通过实证评估量化了攻击效果，MobileRun配合Gemma4:31B的攻击成功率达0.822，Mobile-Use配合Qwen3.6:35B降至0.150但仍存在上下文漂移问题。

◆ 提出了针对移动代理的攻击分类法，涵盖视觉隐藏与完全暴露等多种攻击场景。

◆ 指出当前移动代理架构将被动环境文本视为可信指令的缺陷，倡导采用零信任输入验证、专用安全代理和严格上下文隔离的防御机制。</td></tr>
<tr><td>2026-08-11</td><td>MPPI Planning with Gaussian-Based Human Cost Function for Social Navigation<br><a href='http://arxiv.org/pdf/2608.08323'>论文</a></td><td>该论文针对拥挤环境中机器人安全导航问题，提出了一种基于预测高斯交互场(PGIF)的MPPI规划方法。传统MPPI将行人视为静态点障碍物，低估了动态场景中的风险，而PGIF将行人轨迹预测沿整个规划时域前向传播，构建与运动方向对齐的各向异性高斯排斥场。创新点总结如下：

◆ 提出PGIF时空代价函数，将行人预测前向传播到完整规划时域，而非仅考虑当前位置
◆ 采用各向异性高斯排斥场，其方向与行人运动方向对齐，速度越快前向扩散范围越大
◆ 形成运动锥形危险区域，对进入行人行进路径的轨迹施加更强惩罚，从后方接近的轨迹惩罚较弱
◆ 代价函数具有闭式解且完全可并行化，不增加额外计算开销，保持实时规划性能
◆ 在300个随机人群场景、三个密度等级的实验中，PGIF-MPPI实现0%碰撞率，而vanilla MPPI最高达82%碰撞率

该方法在保持实时性的同时显著提升了密集动态场景下的避障安全性，验证了时空预测与各向异性建模在社交导航中的有效性。</td></tr>
<tr><td>2026-08-08</td><td>EgoTrack3D: A Modular Framework for Egocentric 3D Object Tracking<br><a href='http://arxiv.org/pdf/2608.08016'>论文</a></td><td>EgoTrack3D是一个面向自我中心RGB视频的模块化3D目标跟踪框架，旨在解决快速视角变化和部分遮挡下动态3D场景重建的难题。该方法将2D分割掩码提升到全局3D坐标系，并通过基于点的运动评分机制和基于体素的合并启发式策略来关联目标轨迹。论文的主要创新点如下：

◆ 提出模块化框架，直接从自我中心RGB视频重建并维护动态3D场景表示，突破了现有方法主要针对显式交互或静态场景的局限。

◆ 设计基于点的运动评分与基于体素的合并启发式相结合的关联机制，能够同时处理静态和动态目标的持续3D跟踪。

◆ 在Aria Digital Twin数据集上，PCL指标相对最强基线提升11%，验证了框架在复杂动态场景中的准确性。

◆ 在退化条件下用稀疏3D边界框估计替代稠密深度图，并结合交互引导的动态关联，展示了系统在真实部署约束下的鲁棒性。</td></tr>
<tr><td>2026-08-07</td><td>Drone-Assisted UAV-UGV Collaboration for Autonomous Navigation in Snow-Covered Terrain<br><a href='http://arxiv.org/pdf/2608.07797'>论文</a></td><td>本文针对高海拔积雪环境中传统导航方法失效的问题，提出了一种无人机-无人车协同的自主导航框架。该系统通过空中视角引导地面车辆在能见度低、地形不稳定的复杂场景中安全行驶。

◆ 设计了一种定制化的高效U-Net语义分割网络，结合新颖的合成雪景数据增强策略，在满足实时性计算约束的同时实现了96.5%的道路分割精度。

◆ 采用扩展卡尔曼滤波（EKF）融合机载GPS与IMU数据，将无人机定位的最大观测位置误差控制在±0.5米以内。

◆ 基于YOLOv5目标检测与无人机RGB-D深度相机构建视觉跟踪流水线，实现对无人车位置的精准估计。

◆ 提出结合分割信息的动态路径规划算法，能够针对积雪漂移实时调整路径，显著降低导航偏差。

整体而言，该工作通过空中感知与地面执行的协同，有效解决了雪盖地形下的自主导航难题，验证了多平台协作在极端环境中的应用价值。</td></tr>
<tr><td>2026-08-07</td><td>CoCoNav: Conformal Control for Safe Robot Navigation in Crowds<br><a href='http://arxiv.org/pdf/2608.07751'>论文</a></td><td>CoCoNav提出一种结合在线共形校准与运行时认证规划的人群导航框架，旨在解决行人运动预测误差不确定且可能漂移下的安全高效导航问题。现有反应式方法易产生振荡行为，预测式规划器常将预测视为精确或采用受限误差模型，而将保守不确定性集作为硬约束还会导致模型预测控制不可行。

◆ 提出一种面向特定预测时域的共形比例-积分控制器，自适应调节轨迹误差边界以调控长期经验覆盖率，使系统能响应预测误差的动态变化。

◆ 设计&quot;先松弛后验证&quot;规划机制，通过软约束MPC生成名义轨迹以保证求解器可行性，再将名义轨迹与应急机动一起基于已校准边界进行运行前安全认证。

仿真和四足机器人实验表明，CoCoNav在避碰安全、任务成功率和导航效率之间取得了优于对比基线的良好平衡。</td></tr>
<tr><td>2026-08-10</td><td>Unordered Landmark Visual Navigation<br><a href='http://arxiv.org/pdf/2608.06833'>论文</a></td><td>本文针对图像目标导航依赖时序视频流或深度传感器等强先验的问题，提出无序地标视觉导航（ULVN）框架，仅依靠RGB图像即可在无时间顺序和里程计信息的条件下完成导航任务。该方法将建图、定位与规划统一整合，系统性地缓解了感知混淆、错误关联和建图失败等问题。

◆ 基于几何校验与最大生成森林精炼的二维拓扑地图构建方法，直接从无序图像集合中生成鲁棒拓扑结构
◆ 图信念传播滤波器结合熵自适应融合的全局定位机制，摆脱对序列启发式的依赖
◆ 动态子目标规划策略，实现闭环导航中的稳定执行

在仿真和真实场景中的大量实验表明，ULVN显著优于当前最优方法。</td></tr>
<tr><td>2026-08-07</td><td>CrossTracer: Cross-Embodiment Navigation via VLA Model Reasoning and Trace Residuals Adapting<br><a href='http://arxiv.org/pdf/2608.06688'>论文</a></td><td>CrossTracer针对跨形态机器人导航中VLA模型忽略机器人本体运动约束的痛点,提出了一种基于自适应轨迹残差的两层框架,实现了语义推理与物理可行性之间的统一。框架将导航计划表示为归一化的图像平面航点,作为跨形态泛化的统一接口。

◆ 提出VL-Tracer模块,基于预训练VLA模型根据自我中心观测和灵活的目标描述预测初始导航轨迹

◆ 提出CE-Adapter细化模块,通过视觉可通行性线索、机器人本体身份和初始轨迹预测本体条件化的残差修正

◆ 提出CE-RRT*算法,将全景分割转换为机器人条件化的可通行性代价图,自动生成成本最小化的像素空间轨迹,避免昂贵的人工标注

◆ 构建NaviTrace基准,全面测试从观测、语言指令和机器人类型生成本体一致导航轨迹的能力,总分45.68超越Gemini-2.5-Pro达10.01分,提升28.1%

◆ 在轮式和腿足机器人上完成真实部署,验证了导航成功率和执行效率的提升,体现了方法的实用价值。</td></tr>
<tr><td>2026-08-06</td><td>A Low-Latency ASIC Architecture for Real-Time Line Segment Detection<br><a href='http://arxiv.org/pdf/2608.06439'>论文</a></td><td>本文提出了一种面向实时线段检测的低延迟ASIC架构，基于步长算法并针对硬件实现进行了深度优化，旨在解决传统深度学习方法资源消耗大、经典算法延迟不稳定的难题。该架构采用全流水线设计，每个时钟周期处理一个像素，具有确定性延迟特性，在45nm CMOS工艺下实现VGA分辨率325 FPS、全高清48 FPS的吞吐量，功耗仅25.54 mW，面积为0.412 mm²。

◆ 基于步长算法的硬件定制化设计，将五种ASIC优化技术融合：寄存器式行缓冲与数据复用、无乘法器MCM滤波、8类角度量化、类CAM的关联存储单周期匹配，以及优化的重复线段去除机制。

◆ 全流水线单像素/周期处理架构，实现确定性低延迟，适合实时嵌入式视觉系统。

◆ 在45nm工艺下相比90nm Line Hough变换ASIC，功耗降低49%，帧率提升超过1.6倍，125 MHz时VGA分辨率可达406 FPS，性能优势显著。

◆ 以极小的芯片面积（0.412 mm²）和低功耗（25.54 mW）满足边缘计算场景对实时性、低功耗与小型化的综合需求。</td></tr>
<tr><td>2026-08-06</td><td>Acoustic-driven millimetric helical robot: ultrasonic synergistic manipulation in confined fluidic environment<br><a href='http://arxiv.org/pdf/2608.05746'>论文</a></td><td>本文针对毫米尺度机器人在受限生物环境中声学驱动推进效率不足的问题，提出了一种协调多声场协同操控策略。该方法通过声辐射力与声学流动的协同作用，实现了毫米级螺旋机器人的可控运动，并显著提升了推进性能。通过多物理场仿真捕捉了复合声场下机器人的动力学行为，并在实验中验证了其平面导航、倾斜爬升和垂直运动等能力。半自主导航实验进一步证实了超声协同显著提升了机动性能，体外猪静脉血管测试表明该策略在生物相关受限条件下支持单向和往复运动。这些发现为声学微操控向毫米尺度拓展提供了机理依据，有助于推动需要灵活可控运动能力的生物医学应用。

◆创新点1：提出协调多声场协同操控策略，将声辐射力与声学流动耦合，突破毫米尺度机器人在受限环境中推进效率不足的瓶颈。

◆创新点2：通过多物理场仿真与实验相结合，系统揭示了复合声场下毫米级螺旋机器人的动力学机制。

◆创新点3：在猪静脉血管等生物受限环境中验证了单向与往复运动能力，拓展了声学操控在生物医学领域的应用前景。</td></tr>
<tr><td>2026-08-06</td><td>PathCover: A Fast Convex Decomposition along a Path via Randomized Iterative Space Partitioning (RISP) on Point Clouds<br><a href='http://arxiv.org/pdf/2608.05586'>论文</a></td><td>针对自主机器人导航中实时走廊生成的计算瓶颈,本文提出PathCover框架及其核心算法RISP,直接从原始点云数据构建凸多面体走廊。

◆ 提出RISP随机化迭代空间划分算法,在温和概率消除条件下实现期望线性时间复杂度,比现有走廊生成方法快一个数量级,同时保持相当的走廊体积。

◆ 沿任意无障碍参考路径生成重叠的无障碍凸多面体序列,可安全约束下游MPC和轨迹优化问题。

◆ 数学上严格证明算法有限步终止,并保证沿参考路径的连续推进。

◆ 在合成与真实LiDAR数据集上完成基准测试,并通过四旋翼高保真仿真与搭载实时LiDAR的四足机器人实物部署完成端到端验证,证实了算法的实时性与实用性。</td></tr>
<tr><td>2026-08-05</td><td>Toward Integrating Adaptive Experience Replay and Online Uncertainty Estimation in Safe Actor-Critic Optimal Control<br><a href='http://arxiv.org/pdf/2608.04732'>论文</a></td><td>本文针对安全强化学习中障碍物过滤、不确定性估计与经验回放通常被分开处理的问题，提出了一种集成式安全Actor-Critic最优控制架构。在该架构中，不确定性估计在线更新控制屏障函数所用的障碍几何形状，滤波干预与估计残差共同决定回放优先级，并且评论家从实际执行的动作而非标称动作中学习。作者在二维机器人导航任务中，对六种组件匹配的配置在相同训练预算、随机种子和扰动下进行了系统比较，包括中等后训练测试、十一级感知噪声扫描以及乘数为6.0的极端压力测试，在极端测试中集成配置在五个种子中均无接触并到达目标点。

◆ 提出将不确定性估计、安全滤波与自适应经验回放耦合的集成安全Actor-Critic架构。

◆ 利用在线不确定性估计动态更新控制屏障函数所用的障碍几何形状。

◆ 基于滤波干预和估计残差自适应调整经验回放优先级。

◆ 批评家从实际执行动作（而非标称动作）进行学习，更贴合真实控制行为。

◆ 给出有限训练下的回放曝光界和考虑估计误差与可行性的鲁棒屏障条件。</td></tr>
<tr><td>2026-08-05</td><td>A Vision-based Control Framework for Real-time Autonomous UUV Operations<br><a href='http://arxiv.org/pdf/2608.04723'>论文</a></td><td>本文针对无人水下航行器(UUV)在动态、视觉挑战性水下环境中的自主作业需求,提出了一种全集成视觉驱动的实时定位、导航与建图一体化框架。该框架能够在真实运行中同时实现网相对定位和全局定位,并实时生成连续的三维环境地图,显著提升了系统的鲁棒性和适应性。研究团队通过合成数据集(含真值)以及UUV实船自主导航实验对所提方法进行了全面验证,实验结果证明了其实时性能与稳健性。

本文的核心创新点可概括如下:

◆ 构建了面向UUV的全集成视觉定位-导航-建图一体化流水线,实现了多任务协同运行的端到端框架。

◆ 同步支持网相对定位与全局定位双模式,赋予UUV在网箱等受限场景与开阔水域的灵活作业能力。

◆ 在动态、视觉退化等复杂水下条件下实现了连续三维地图的实时构建,提升了环境感知的时间连续性。

◆ 通过合成数据与实船在线实验双重验证,兼顾了算法精度评估与工程落地可靠性,为海洋机器人现场部署提供了技术基础。</td></tr>
</tbody>
</table>
</div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-17</td><td>FlexWorm: Primitive-augmented Hybrid Contact-motion Planning for Suction-based Multi-segment Deformable Robots<br><a href='http://arxiv.org/pdf/2608.16853'>论文</a></td><td>本文针对多段吸附式软机器人在复杂环境中依赖人工设计步态的问题，提出了FlexWorm规划框架，实现了在三维复杂曲面上的自主导航。该框架将离散的吸附切换与连续的形变规划统一建模，在几何、碰撞和准静态可行性约束下生成可行运动序列，且与具体驱动方式解耦。

◆ 提出块式逆运动学混合搜索（IKHS），采用最佳优先搜索遍历吸附转移序列，仅在诱导出的自由块上求解逆运动学，显著降低搜索空间。

◆ 在IKHS基础上提出原始动作增强的混合搜索（PaHS），利用学习的观测-原始动作嵌入快速检索经过验证的短运动片段作为局部候选，检索失败时回退至IKHS。

◆ 在仿真多种地形中，规划成功率、转移质量和效率均优于对照基线，PaHS在保持成功率的同时大幅缩短规划时间。

◆ 在气动多段软机器人上完成重复硬件实验，验证了在驱动与吸附不确定性下的可执行性和在线恢复能力。</td></tr>
<tr><td>2026-08-17</td><td>Semantic- and Density-Aware Planning for Accessibility-Preserving Multi-Object Placement<br><a href='http://arxiv.org/pdf/2608.16741'>论文</a></td><td>本文针对家庭服务机器人在线多物体上架场景，指出已有方法难以同时兼顾语义组织、空间密集利用与机械臂可达性。论文提出语义-密度放置规划方法SDPP，融合语义相似度与空间邻近性对候选位姿排序，并利用可达性地图过滤不可达位姿。

◆ 提出语义-密度评分机制，在未知未来物体的在线条件下联合优化语义一致性与货架高密度占用。

◆ 设计可达性地图AM，运动规划前过滤不可达候选，并对降低剩余工作空间的放置施加惩罚以保留后续操作空间。

◆ 仿真结果显示SDPP在语义放置质量上显著超越现有基线，并取得最高平均货架密度，同时AM大幅缩短可行位姿搜索时间；家庭货架实物实验验证了整套流程的实际可部署性。</td></tr>
<tr><td>2026-08-17</td><td>KC-BFPRL: Knowledge-Guided Multi-UAV Collaboration for Grassland Restoration via Bilevel Formerpointer-Based Reinforcement Learning<br><a href='http://arxiv.org/pdf/2608.16326'>论文</a></td><td>本文针对大规模草地生态修复中多无人机协同的恢复区域最大化问题RAMP，提出了知识引导的双层FormerPointer强化学习框架KC-BFPRL。框架采用层次化分解策略，将复杂组合优化问题拆解为全局任务分配与局部修复规划，后者又细分为上层轨迹规划和下层修复区域分配，从而逐级降低求解难度。

◆ 基于Transformer编码器融合静态环境特征与动态无人机状态，实现异构信息的统一表征。

◆ 采用Pointer Network解码器结合鲁棒的Actor-Critic训练框架，提升序列决策能力与策略稳定性。

◆ 嵌入生态优先级规则与启发式逻辑作为结构化热启动，有效解决强化学习冷启动问题并严格保证约束满足。

实验结果表明，KC-BFPRL在最具挑战性的U8-R160场景下达到0.00%的最优性差距，运行速度比MAPDP快近三倍，充分验证了其在鲁棒性、可扩展性和实时性方面的优势。</td></tr>
<tr><td>2026-08-16</td><td>Tabletop Pen Manipulation With a Vision-Guided 4-DoF Arm<br><a href='http://arxiv.org/pdf/2608.15968'>论文</a></td><td>本文针对低成本四自由度机械臂（缺少腕部旋转关节）在任意姿态物体抓取中理论欠驱动的问题，提出了一种视觉感知与运动规划融合的解决方案。系统利用固定俯视相机采集桌面图像，由YOLO11n-OBB定向检测器识别书写工具的类别、位置和朝向，再结合相机内参和ArUco参考位姿将像素坐标转换为机器人坐标系下的位姿，同时通过颜色分类器完成颜色判定。核心策略是根据目标朝向选择动作：接近机械臂默认接近方向的目标直接抓取，角度偏差较大的目标则通过多次&quot;矫正扫掠&quot;逐步调整姿态直到可抓取。在七种书写工具上完成的326次运动实验中，196次为直接抓取、130次为矫正扫掠，最大可修正90度姿态偏差，证明通过任务感知的巧妙工程设计可有效补偿缺失的腕部旋转自由度。

◆ 融合YOLO11n-OBB定向目标检测与ArUco位姿标定，实现低成本视觉到机器人坐标的精确映射
◆ 提出基于朝向分级的混合运动策略，将直接抓取与迭代矫正扫掠相结合
◆ 验证在4-DoF欠驱动平台上可完成传统需5-DoF的桌面分拣任务，兼具经济性与实用性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-15</td><td>Accelerating Mixed Discrete-Continuous Motion Planning via Neural Graphs of Convex Sets<br><a href='http://arxiv.org/pdf/2608.15440'>论文</a> | <a href='https://neural-gcs.github.io/'>代码</a></td><td>该论文针对运动规划中离散决策与连续轨迹耦合所带来的计算瓶颈,提出一种基于学习的加速方法,将传统GCS(Graphs of Convex Sets)框架中耗时的凸松弛步骤替换为神经网络预测,大幅提升在线重规划的效率。

◆ 采用图注意力网络(GAT)进行单次前向传播,预测图中高概率候选路径,取代标准GCS中昂贵的凸松弛过程
◆ 设计轻量级排序网络按估计轨迹代价对候选排序,结合顺序评估与早停机制高效恢复近优运动规划解
◆ 在3D四旋翼避障、7自由度机械臂运动规划及平面接触推物等多样化机器人任务中验证方法通用性
◆ 相比标准GCS实现最高达两个数量级的加速,同时保持100%成功率,仅以解的少量次优性为代价...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-14</td><td>Spatiotemporal Tube-Based Safety-Certificate for Autonomous Navigation of Articulated Vehicles<br><a href='http://arxiv.org/pdf/2608.14531'>论文</a></td><td>本文针对铰接式车辆（如牵引半挂车、卡车拖车、自动导引车及公路列车等）在狭窄路径下自主导航的难题，提出了一种基于时空管的安全证书规划方法。该方法通过利用铰接链节间的运动学特性与摆动约束，为牵引车规划出一条经过认证的路径，确保被牵引的挂车系列始终保持在道路走廊范围内。核心思想是结合可允许的修正量对时空管进行修正，从而为整车在给定路线上提供路线安全证书。该规划方法在复杂路径下的卡车-拖车导航仿真中得到了验证。

◆ 提出时空管（spatiotemporal tube）规划框架，将铰接车辆的链节运动学与摆动约束统一纳入路径安全约束中。

◆ 通过可允许修正量对时空管进行修正，使得仅需规划牵引车的轨迹即可保证整个挂车链节位于安全走廊内。

◆ 为铰接式车辆自主导航提供了一种可认证的安全证书方法，能够在复杂狭窄路径下保证规划路径的安全性。</td></tr>
<tr><td>2026-08-14</td><td>Expected Free Energy-based Informative Path Planning for Robotic Mars Exploration<br><a href='http://arxiv.org/pdf/2608.14466'>论文</a></td><td>本文针对火星探索等未知环境下机器人自主探测任务,提出基于期望自由能(Expected Free Energy, EFE)的统一信息路径规划方法。该方法将主动推断中的EFE作为动作选择准则,首次将信息获取与目标搜寻两类目标融合于同一优化框架中,弥补了传统信息论方法仅优化单一目标的不足。机器人通过高斯过程建立对信息场的信念,并在严格路径长度预算约束下规划连续轨迹,通过最小化期望自由能实现高效探测。

◆ 提出以期望自由能为统一目标的信息路径规划准则,首次将信息建图精度与高价值区域定位融合为单一优化目标,克服了传统方法只能兼顾单一目标的局限。

◆ 构建基于高斯过程的信息场信念表示,并在硬性路径长度约束下进行连续轨迹规划,显式建模并平衡测量代价与行进代价。

◆ 在多组仿真实验中验证,该方法在相同预算设置下同时获得更准确的后验信息地图和更高的高价值区域定位准确率,优于多种信息论基线方法。

◆ 该统一且易调参的原则性策略降低了实际部署时的参数整定难度,有利于资源受限环境下自主机器人的工程化应用。</td></tr>
<tr><td>2026-08-14</td><td>Control-Informed Constraint Adaptation in Minimum-Time Trajectory Planning for Autonomous Racing<br><a href='http://arxiv.org/pdf/2608.14448'>论文</a></td><td>这篇论文针对自动驾驶赛车在极限动态下轨迹规划保守、控制误差被忽视导致性能损失的问题，提出了一种控制信息驱动的在线轨迹规划框架，通过运行时测量系统性的跟踪偏差，动态调整空间赛道约束并迭代扩展自由空间规划区域，使规划器在保持时间最优的同时补偿累积执行误差。

◆ 控制误差反馈机制：将控制层产生的系统性跟踪偏差实时反馈至规划层，打破传统模块化架构中规划与控制之间的信息壁垒。

◆ 约束动态自适应：根据实测跟踪误差动态调整空间赛道约束，迭代扩大可用规划区域，让规划器主动&quot;学习&quot;自身执行偏差。

◆ 时间最优保持：在补偿误差的同时维持时间最优性，既保证安全性又挖掘极限性能。

该方法在高保真闭环仿真中得到验证，在不增加计算负担（中位运行时间25毫秒）的前提下，单圈时间减少1.8秒，证明了该方法能系统性地释放模块化架构此前无法触及的性能。</td></tr>
<tr><td>2026-08-14</td><td>PILOT: Privileged Imitation Learning for End-to-End Motion Planning of Autonomous UAVs under Partial Observability<br><a href='http://arxiv.org/pdf/2608.14082'>论文</a></td><td>PILOT提出了一种面向部分可观测环境下基于视觉的无人机端到端运动规划框架，通过特权模仿学习将计算密集的最优控制专家策略蒸馏到学生策略中。该方法在仿真中对四旋翼和固定翼飞机均实现了与特权专家相当的性能，并减少了超过80%的计算开销，同时在室内外实现了零样本部署，验证了跨域泛化能力。

◆ 提出特权模仿学习框架，通过双目标损失函数将最优控制专家策略蒸馏为学生策略，兼顾规划性能与安全动态约束正则化。

◆ 设计基于时序卷积网络(TCN)的时空感知融合模块，从历史深度图像和里程计中推理任务相关隐式上下文，无需维护持久地图即可缓解部分可观测性问题。

◆ 引入轨迹参数化层，将网络输出映射为结构化轨迹，训练中显式施加连续性、动态一致性及障碍软惩罚，鼓励对未见观测的约束满足。</td></tr>
<tr><td>2026-08-13</td><td>ReflectFact: Self-Reflective Agents for Improving Comprehension and Reasoning in Multi-Hop Fact Verification<br><a href='http://arxiv.org/pdf/2608.12877'>论文</a></td><td>该论文针对多跳事实验证中多智能体方法的两大缺陷——智能体缺乏全局目标感知导致推理偏离,以及参数化知识与外部证据冲突影响判断,提出了名为ReflectFact的自反思智能体框架。

◆ 显式推理路径规划:通过解析隐含实体、将声明拆解为子问题并整合已验证事实,构建基于证据的推理路径,避免推理方向偏离。

◆ 证据漂移验证:当智能体回答仅复述其参数化先验时,要求其引用支持证据重新作答,从而校准证据偏离,确保理解的证据基础性。

◆ 推理反思验证:从全局任务视角对每一步推理进行复审,发现不一致时重新生成步骤,以纠正位置偏差和替换偏差等推理缺陷。

最终聚合经校验的推理链得出可靠结论,在HOVER和EX-FEVER数据集上分别超越最强基线3.32%和2.78%,达到当前最优性能,有效弥补了现有方法在理解与推理上的不足。</td></tr>
<tr><td>2026-08-12</td><td>Learning-Based Behavior Planning for Automated Driving: Real-World Integration and Deployment<br><a href='http://arxiv.org/pdf/2608.12198'>论文</a></td><td>本论文针对自动驾驶中学习型运动规划方法缺乏可解释性和难以保证安全性的问题，提出了一种混合规划架构，将机器学习的数据驱动优势与经典方法的可验证性和确定性相结合。核心思路是用深度神经网络理解复杂交通场景并提出驾驶行为建议，再由基于优化的监督层对建议进行验证，并强制施加可行驶性与安全约束。文章在真实城市数据上进行了开环研究评估驾驶行为，讨论了实现稳定闭环运行的系统集成要点，并报告了在研究车辆karl上的实车部署结果。

◆ 提出混合规划架构，将学习型行为建议与基于优化的安全监督相结合，兼顾性能与可验证性

◆ 设计深度神经网络用于复杂交通场景理解与驾驶行为提议

◆ 构建基于优化的监督层，显式强制可行驶性和安全约束，提升安全性与可解释性

◆ 完成从开环评估到闭环系统集成再到真实道路部署的完整验证链条...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-11</td><td>Risk-Aware Kinodynamic Motion Planning Under Uncertainty For Safe Navigation on Planetary Environments<br><a href='http://arxiv.org/pdf/2608.11175'>论文</a></td><td>本文针对行星环境中自主机器人在未知地形力学和感知不确定性下的安全运动规划问题，提出了一种风险感知的运动学动力学运动规划方法。该方法分两步进行：首先采用基于采样的AO-RRT规划器生成动力学可行且风险感知的渐进最优轨迹，然后以此为初解，通过序列凸规划（SCP）将其进一步优化为非线性优化问题。

◆ 采用条件风险价值（CVaR）作为风险量化指标，使规划器能够显式地考虑最坏情况下的尾部风险，而不仅依赖期望代价。

◆ 提出AO-RRT与SCP相结合的两阶段框架，将采样规划的速度与凸优化的局部精炼能力统一在同一流程中，保证了动力学可行性、风险感知与渐进最优性。

◆ 将该方法部署于真实硬件平台上，在行星地形仿真与实验中均验证了轨迹风险降低超过97%，证明了方法的实用性与鲁棒性。</td></tr>
<tr><td>2026-08-11</td><td>On the Sequential topological complexity of directed (parametrized) motion planning algorithms<br><a href='http://arxiv.org/pdf/2608.10990'>论文</a></td><td>本文针对运动规划问题中需要系统依次穿越多个预设中间状态、且动力学受方向性约束并依赖外部参数的情形，引入了有向(参数化)拓扑复杂度的序列类比(sequential analogue)。作者系统地建立了该新不变量的基础理论框架，推导出若干基本性质，并在多类典型空间上完成了具体计算。

◆首次提出&quot;有向参数化拓扑复杂度的序列类比&quot;这一新概念，将经典拓扑复杂度从单步规划推广到多步顺序规划，并融合有向动力学与参数依赖性。

◆证明了该不变量对底空间上的有向结构敏感——同一拓扑空间赋予不同的有向结构时，可获得不同的复杂度数值，从而突破了传统拓扑复杂度仅依赖底空间拓扑的局限。

◆为研究受约束、序列化的机器人运动规划问题提供了新的代数拓扑工具，兼具理论深度与可计算性。</td></tr>
<tr><td>2026-08-13</td><td>Real-World Cooperative Bimanual Dexterous Grasp of Large Objects from Single-View Observations<br><a href='http://arxiv.org/pdf/2608.10383'>论文</a></td><td>本文针对大型物体双臂灵巧协作抓取这一难题,提出了一套完整的真实世界抓取框架。现有研究多聚焦于顺序操作而非协作抓取,且受限于仿真环境,主要瓶颈在于难以获取完整三维模型并生成物理可行的抓取动作。该工作通过构建包含关节角、视觉观测与力信号的多模态数据集,训练了基于DDPM的抓取生成模块,能够从分割点云直接预测关节级抓取配置。框架整合了运动规划与在线抓取细化策略,仅依赖单视角输入即可合成可执行的双臂抓取,显著降低了对完整三维模型的依赖。在双臂机器人平台上的实验表明,该方法对未见过的不同几何与位姿物体均具有较高的成功抓取率。

◆ 首次在真实世界中实现面向大型物体的双臂协作灵巧抓取,突破了现有研究多停留在仿真或顺序操作层面的局限。

◆ 提出基于DDPM的抓取生成模块,直接从分割点云预测关节级抓取配置,无需完整三维模型,仅凭单视角观测即可工作。

◆ 设计了融合运动规划与在线抓取细化的执行策略,通过力信号反馈保证抓取的物理稳定性与可执行性。</td></tr>
<tr><td>2026-08-10</td><td>Whole-Body Planning for Humanoids Navigating Confined Spaces via Self-Collision Avoidance References<br><a href='http://arxiv.org/pdf/2608.10220'>论文</a></td><td>该论文针对仿人机器人在高度受限环境中的运动规划问题，提出了一套三阶段全身规划框架。研究核心是将运动学路径规划直接建立在可达刚性体体积空间上，而非传统的粒子抽象样条方法，从而有效避免陷入局部最优。

◆ 提出基于可达性约束的可微碰撞避免规划框架，直接在刚性体可达体积空间进行运动学路径搜索，生成体积感知引导轨迹。

◆ 设计三阶段级联规划流程，将运动学引导作为高质量参考输入到全阶轨迹优化器，解决长视野下复杂自碰撞约束的优化难题。

◆ 采用残差强化学习策略在线跟踪参考规划，在物理仿真域随机化下实现鲁棒执行。

◆ 在Unitree G1平台上完成三组超NIST应急响应标准的密闭空间测试任务，约束比Cr小于1.5，实现12至18秒含复杂手脚接触的可行轨迹生成，标准基线方法均告失败。</td></tr>
<tr><td>2026-08-10</td><td>4D-WAM: 4D Consistent World Modeling for Autonomous Driving<br><a href='http://arxiv.org/pdf/2608.10107'>论文</a></td><td>该论文针对自动驾驶世界-动作模型（WAM）仅基于2D视频训练、缺乏4D场景理解从而导致预测与规划不一致的问题，提出了4D-WAM框架。其核心思路是在训练阶段引入几何基础模型，对WAM预测的未来帧进行4D感知响应，并据此定义4D一致性损失，从而在不增加推理成本的前提下引导模型学习物理一致的4D场景表示。

◆创新点一：提出基于几何基础模型的训练时4D一致性监督机制，使模型能够理解、表示并预测4D一致的驾驶场景演化。

◆创新点二：发现WAM中的&quot;早期决策&quot;现象，揭示驾驶决策主要在早期高噪声阶段形成。

◆创新点三：提出面向决策的时间步采样策略，将4D监督集中作用于决策形成的关键阶段，进一步提升轨迹规划性能。

大量实验表明，4D-WAM能够有效建模4D一致的场景演化，并在NAVSIM-v1和NAVSIM-v2基准上取得了当前最优性能。</td></tr>
<tr><td>2026-08-10</td><td>Energy-Structured Latent World Models with Neural Time Fields for Physically Constistent Open-World Motion Planning<br><a href='http://arxiv.org/pdf/2608.09876'>论文</a></td><td>本文针对具身AI中物理一致的运动规划难题，提出能量结构化潜在世界模型（ELWM），通过将能量与动量显式嵌入潜在状态，结合耗散与控制端口保证严格因果转换，使模型能够从多模态RGB-D与惯性交互数据中学习可复用的物理知识，从而实现物理一致的未来预测。

◆ 提出Energy-Structured Latent World Model (ELWM)，将能量与动量显式编码进潜在状态，通过耗散与控制端口约束状态转移，从根本上解决现有潜在模型物理隐式吸收、无法形成可复用知识的问题。

◆ 构建Physics-Conditioned Neural Time Fields (PC-NTF)，将ELWM通过Eikonal方程融入到达时间场，生成物理信息驱动的导航策略，桥接预测式世界模型与安全可行的运动规划。

◆ 在保留场景的实验中全面优于基线方法：0.8秒运动预测NRMSE由0.36降至0.29，导航成功率从81.3%提升至89.7%，SPL从0.64提升至0.73，物理碰撞率从12.1%降至5.8%，Eikonal残差从0.083降至0.031。</td></tr>
<tr><td>2026-08-10</td><td>Entanglement-Free Trajectory Planning for Tethered Mobile Robots with a Slack Tether<br><a href='http://arxiv.org/pdf/2608.09860'>论文</a></td><td>本文针对带有松弛缆绳的系缆移动机器人，提出了一种能够在运动规划全过程中考虑缆绳缠绕状态的规划算法，能够在含静态障碍物的环境中计算出动态可行且避免缠绕的轨迹。该方法的核心思路是将缠绕避免约束整合到规划管线的每一个阶段，而非仅在轨迹优化阶段进行处理。算法采用三步式管线：首先构建系缆机器人无缠绕构型空间的拓扑模型，然后基于该模型生成满足无缠绕约束的候选路径，最后通过求解同伦约束的轨迹生成问题得到动态可行的最终轨迹。

◆ 构建了系缆机器人无缠绕构型空间的拓扑模型，为路径搜索提供几何基础。

◆ 基于拓扑模型生成满足无缠绕约束的候选路径集合，确保路径层面的安全性。

◆ 通过同伦约束的轨迹生成，将拓扑层面的缠绕避免与动态可行性相结合。

仿真结果表明，该方法能够有效避免缠绕约束的违反，生成更安全可靠的运动轨迹。</td></tr>
<tr><td>2026-08-10</td><td>FactorDrive: Adaptive Multi-Step Reasoning Driven by Planning-Critical Factors for End-to-End Autonomous Driving<br><a href='http://arxiv.org/pdf/2608.09591'>论文</a></td><td>该论文针对端到端自动驾驶中视觉语言模型空间物理证据融合不足、推理适应性粗糙以及推理路径优化未充分探索等问题，提出FactorDrive框架，以规划关键因子(PCFs)驱动自适应多步推理。◆构建PCF-CoT思维链数据集，将规划推理锚定于轨迹相关的空间物理证据，并围绕场景特定PCFs组织推理过程，使推理路径的组成与深度能够适配不同规划需求。◆设计质量搜索引导的分组相对策略优化方法(QS-GRPO)，将蒙特卡洛树搜索与轨迹级规划奖励结合，自动发现并优化具有更高规划质量的推理路径。◆在nuScenes开放环和NAVSIM闭环导向基准上均取得最先进的规划性能。</td></tr>
<tr><td>2026-08-09</td><td>360CityArena: A Realistic Virtual Urban Navigation Benchmark for Embodied Agents<br><a href='http://arxiv.org/pdf/2608.08814'>论文</a></td><td>360CityArena是一个基于360度视频构建的高真实感城市导航基准，用于评估具身智能体在城市环境中的探索与推理能力。针对现有户外基准在真实感和场景复杂度方面的不足，该工作以日本东京秋叶原地区为蓝本，利用602段360度视频重建了覆盖85条街道的城市场景，并精心设计了175个人工编写的任务。

◆基于真实360度视频重建高保真城市环境，覆盖东京秋叶原85条街道
◆构建175个人工编写任务，涵盖环境理解、路径推理和空间推理三大类别
◆任务系统性地覆盖定位、地标搜索、路径规划等城市探索核心能力

实验结果显示，即便是当前最强的Gemini 2.5 Flash模型，在该基准上的表现也远低于人类水平（17.1%对比77.3%），揭示了城市尺度具身导航与空间推理仍存在重大挑战。</td></tr>
</tbody>
</table>
</div>

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

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-07-30</td><td>ENCORE: Event-Assisted Complementary Motion Refinement for Learned Video Compression<br><a href='http://arxiv.org/pdf/2607.28020'>论文</a></td><td>ENCORE提出了一种事件相机辅助的学习视频压缩框架,旨在解决传统学习方法仅依赖RGB帧推断运动时在快速运动、模糊、低光照等场景下鲁棒性不足的问题。

◆ 提出互补运动表示(CMR),将对齐后的RGB-事件特征分解为共享的公共运动表示和模态特定的运动表示,充分利用两种模态的互补信息。

◆ 设计空间能量与冗余感知的校准模块(SERIC),用于识别事件相对于RGB的新颖且活跃的响应,抑制弱证据或冗余信息,并预测候选光流修正量。

◆ 引入能量感知路由机制(EAR),自适应决定光流修正的应用位置和强度,实现精细化的运动细化。

◆ 在多个数据集(BS-ERGB、HQ-EVFI、CED)上均取得一致性能提升,在BS-ERGB上最高实现20.80%的PSNR-RGB和22.14%的MS-SSIM-RGB BD-rate节省。

◆ 事件仅作为运动建模的辅助模态,RGB仍然是唯一的编码与重建目标,保证了框架的实用性和兼容性。</td></tr>
<tr><td>2026-07-29</td><td>Semantic-Aware Temporal Adaptation for UAV Anti-UAV Tracking<br><a href='http://arxiv.org/pdf/2607.26511'>论文</a> | <a href='https://github.com/XiaozhenQiao/SATATrack'>代码</a></td><td>该论文针对UAV反无人机跟踪任务,提出了一种语义感知的时序自适应框架SATATrack。由于观察者无人机和目标无人机同时运动,场景存在快速视角变化、运动模糊和视觉相似干扰物,使固定视觉表征难以可靠匹配目标。

◆ 核心创新一:语义感知上下文传播(SACP),利用稳定的目标语言描述作为语义锚点,在骨干网络各阶段引导跨帧时序上下文传播,有效保持快速外观变化下的目标身份一致性。

◆ 核心创新二:训练阶段引入对比正则化器,抑制模型对语义相似背景区域的响应,提升特征判别性。

◆ 核心创新三:推理阶段提出时序感知分布对齐(TADA),无需更新模型参数,在线融合近期帧特征估计与训练时统计量,缓解视频特定的测试时域偏移。

该方法在UAV-Anti-UAV基准上达到最优性能,同时在反无人机和无人机目标跟踪任务上也具有竞争力,验证了语义与时序自适应协同设计的有效性。</td></tr>
<tr><td>2026-07-28</td><td>Eddeep: a deep-learning framework for fast eddy-current distortion correction in diffusion MRI<br><a href='http://arxiv.org/pdf/2607.26292'>论文</a> | <a href='https://github.com/CIG-UCL/eddeep'>代码</a></td><td>本文提出Eddeep，一种用于扩散磁共振成像(dMRI)中涡流畸变校正的深度学习框架，旨在解决传统迭代方法(如FSL Eddy)计算成本高的问题。Eddeep将校正任务分解为两阶段：首先采用监督式图像翻译网络对扩散加权图像和b=0图像进行外观标准化，消除对比度差异以利于可靠配准；其次采用无监督配准网络在物理约束的二次畸变模型下，同时估计涡流畸变参数和体素间头动参数，实现单次前向传播完成校正。◆两阶段分解策略：先通过监督式图像翻译标准化图像外观，再通过无监督配准联合估计畸变与运动参数，简化了传统迭代校正流程。◆物理约束的二次畸变模型：将涡流畸变与头动参数在统一框架下联合估计，保证校正结果符合物理规律。◆单次前向传播推理：摆脱对迭代优化的依赖，显著降低计算时间，适合大规模研究和临床部署。方法在UK Biobank数据上训练，并在域内和域外数据集(Memodyn)上验证，在体素间抖动、扩散峰度残差、信号不规则性和互信息等多项指标上达到与FSL Eddy相当的校正质量，同时大幅提升推理速度。</td></tr>
<tr><td>2026-07-31</td><td>JADE-GS: Joint Allocation of Deblurring Evidence for Event-Assisted 3D Gaussian Splatting<br><a href='http://arxiv.org/pdf/2607.14990'>论文</a></td><td>JADE-GS针对3D高斯泼溅(3DGS)在运动模糊场景下的重建难题,提出了一种融合事件相机信息的联合去模糊框架。论文观察到事件双积分(EDI)的解析反演与基于学习的帧-事件联合复原这两种先验在不同区域具有互补性,各有所长。本文的核心思想是将二者的结合建模为空间证据分配问题,通过轻量级的空间先验路由器在像素级预测融合权重,生成额外的监督目标。

◆ 提出空间证据分配框架,将EDI解析反演与学习式复原两种互补先验在像素级进行自适应融合
◆ 设计轻量级空间先验路由器,仅利用模糊帧和事件流即可预测逐像素分配权重
◆ 路由器无需清晰参考图像训练,通过场景一致性与曝光测量作为自监督信号
◆ 优化完成后移除路由器,推理阶段保持原生3DGS渲染,无需生成式解码

实验表明,JADE-GS在基准上取得了领先的感知质量,在真实数据集上保真度最优,且训练开销远低于基于扩散的替代方案。</td></tr>
</tbody>
</table>
</div>

<h2 id='vlm'>VLM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-08-17</td><td>When State Becomes an Attack Surface: State-Semantic Injection in LLM-Driven Embodied Agents<br><a href='http://arxiv.org/pdf/2608.16806'>论文</a></td><td>这篇论文揭示了LLM驱动的具身智能体所面临的一种新型安全威胁——状态语义注入攻击。区别于以往针对用户输入的提示注入研究，本文发现智能体所依赖的环境状态信息本身也可被武器化，攻击者能够通过篡改场景描述、物体属性或空间关系等内容来操纵智能体的任务规划与行为决策。该攻击利用了具身智能体在任务执行中必须结合状态信息进行任务接地的内在特性，具有较高的隐蔽性与现实危害性。论文系统性地定义了此类攻击的威胁模型，并分析了其对SayCan、Code as Policies、VoxPoser等多种主流具身智能体架构的影响。该研究为具身智能体领域的安全防御机制设计提供了重要的理论基础与实践指引。

◆ 首次提出&quot;状态语义注入&quot;这一新型攻击范式，将智能体安全研究从用户输入层面拓展到环境状态层面
◆ 系统揭示了状态信息作为攻击面的安全风险，弥补了LLM具身智能体安全研究的空白
◆ 针对多种主流具身智能体架构开展攻击分析与验证，证实了威胁的广泛适用性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-17</td><td>Diagnosing Dense Same-Class Attribute Misbinding in Large Vision-Language Models<br><a href='http://arxiv.org/pdf/2608.16805'>论文</a></td><td>本论文针对大视觉语言模型在密集同类物体场景中将属性错误绑定到错误实例这一隐蔽问题,形式化定义了DSCAM(密集同类属性错绑)失败模式,揭示了传统问答准确率和物体幻觉指标都无法捕捉的盲区。

◆ 提出InstaBind-Lite受控基准,包含524张图像、529组同类实体群、1773个标注实例和9580个确定性问题,通过源实例标注将错误区分为无支持生成、识别失败和跨实例属性转移三类。

◆ 设计了绑定特异性指标,可量化属性转移的频率、邻接性、序数距离和干预效果,使原本模糊的错答变成可溯源的失败类别。

◆ 在5个开源和2个商业API模型上评估,开源模型平均错绑率19.84%,API系统为7.55%,且80%以上可识别转移来源于相邻实例。

◆ 实验表明定位优先和实例优先的干预策略仅对部分模型有效,InstaBind-Lite由此开启了&quot;模型是否真正知道每个属性归属于哪个实例&quot;这一传统基准无法测量的可靠性维度。</td></tr>
<tr><td>2026-08-17</td><td>Neurosymbolic Embodied Agents<br><a href='http://arxiv.org/pdf/2608.16794'>论文</a></td><td>本文针对语言模型生成的具身规划无法保证可执行性的问题，提出了一种神经符号智能体，将长周期家务任务分解为任务导向的视觉探索与受限符号规划两个阶段。第一阶段通过视觉语言模型和探索框架从第一人称观测与交互中获取目标相关谓词和实例绑定，生成符号化初始状态；第二阶段利用PDDL转移模型约束解码，使生成的动作token必须在可应用动作范围内扩展，并结合蒙特卡洛树搜索和域无关启发式评估可执行的后续规划。实验表明，在VirtualHome和ALFWorld上，4B至27B开源模型均能实现超过90%的成功率，且最小模型大幅超越27B直接视觉策略。

◆ 提出&quot;视觉探索+符号规划&quot;两阶段解耦的神经符号具身智能体框架
◆ 基于PDDL转移模型的约束解码机制，从结构上保证规划结果的环境可执行性
◆ 揭示约束解码与搜索具有互补性，单独使用均解决不到三分之一任务，组合后超过95%
◆ 相比扩展思维大幅减少生成token数，相比直接交互大幅减少模型可见图像数
◆ 残差失败可明确归因于状态获取阶段而非规划生成，无需任何专门训练...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-17</td><td>TransAnyText: Translating Arbitrary Text in E-commerce Images via Structured Visual Generation<br><a href='http://arxiv.org/pdf/2608.16284'>论文</a></td><td>TransAnyText针对跨境电商图像翻译中准确性、视觉保真度和可编辑性难以兼得的难题，提出了一种结构化视觉代码框架。该方法将图像文本翻译重新定义为从源图像和目标语言生成可渲染的HTML补丁，将语义生成与像素渲染解耦：由视觉语言模型负责视觉理解、跨语言翻译和结构化代码生成，扩散模型负责背景修复和像素级精修，最后通过确定性渲染合成最终图像。论文还设计了包含监督微调、特权差距加权自蒸馏和带可验证奖励的强化学习的三阶段后训练框架，并发布了多语言数据集TransAnyDataset和基准TransAnyBench。实验表明该方法在翻译质量、视觉一致性和可编辑性方面优于级联管线、开源端到端模型和闭源图像编辑系统。

◆将图像文本翻译重构为从源图像到可渲染HTML代码的生成任务，实现语义生成与像素渲染的解耦

◆提出三阶段后训练框架，包含SFT建立图像到代码映射、PWSD强化风格与布局令牌学习、RLVR优化任务级性能

◆发布多语言电商图像翻译数据集TransAnyDataset与评测基准TransAnyBench

◆提供兼顾翻译准确性、视觉保真和输出可编辑性的统一解决方案...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-17</td><td>Seeing Before Answering: Training-Free Visual Layer Profiling for Vision-Language Models<br><a href='http://arxiv.org/pdf/2608.16263'>论文</a></td><td>该研究揭示了LLaVA类视觉语言模型默认使用视觉骨干网络倒数第二层的脆弱性：在2个VLM和7个基准的14个模型-任务对中，13个并非最优，最佳层因任务和骨干网络而异。

◆提出将矩阵熵推广为视觉数据集熵VDE，仅用100个无标注样本即可预测各层性能，无需下游推理。
◆发现投影前VDE能有效追踪逐层准确率，排名最高的层在LLaVA-Video上覆盖了oracle最佳层。
◆揭示投影器虽重塑视觉几何但未抹除性能相关趋势，投影前VDE比投影后信号更强。
◆证明Gromov-Wasserstein距离投影后失效，仅可作视觉-语言对齐诊断而非层选择器。</td></tr>
<tr><td>2026-08-17</td><td>AdaSprite: Resource-efficient Online Co-Adaptation for V2I Systems Under Large-scale Data Drifts<br><a href='http://arxiv.org/pdf/2608.16188'>论文</a></td><td>AdaSprite针对车路协同(V2I)场景中视觉语言模型面临的分钟到小时级大规模数据漂移问题,提出在边缘服务器上协同适配多个视觉混合专家(V-MoE)骨干网络,既避免云端卸载的延迟与隐私风险,又克服设备端方法的精度损失。

◆ 通过协作式弹性扩展结合多级复用机制,优化专家生命周期,有效减少DRAM碎片化与负载不均。

◆ 利用V-MoE可预测的激活模式实现高效内存I/O复用,缓解内存-计算瓶颈。

◆ 引入双缓冲调度策略,充分利用专家稀疏性,降低异步适配带来的任务切换开销。

该系统探索了边缘资源受限下并发任务数目的性能上界,在弱边缘设备上可支持多达17个并发V2I任务(基线仅6个),SLO达成率提升1.6倍,吞吐量提升2.1倍,并支持用户在精度与并发度之间进行秒级权衡。</td></tr>
<tr><td>2026-08-17</td><td>SafeGesture: Evaluating Fine-Grained Hand Gesture Understanding in Vision-Language Models through Scenario-Conditioned Safety Interpretation<br><a href='http://arxiv.org/pdf/2608.16081'>论文</a></td><td>本文提出了SafeGesture基准，用于评估视觉语言模型在安全关键场景下对细粒度手部手势的理解能力，包含6种HaGRID手势与8种操作场景的4,800个评估样本，并系统测试了五种代表性VLM。

◆ 提出了SafeGesture基准，将手势识别与场景化安全推理结合，填补了VLM在安全关键操作场景中手势理解评估的空白。

研究发现存在显著的感知-推理脱节现象：GPT-4o手势识别准确率高达98.4%，但安全推理准确率仅为53.3%，Qwen2.5-VL同样存在45个百分点的差距。

◆ 揭示了&quot;感知-推理脱节&quot;现象，指出模型能准确识别手势却难以推理出场景适当的安全行动。

实验发现多数模型几乎不使用不确定性标签，且仅靠场景多数类先验（无视觉输入）即可达到58.3%安全准确率，超过多数被测模型，暴露出严重的标签偏置问题。

◆ 发现标签偏置的隐蔽性，证明高准确率可能掩盖模型依赖场景先验而非真正视觉理解的本质。

进一步分析表明，提供真实手势作为文本仅带来0.4至3.2个百分点的提升，所有模型安全准确率均不超过56.2%，说明核心瓶颈在于场景条件下的安全推理能力，而非手势识别本身。

◆ 明确指出瓶颈定位：场景条件安全推理是主要限制因素，而非视觉感知，为未来研究指明方向。</td></tr>
<tr><td>2026-08-16</td><td>SEER: Long-Context Reasoning via Selective Visual-Text Compression<br><a href='http://arxiv.org/pdf/2608.15962'>论文</a> | <a href='https://github.com/jiaweixu98/SEER'>代码</a></td><td>SEER针对长上下文推理中注意力计算复杂度高的问题，提出一种选择性视觉-文本压缩框架。该方法通过视觉扫描定位查询相关图像，仅在必要时才回溯检索原始文本，从而兼顾视觉压缩的高效与文本推理的精度。

◆ 提出选择性视觉-文本压缩策略，突破现有方法对全部内容统一压缩、牺牲关键信息精度的局限
◆ 在工具交互轨迹上进行监督微调，使模型自适应学习何时调用选择、何时调用检索工具
◆ 设计视觉扫描结合按需文本回溯的两阶段机制，融合视觉范式的高效与文本范式的精确

实验表明，SEER在LongBench基准上达到51.11%的平均准确率，较视觉文本基线Glyph-9B提升2.33点、较Qwen3-8B提升3.49点，同时相对全文本基线保留了平均提示词节省量。</td></tr>
<tr><td>2026-08-16</td><td>Conjunctive Poisoning in AI Supply-Chain Applications<br><a href='http://arxiv.org/pdf/2608.15913'>论文</a> | <a href='https://github.com/N-H-Arif/llm_temp'>代码</a></td><td>这篇论文揭示了AI供应链中一种被忽视的攻击面：提示包装器与配置元数据的联合投毒攻击。研究表明，恶意开发者可将看似无害的包装器与精心构造的元数据配对，在不修改模型权重、训练数据或推理后端的情况下确定性改变模型生成后的行为。

◆ 提出&quot;合取投毒&quot;攻击模型，通过嵌入包装器标记与加密绑定元数据的双重门控机制实现隐蔽激活

◆ 在15个开源与闭源LLM/VLM部署上系统评估该攻击的实际可行性

◆ 证明现有防御措施（包括静态元数据检查、包装器扫描器、PromptShield和SigStore签名）均无法有效应对此类威胁

◆ 设计轻量级中间件防御TIF-BAH，在推理时验证包装器完整性并记录行为证明

研究强调包装器与元数据的交互构成现代AI部署中未受保护的新执行层，暴露出模型权重和提示级防御所无法覆盖的部署时行为风险。</td></tr>
<tr><td>2026-08-16</td><td>CLARA: Clip-Level Multimodal Alignment with VLM-Derived Rationales for Hateful Video Detection<br><a href='http://arxiv.org/pdf/2608.15905'>论文</a></td><td>该论文聚焦于仇恨视频检测任务,指出仇恨信号通常由语音、音频、视觉等多模态线索的复杂交互产生,且具有短暂、隐式且时序依赖的特点,传统视频级表征难以有效捕捉。针对这一挑战,作者提出了CLARA框架,将视频建模为细粒度片段序列,以更精准地定位时序化的仇恨信号。

◆ 提出基于混合专家的片段编码器,实现多模态线索的自适应对齐,有效融合不同模态信息。

◆ 设计局部-全局片段对比学习目标,联合建模短期线索与长距离时序依赖关系。

◆ 引入由视觉语言模型生成的推理依据,并通过门控Transformer融入高层语义指导,增强模型对隐式仇恨含义的理解。

在三个仇恨视频数据集上的大量实验表明,CLARA consistently超越现有最优方法,消融实验与参数分析进一步验证了各组件的有效性。</td></tr>
<tr><td>2026-08-16</td><td>Beyond Single Object: Learning 3D Relations with Large Language Models<br><a href='http://arxiv.org/pdf/2608.15710'>论文</a></td><td>该论文针对3D大语言模型（3D-LLMs）目前只能处理单物体或场景描述、难以进行多物体间细粒度比较的核心缺陷，提出了一套完整的解决方案。作者通过构建专门的多物体指令数据集和轻量级交互模型，使3D-LLM具备了几何推理和物体间关系理解能力，并在新设计的应用基准上显著超越现有3D和2D视觉语言模型。

◆ 提出MO3D多物体3D指令数据集，专门要求细粒度的跨物体比较推理，弥补了现有3D-LLM数据在多物体关系建模上的空白。

◆ 设计Multi-3DLLM模型，采用极简的Patch-Interaction Transformer（PIT），能够在保留局部几何细节的同时，显式建模物体间与物体内的交互关系。

◆ 构建Mini-apps应用驱动基准（Shape Mating和Change Captioning），首次从几何理解与实际应用角度评测3D-LLM的多物体推理能力。

◆ 实验证明现有3D-LLM和2D-VLM在多物体比较任务上均表现不佳，缺乏以比较为中心的设计和几何感知能力，而Multi-3DLLM在所有基线上取得领先，并展现出向单物体分类任务的正向迁移能力。</td></tr>
<tr><td>2026-08-16</td><td>ConceptFormer: Learning Adaptive Latent Concepts for Query-Document Alignment in Visual Document Retrieval<br><a href='http://arxiv.org/pdf/2608.15698'>论文</a> | <a href='https://github.com/Neuir/ConceptFormer'>代码</a></td><td>视觉文档检索旨在从包含文本、布局、图表等丰富证据的文档集合中定位查询相关页面，现有方法依赖文本描述或局部视觉区域作为监督信号，难以充分捕捉复杂视觉结构。ConceptFormer提出了一种潜在概念表示学习框架，通过查询条件化的连续潜在概念桥接局部视觉证据与高层语义相关性，无需文本中间表示或原始视觉标注。

◆ 提出基于查询条件化潜在概念的中间表示方法，动态建模查询与文档间的语义对齐，摆脱对文本代理或固定视觉区域的依赖
◆ 训练阶段借助强视觉语言模型自适应确定潜在概念token数量，实现细粒度证据的灵活捕获
◆ 在多个视觉文档检索基准上取得显著提升，平均NDCG@10相对最强视觉检索基线和最强OCR文本检索基线分别提升16.7%和22.1%
◆ 分析表明潜在概念能有效连接局部视觉证据与高层语义，兼顾细粒度文本线索和复杂文档级视觉结构...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-16</td><td>AlloEgo-VLM: Disambiguating Allocentric and Egocentric Reference Frames in Vision-Language Models<br><a href='http://arxiv.org/pdf/2608.15605'>论文</a></td><td>本论文针对视觉语言模型在空间语义理解中面临的环境参照框架与自我参照框架歧义问题展开研究，揭示了现有VLM因训练数据不足而对隐含空间方向产生不一致响应的局限性。

◆ 构建了名为AlloEgo-View的新数据集，采用结构化空间表示方法，包含图像、查询与视角特定答案的三元组，并详细标注参考对象、目标对象、方向、参照框架及视角类型。

◆ 提出了AlloEgo-VLM消歧框架，可在查询模糊的情况下有效区分两种参照框架，并通过监督微调便捷集成到现有VLM中。

◆ 将框架部署到基于NVIDIA Isaac Sim的机器人平台，在开放式物体搜索任务中验证了其真实场景下的可行性与实用价值。

实验结果表明当前VLM在处理视角特定查询时存在明显不足，而AlloEgo-VLM展现了强大的参照框架消歧能力，为具身智能中的空间理解提供了新的解决思路。</td></tr>
<tr><td>2026-08-16</td><td>From Generalist to Specialist: A Context-Fusion Framework for Endoscopic Polyp Reporting with a Frozen VLM<br><a href='http://arxiv.org/pdf/2608.15580'>论文</a></td><td>本文提出了一种上下文融合框架,用于在冻结通用视觉语言模型的前提下实现内镜息肉报告的专科化,无需修改预训练权重即可引入可靠的专家知识。该框架融合两类上下文:由自监督息肉编码器检索的相关图像-报告对作为显式转导上下文,以及可学习的连续专家标记作为跨病例共享的隐式指令上下文。在2056张专家标注的公开内镜图像上的实验表明,该框架在数值、分类和报告生成指标上均显著优于直接冻结推理,在与通用VLM、任务专用预测器及权重适配方法的对比中取得了最强综合表现。该方法仅引入相当于冻结VLM参数量的0.006%的可训练参数,实现了极轻量级的专科适配。此外,当检索到的最相似案例包含正确目标类别时,框架可修正权重适配基线70.5%的错误,验证了显式证据对专科化的关键作用。

◆ 提出上下文融合范式,通过隐式指令上下文与显式转导上下文的协同,在冻结VLM上实现专科化,避免权重修改导致的预训练能力损失
◆ 设计自监督息肉编码器进行图像-报告对检索,提供查询特定的显式证据,实现零权重更新的知识注入
◆ 引入可学习连续专家标记作为跨病例共享的隐式指令,大幅压缩可训练参数量至0.006%
◆ 在统一接口下同时支持定量测量、Paris分类和形态学报告生成,验证了上下文融合作为通用VLM专科化策略的有效性...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-16</td><td>Catching Hallucinated Citations in Video-LLM Question Answering: A Self-Verification Pipeline and Verifier Ablation Study<br><a href='http://arxiv.org/pdf/2608.15574'>论文</a> | <a href='https://github.com/yogesh-iitj/grounded-video-qa'>代码</a></td><td>本文针对视频问答系统中视觉语言模型常以高置信度生成带时间戳引用却未真正得到帧画面支持的问题，提出了一种检索增强生成加事后逐帧自验证的闭环流程。每个创新点如下：

◆ 揭示了&quot;时间戳幻觉&quot;这一新型欺骗性错误：时间戳让用户感觉引用有依据，但实际上并未校验所述内容是否真实来自所引用帧。

◆ 设计了完整自验证管线：检索增强语言模型先生成带时间戳引用答案，再对每条引用帧独立复核后才呈现给用户。

◆ 通过三项验证设计的消融实验得出关键结论：直接询问视觉模型因迎合性完全失效（0%），盲目重新描述加通用大模型判断不稳定（0%–100%），改用小型自然语言推理模型则稳定捕获79%的伪造引用。

◆ 在Apple Silicon的MLX与Google Colab的CUDA双平台上实现并开源了完整管线与评测工具，兼顾本地与云端部署。</td></tr>
<tr><td>2026-08-16</td><td>CrossView: Can Vision-Language Models Reason Across Cameras?<br><a href='http://arxiv.org/pdf/2608.15539'>论文</a> | <a href='https://utaustin-swarmlab.github.io/CrossView'>代码</a></td><td>这篇论文针对当前视频理解基准测试局限于单摄像头场景的问题，提出了多摄像头视频理解这一全新研究方向。论文指出多摄像头推理并非单摄像头问题的简单扩展，而是面临上下文随视角数量扩展、遮挡处理、视角重要性判断以及跨视角证据融合等根本性挑战。为此，作者构建了CrossView基准，涵盖自动驾驶、安防监控、自我/外部视角视频和机器人四大领域，对多种模型进行了系统评估。实验结果显示，无论专有模型如GPT-5.2还是开源模型如Qwen3-VL，准确率均显著偏低，且开源模型差距明显。论文的核心创新点如下：

◆首次将多摄像头视频推理明确定义为区别于传统单摄像头理解的独立问题，揭示其在上下文管理、遮挡推断和证据融合等方面的根本性差异

◆构建了覆盖自动驾驶、安防监控、自我/外部视角和机器人四大真实场景的多摄像头视频问答基准数据集CrossView

◆通过大规模实验系统揭示了现有视觉语言模型在多摄像头联合推理任务上的严重性能不足

◆证实模型性能与其联合处理多视角信息的能力高度相关，为后续模型设计提供了明确方向

◆开源了完整的代码与数据集，推动多摄像头视频理解领域的进一步研究...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-16</td><td>UniFed-VLM: Federated Instruction Tuning for Vision-Language Models with Multiple Heterogeneity<br><a href='http://arxiv.org/pdf/2608.15516'>论文</a> | <a href='https://github.com/wangpengyu2004/UniFed-VLM'>代码</a></td><td>本文研究视觉语言模型(VLM)在联邦学习场景下进行指令微调所面临的多维异构性挑战,涵盖任务、模态和模型架构三个层面的异构。现有方法多基于简化假设,难以应对真实场景中复杂的联合异构问题。为此,作者提出了UniFed-VLM统一联邦指令微调框架,该框架包含联邦补偿子空间聚合(FedCSA)和两阶段协作蒸馏(TCoD)两个关键组件。FedCSA通过子空间对齐的参数高效适配器聚合机制,结合动态加权与补偿策略缓解异构性引起的参数冲突;TCoD则借助互蒸馏适配器(MDA)与基于专家混合的蒸馏策略,在异构模型间实现有效知识迁移。在多个基准数据集上的实验表明,该方法在多样化任务中取得了优于现有联邦学习方法的平均性能。

◆ 首次系统研究任务、模态和模型架构联合异构下的VLM联邦指令微调问题
◆ 提出FedCSA方法,通过子空间对齐的动态加权与补偿聚合缓解异构冲突
◆ 设计TCoD两阶段协作蒸馏机制,结合MDA和MoE蒸馏策略实现跨异构模型知识迁移...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-15</td><td>NumerosityVLM: A Cognitively Inspired Benchmark for Interpreting Numerosity Representations in Vision-Language Models<br><a href='http://arxiv.org/pdf/2608.15425'>论文</a> | <a href='https://github.com/fuy3/NumerosityVLM-Benchmark'>代码</a></td><td>核心贡献：本文针对视觉语言模型(VLMs)在数量感知能力上的不足，提出了认知启发的诊断基准NumerosityVLM，包含10800张合成图像，在六个受控条件下正交操控物体大小、空间排列和数量，并逐步剔除纹理、形状和颜色等因素。

◆创新点一：将数量与相关视觉因素解耦，通过正交实验设计避免传统计数基准中数量与大小、密度等视觉线索的混淆，从而能够精准诊断模型的纯数量感知能力。

◆创新点二：基于认知科学中人类婴儿前语言阶段即具备数量感知这一发现，构建了类人认知启发的评估范式，揭示当前VLMs在类人基础认知能力上的欠缺。

◆创新点三：多因素分析发现模型架构是性能方差的最大解释因素(partial ω²=0.325)，远超视觉条件的影响。

◆创新点四：通过层级探针分析发现，视觉编码器的早期阶段即出现线性可分的数量信号，且模型间性能差异主要源于语言模型组件，为架构改进提供了明确方向。</td></tr>
<tr><td>2026-08-15</td><td>FloodReasonBench: Benchmarking VLM Reasoning Segmentation for Embodied Flood Response at the Edge<br><a href='http://arxiv.org/pdf/2608.15410'>论文</a></td><td>本文提出FloodReasonBench,首个面向边缘端具身洪水响应的视觉语言模型推理分割基准。研究构建了源于真实场景的洪水专用推理分割数据集FloodResponseSeg,并在轻量视觉编码、分层分割推理与压缩中间表示等条件下对推理分割流水线进行系统刻画。实验基于NVIDIA Jetson AGX Xavier平台,揭示了推理精度、时延、能耗与通信开销之间的权衡关系。关键发现表明,通用预适应设置下精度随分区大幅波动,而洪水适配后跨分区精度范围显著收紧。

◆ 提出FloodReasonBench基准,专门评估VLM推理分割在边缘具身洪水响应中的表现
◆ 构建FloodResponseSeg数据集,源自真实洪水场景,涵盖响应相关标注目标
◆ 首次在轻量视觉编码、分层分割推理、压缩中间表示下系统刻画推理分割流水线
◆ 基于Jetson AGX Xavier实测,提供精度—时延—能耗—通信的端到端权衡分析
◆ 发现洪水适配设计空间比通用预适应具有更紧凑的跨分区精度分布...[摘要不完整，待更新]</td></tr>
<tr><td>2026-08-15</td><td>Remember Smarter: Visual History Compressor and Hyperbolic Experience Space for Robotic Memory<br><a href='http://arxiv.org/pdf/2608.15269'>论文</a></td><td>针对长时序机器人策略需紧凑访问历史观测与可复用经验、且不扩张VLA上下文的挑战，本文提出即插即用模块Remember Smarter (RS)，包含视觉历史压缩与双曲经验记忆两条互补分支。

◆ 视觉分支利用双向空间Mamba和因果时序Mamba对多视角patch历史进行压缩，并通过残差交叉注意力将压缩记忆暴露给面向动作的隐状态，同时保持VLM视觉token流不变。

◆ 经验分支将成功的最终层VLM状态存储于Poincaré VAE空间进行层次化组织，并以异步方式将检索到的经验转化为测地线提示token，避免阻塞动作推理过程。

该设计有效缓解了长时序任务中的上下文膨胀问题。当RS适配pi0时，在LIBERO-Plus上将总体成功率从53.6%提升至70.6%，并在真实机器人实验中显著增强了记忆保持与经验利用能力。</td></tr>
</tbody>
</table>
</div>

<h2 id='archive'>归档</h2>

> [点击查看所有历史论文归档](./docs/archive.md)


<h2>GitHub 实验室仓库监控</h2>

<h3>HKU-MARS (港大火星实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>5071</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4519</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2441</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1629</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1618</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1476</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1307</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1284</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>1042</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>1004</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>932</td><td>An efficient and consistent bundle adjustment for </td></tr>
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
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>212</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>207</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>184</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
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
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>877</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>702</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>663</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>654</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>596</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>574</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>573</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>568</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>552</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>518</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>502</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>464</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>453</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>448</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>334</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>313</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>301</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>285</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>263</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
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
> 更新于: 2026.08.18

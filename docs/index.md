# 计算机视觉领域最新论文 (2026.07.22)

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
<li><a href='#archive'>归档</a></li>
</ol>
</details>

<h2 id='slam'>SLAM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-21</td><td>Identifying and Determining Atmospheric Parameters of BHB Stars Based on LAMOST DR11<br><a href='http://arxiv.org/pdf/2607.19175'>论文</a></td><td>针对BHB星样本匮乏的问题，本研究基于LAMOST DR11大规模光谱巡天数据，系统搜寻并识别了13988条BHB星光谱，对应10236颗独立恒星，识别率达80%至90%，污染率低于10%。

◆首次将色指数信息整合到SLAM数据驱动的光谱标记流程中，有效解决了BHB星有效温度与表面重力之间的长期简并问题，显著提升了大气参数的测定精度。

◆在[Fe/H]金属丰度分布中识别出一个明显的凸起特征，证实大部分富金属BHB星属于银盘星族，为揭示银晕与银盘的过渡结构提供了新的观测证据。

◆在构建大规模BHB星样本的同时，同步标定了4282颗蓝离散(BS)星的大气参数。

该工作为后续多类蓝色恒星的统计研究与银河考古学...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-20</td><td>Lifelong Localization in Dynamic Indoor Environments Combining Odometry with Sparse Distance Sampling<br><a href='http://arxiv.org/pdf/2607.17852'>论文</a></td><td>本文提出了一种面向动态室内环境的终身定位框架，通过融合机器人里程计与稀疏距离采样实现鲁棒定位。该方法利用少量距离样本构建位置先验，能实时解决机器人绑架问题（kidnap problem），并能在时间维度上将该先验与里程计持续融合，逐步收敛至机器人真实位姿。

◆ 仅需16个稀疏距离样本即可达到接近完整LiDAR SLAM的定位精度，显著降低传感器成本、存储空间和传输带宽需求。
◆ 基于真实环境数据洞察，对动态障碍进行显式建模与学习，使框架在静态环境以及动态变化已被正确学习的场景中均具备可证明的收敛性保证。
◆ 借助稀疏距离采样替代高密度扫描，兼顾隐私保护与计算效率，适用于资源受限或对隐私敏感的实际部署场景。</td></tr>
<tr><td>2026-07-20</td><td>SLAM in Low-Light Environments: Project Report<br><a href='http://arxiv.org/pdf/2607.17699'>论文</a></td><td>本文系统评估了RGB相机在低光照环境下进行SLAM的极限性能。研究团队选取了六种代表性SLAM系统,涵盖特征点法、直接法、滤波法与学习方法,在LaMARia五个不同难度与光照条件序列上进行基准测试,并结合绝对位姿误差、相对位姿误差和控制点召回率进行多维评估。

◆首次对跨范式的六种主流SLAM系统在统一低光照基准下进行系统性对比,填补了现有研究在低光RGB-SLAM性能边界上的认知空白。

◆揭示了惯性融合与全局优化是低光环境下稳定跟踪的两个必要条件,只有同时具备二者的Kimera-VIO才能完整跟踪所有序列。

◆明确指出现有方法的不足之处:经典单目流程(ORB-SLAM3、DSO)与滤波法(OpenVINS)在低光下普遍失败或发散,即便能跟踪的DPVO和DPV-SLAM也产生约100米的绝对误差。

◆为未来低光SLAM研究指明方向,即发展低光专用的学习前端或重新引入多模态互补传感,具有重要的实践指导意义。</td></tr>
<tr><td>2026-07-20</td><td>Toward Site-Aware MR Art Exhibitions: A SLAM-Based Deployment Pipeline for Spatial Coherence and Exhibition Experience<br><a href='http://arxiv.org/pdf/2607.17665'>论文</a></td><td>本文针对大规模混合现实（MR）艺术展览部署缺乏系统性指导的问题，提出了一套基于SLAM技术的实用部署流程。研究者首先通过试点研究对比了基于标记（marker-based）和基于SLAM的空间对齐方法在MR展览中的表现差异，验证了SLAM在复杂展览环境中的优势。在此基础上，他们将空间对齐不仅视为技术手段，更视为影响展览体验的设计决策，构建了一个融合技术部署与策展理念的完整流程。该流程通过系统开销测量和用户主观体验反馈进行了双重评估，结果表明空间对齐质量直接影响展览的整体连贯性、访客的沉浸感与连续性以及对艺术作品的解读。最后，研究为未来大规模MR艺术展览的部署提供了具有实证依据的设计参考。

◆ 创新点一：将空间对齐从纯技术问题提升为影响展览体验的设计决策，强调技术与策展的融合。

◆ 创新点二：实证对比了基于标记与基于SLAM的对齐方法，为MR展览空间对齐方案的选择提供数据支撑。

◆ 创新点三：提出面向大规模MR艺术展览的系统化部署流程，弥补现有研究多停留在原型或个案层面的不足。

◆ 创新点四：从技术稳定性与用户体验双重维度评估流程效果，揭示空间对齐对展览连贯性、沉浸感及作品解读的多维影响。</td></tr>
<tr><td>2026-07-19</td><td>DROID-ANCHOR: Odometry-Anchored Recurrent Metric Depth Estimation<br><a href='http://arxiv.org/pdf/2607.17058'>论文</a></td><td>针对单目视觉SLAM系统的尺度模糊与尺度漂移问题，本文提出Metric-DROID，一种端到端循环架构，通过融合本体感知里程计将视觉SLAM锚定到物理度量空间，在保持视觉重投影精度的同时实现稳定的绝对尺度输出。
◆ LSTM更新算子将高频里程计序列编码为空间特征图，为迭代优化提供持续性的度量偏置，使网络在循环更新过程中有效保留运动学信息。
◆ 不确定性感知度量后端（BA_odom）将里程计视为带学习异方差协方差Σ_o的几何锚点，通过时变协方差自适应平衡视觉重投影与度量平移残差，显著抑制轮式滑动和传感器噪声的影响。
◆ 选择性残差微调策略在保留预训练几何先验的同时实现零样本度量对齐，避免破坏原有视觉特征表达能力。
大量实验表明，Metric-DROID在多个公开数据集上的度量深度估计精度和鲁棒性均显著优于现有方法。</td></tr>
<tr><td>2026-07-18</td><td>A BIM-enabled, Agent-based Discrete-event Simulation Platform for Robotic Studies: A Method based on Graph Theory<br><a href='http://arxiv.org/pdf/2607.16920'>论文</a></td><td>本文针对室内机器人在设施管理中的复杂任务需求，提出了一种基于BIM的多智能体离散事件仿真平台，实现知识驱动的导航与操作规划。研究将室内环境离散化为网格单元，并将其映射为图节点，根据与建筑元素的空间关系将其分类为目标、障碍或常规节点，通过为相邻节点间的边赋予通行代价，利用图论算法计算无碰撞的最优导航路径。仿真结果验证了图表示方法在避障与路径规划中的有效性，并通过网格细化解决了粗离散化导致的目标与障碍单元重叠问题，提升了空间精度和路径可行性。该平台支持机器人在实际部署前的虚拟评估，为BIM驱动的机器人系统应用于设施管理奠定了基础。

◆ 基于BIM的图论建模方法：将BIM几何、语义及运维信息转化为图节点与边，使机器人能访问超越传统导航的环境知识
◆ 多智能体离散事件仿真框架：支持知识驱动的室内导航与操作规划，可在部署前进行虚拟评估
◆ 节点分类与通行代价机制：通过目标/障碍/常规节点分类及边权分配，实现无碰撞路径规划
◆ 网格细化策略：有效缓解粗离散化引起的目标与障碍单元重叠问题，提升路径可行性与空间精度...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-18</td><td>GLidE-SLAM: GL-Accelerated Indirect-Direct Embedded SLAM<br><a href='http://arxiv.org/pdf/2607.16897'>论文</a></td><td>GLidE-SLAM 是一种面向嵌入式设备的单目混合视觉 SLAM 系统,通过将直接跟踪与间接建图在架构上解耦,有效解决了资源受限平台上跟踪与建图的算力竞争问题。系统利用 GPU 加速的图像对齐操作进行仅位姿估计的直接跟踪,避免深度优化和地图点创建,从而将高并行度工作负载卸载到 GPU,释放 CPU 资源用于后端的间接建图和地图维护。

◆ 架构创新:采用间接-直接混合的解耦设计,直接跟踪处理中间帧位姿估计,间接流水线专门负责地图扩展和全局一致性,实现跟踪与建图的并行高效协同。

◆ GPU 卸载策略:利用高度并行的图像对齐操作进行位姿跟踪,降低 CPU 负载,使后端任务能获得更多计算资源。

◆ 跨平台可移植性:使用厂商无关的 OpenGL ES 3.1 计算着色器实现直接跟踪器,无需 CUDA 支持即可部署在更广泛的商用嵌入式平台上。

◆ 首创性工作:据作者所知,这是首个通过计算着色器在嵌入式级设备上实现的完整直接光度位姿估计器。

◆ 性能优势:在目标平台上实现相比纯 CPU 基线最高 9 倍的帧率提升,同时保持轨迹精度,提升了在资源受限硬件上的实际部署可行性。</td></tr>
<tr><td>2026-07-15</td><td>Depth-Regularized JEPA World Models Learn More Transferable Representations from Real Outdoor Robot Data<br><a href='http://arxiv.org/pdf/2607.16314'>论文</a></td><td>该论文针对JEPA世界模型难以从复杂真实户外机器人视频中学习鲁棒动力学的难题，提出了一种融合深度几何先验的轻量化训练方法。

◆核心创新一：引入深度作为几何先验，在训练阶段对潜在表征施加监督，使模型直接学习符合三维场景结构的鲁棒动力学，从而应对户外视觉的复杂性。

◆核心创新二：将深度监督与SIGReg各向同性正则器相结合，在最大化任务无关潜在多样性的同时，按场景几何约束组织该多样性，目标是获得与几何一致的最高熵表示。

◆核心创新三：采用仅在训练时启用的过参数化策略，在不增加推理时间的前提下提升模型容量以应对更高复杂度。

在18M参数模型和真实农业机器人视频上的实验表明，该方法相比基线LeWM将视觉里程计探针误差降低33%，显著提升域内及TartanGround域外基准的惊讶分数分离度，并改善多步潜在推演在域外场景下的保真度，优势随推演步长增大而扩大。尤为关键的是，该方法在光照、阴影等与三维几何无直接关联的物理理解任务上同样带来提升，验证了深度作为物理基础先验可有效增强世界模型在多任务上的泛化能力。</td></tr>
<tr><td>2026-07-16</td><td>Immediate 3D Gaussian Splat Reconstruction of Unordered Input with Global Consistency<br><a href='http://arxiv.org/pdf/2607.14481'>论文</a></td><td>这篇论文提出了首个针对3D高斯泼溅(3DGS)重建的即时反馈方案,能够在无序图像输入下提供全局一致的重建结果。传统3DGS方法依赖有序序列或离线处理,而该方法突破了输入顺序的限制,实现了捕获过程中的实时可视化反馈。

◆ 利用视觉位置识别模型和共视性图(covisibility graph),提出了一种适用于无序序列的快速匹配方法,并能高效筛选高连接度关键帧,即使在有序序列下也能提升重建质量。

◆ 通过GPU优化和高斯基元(primitive)的精放置策略,实现了快速局部重建,在保持视觉质量的同时满足即时反馈的需求。

◆ 基于共视性图提出新颖的聚类(cluster-based)回环闭合方法,无需依赖顺序输入即可高效处理大范围场景中的回环问题,确保全局一致性。

◆ 引入渐进式层级结构(progressive hierarchy),使方法能够高效扩展到包含数千张图像的大规模环境,同时不牺牲计算效率。该方法在多个数据集上验证了其在无序输入下实现高质量即时3DGS重建的可行性。</td></tr>
<tr><td>2026-07-15</td><td>SeeSE3: Emergence of 3D Space in Vision Features<br><a href='http://arxiv.org/pdf/2607.14228'>论文</a></td><td>本文研究视觉基础模型的特征空间是否内在反映三维欧几里得空间的性质。作者以SE(3)变换群为分析框架，从拓扑与几何双重视角探测特征空间结构，区别于以往回归深度或法向量等图像级量的传统方式。

◆ 提出互近邻度量，从拓扑角度衡量特征邻域与空间结构的对齐程度。

◆ 设计Poincaré Adapter，测试相机运动几何在潜位移中的线性可及性。

◆ 发现自监督视觉模型的潜空间子结构与三维空间存在高度相关性，即使训练中未使用显式3D监督。

◆ 基于此提出&quot;潜空间导航&quot;方法，无需显式三维重建即可在潜空间中完成视觉里程计与定位。</td></tr>
<tr><td>2026-07-15</td><td>Improving Map Consistency in Graph-Based LiDAR SLAM Through Information-Aware Odometry and Retroactive Loop Closure<br><a href='http://arxiv.org/pdf/2607.13516'>论文</a></td><td>该论文针对图优化LiDAR SLAM中轨迹精度高但地图几何一致性差的痛点，提出了一套系统性的改进方案。

◆ 提出基于几何依赖的信息矩阵估计框架，为ICP里程计约束提供原理化的权重分配，从而提升位姿图优化的可靠性。

◆ 设计分层回环检测模块，将位置识别与几何配准解耦，增强回环检测的鲁棒性。

◆ 提出回溯式回环闭合模块，利用已优化位姿图恢复先前被遗漏的回环约束，进一步修正局部偏差。

◆ 建立专门评估重访位置地图一致性的评测协议，弥补现有方法在局部几何质量评价方面的不足。

实验在多个公开数据集上的结果表明，该方法在保持全局轨迹精度与现有先进方法相当甚至更优的同时，显著提升了重访区域的局部地图几何一致性，验证了不确定性感知里程计与几何引导回环精化耦合的有效性。</td></tr>
<tr><td>2026-07-15</td><td>Breaking Déjà Vu: Independent Auditing of Visual Place Recognition through Vision-Language Reasoning<br><a href='http://arxiv.org/pdf/2607.12818'>论文</a></td><td>本文针对视觉位置识别（VPR）在实际部署中依赖固定阈值、难以适应环境变化的核心痛点，提出了一种基于视觉语言模型（VLM）的后检索独立审计框架。

传统VPR方法在闭环检测等安全关键场景中容易因固定阈值导致误匹配，进而污染SLAM估计的轨迹与地图，而本文方法在检索阶段后对候选匹配进行独立实例级验证。

该框架利用VLM对查询图像与候选图像进行联合推理判断，无需架构特定的置信度度量、数据集相关阈值或部署环境的先验知识，具备良好的通用性。

在六个基准数据集、五种SOTA VPR方法以及四种VLM上的广泛实验表明，该方法平均将recall@1提升13.6%，同时将误接受率降至12%，并保持精度高于95%、覆盖率高于75%。

核心创新点如下：

◆ 提出视觉位置识别审计（VPR Auditing）概念，将VLM作为独立的后检索验证器，实现查询与候选图像的联合语义推理。

◆ 设计无需架构特定置信度、无需数据集相关阈值、无需环境先验知识的通用验证机制，摆脱对部署调参的依赖。

◆ 在多数据集、多VPR方法、多VLM的组合实验中验证了框架的普适性，显著提升召回率的同时有效控制误匹配风险。</td></tr>
<tr><td>2026-07-14</td><td>PixelLoop: Shortcut Topological Navigation with Pixel-Level Loops<br><a href='http://arxiv.org/pdf/2607.12811'>论文</a> | <a href='https://pixelloop-nav.github.io/'>代码</a></td><td>本文研究拓扑地图中的回环检测问题,聚焦于在纯拓扑表示中回环对导航的具体作用与下游影响。区别于传统基于全局位姿的SLAM回环,作者认为拓扑地图中的回环是连接不同路径的捷径,而非仅用于坐标对齐。

◆ 在像素空间直接引入回环闭合,提出PixelLoop方法,利用基于像素级相对3D几何的稠密拓扑表示,使回环作为稠密的拓扑捷径改变规划连通性和代价传播。

◆ 相比稀疏的图像级边或位姿图校正,像素级回环能够实现稳定的任意点到任意点导航,并生成与几何最短路径精确对齐的代价地图。

◆ 验证了将回环应用于细粒度像素拓扑相对于图像级拓扑的独特优势,在需要利用捷径的场景中提升最为显著。

在大量仿真实验中,PixelLoop相比图像级相对基线在成功率和SPL上均取得超过35%的绝对提升,并通过真实移动机器人部署进一步验证了稠密像素级回环作为拓扑视觉导航基础的实用性与鲁棒性。</td></tr>
<tr><td>2026-07-14</td><td>DiffRadar: Differentiable Physics-Aware Radar SLAM with Gaussian Fields<br><a href='http://arxiv.org/pdf/2607.12265'>论文</a></td><td>DiffRadar提出了一种基于可微物理感知高斯场的实时雷达SLAM系统，旨在解决传统雷达扫描匹配中离散化破坏几何连续性、导致位姿估计不稳定的问题。该方法将场景表示为各向异性高斯基元，通过可微雷达前向模型在距离-方位和多普勒-方位空间渲染观测，从而可直接从雷达信号联合优化机器人位姿与场景结构。

◆ 将雷达观测建模为可微物理感知高斯场，替代传统离散扫描匹配，保持几何连续性
◆ 采用各向异性高斯基元，通过可微前向模型在距离-方位和多普勒-方位空间渲染雷达信号
◆ 实现从雷达信号直接联合优化机器人位姿与场景结构，突破传统几何配准的局限
◆ 在商用FMCW雷达硬件上实现70 FPS实时运行

实验在Radarize基准及针对走廊退化、运动模式切换、动态杂波、长时回环等失效模式的压力测试套件上进行，结果显示轨迹误差显著降低，地图一致性提升超过一倍，尤其在特征稀疏的走廊场景下优势明显。</td></tr>
<tr><td>2026-07-13</td><td>Self-Healing Visual Recovery for Autonomous Ground Vehicles Using Camera-Only Visual Odometry<br><a href='http://arxiv.org/pdf/2607.11686'>论文</a></td><td>针对低成本仅用摄像头的地面机器人在循线行驶时易因遮挡或急转丢失引导线的问题，本文提出了一种轻量级的两阶段自愈恢复方法，无需激光雷达、GPS或GPU支持。
◆第一阶段通过原地旋转、逐步放宽颜色检测阈值并结合多帧确认来重新捕获引导线。
◆第二阶段利用单目视觉里程计回溯到预先保存的&quot;面包屑&quot;位置，为重新搜索争取空间。
◆整套系统在50毫秒控制周期内嵌入了完整的MAPE-K自适应循环，无需外部适配管理器。
◆系统融合深度门控HSV循线器、YOLOv8n障碍检测器与视觉里程计地图，在纯CPU硬件上达到20赫兹运行频率。
在Webots三个仿真场景共119次故障注入测试中，该方法成功率达86.6%，中位恢复时间为3.26秒，验证了仅依靠摄像头在成本与算力受限条件下实现可靠视觉恢复的可行性。</td></tr>
<tr><td>2026-07-13</td><td>GeoGS-SLAM: Online Monocular Reconstruction Using Gaussian Splatting with Geometric Priors<br><a href='http://arxiv.org/pdf/2607.11184'>论文</a> | <a href='https://rlgao.github.io/geogs_slam'>代码</a></td><td>GeoGS-SLAM提出了一种基于3D高斯泼溅的单目在线稠密重建系统，核心目标是解决现有方法依赖外部深度传感器或丢弃RGB信息导致重建质量下降的问题。系统首先利用预训练的前馈视觉几何模型从无标定RGB输入中预测相机位姿与场景几何先验，随后通过直接从RGB和几何先验中采样高斯基元来扩展场景地图。

◆提出融合3DGS表征与学习几何先验的单目稠密SLAM框架，无需外部深度传感器即可实现高质量重建。

◆设计从RGB和几何先验联合采样高斯基元的策略，并采用由粗到精的优化方式协同最小化光度与几何损失。

◆引入在线回环检测与位姿图优化以保证全局一致性，同时维持在线实时性能。

◆在室内外基准测试中取得了优于现有方法的渲染质量与跟踪精度。</td></tr>
<tr><td>2026-07-13</td><td>Desc++: Efficient Descriptor Enhancement for Data Association in Existing Visual SLAM Systems<br><a href='http://arxiv.org/pdf/2607.11099'>论文</a></td><td>本文针对视觉SLAM中传统手工描述符在光照和视角变化下鲁棒性不足、而学习型前端又需替换整个流水线的问题，提出了一种轻量级描述符增强模块Desc++。

◆创新点一：提出联合编码描述符表征与关键点几何信息的混合架构，将顺序无关的全局注意力与几何感知的序列建模相结合，在保持线性时间复杂度的同时增强上下文表达能力。

◆创新点二：增强后的描述符保持原始维度和匹配接口，无需修改现有流水线即可直接集成到已部署的V-SLAM系统中。

◆创新点三：在描述符匹配、对应点分析以及四个不同V-SLAM系统的系统级基准测试中，匹配精度超越现有最优增强方法，并将提升转化为更准确稳定的轨迹估计。

◆创新点四：在精度与效率之间取得良好平衡，适合实际集成到实时V-SLAM流水线中。</td></tr>
<tr><td>2026-07-12</td><td>Mapping Pamir: Multi-Session Visual-Inertial SLAM and 3D Reconstruction of an Underwater Shipwreck<br><a href='http://arxiv.org/pdf/2607.10925'>论文</a></td><td>本文提出了一种面向水下环境的多会话三维重建框架，使用低成本运动相机采集视觉惯性数据，并融合潜水电脑的水深信息以提升尺度估计。系统首先利用开源的SVIn2视觉惯性SLAM框架生成各会话的相机轨迹与稀疏重建，再通过COLMAP结构光束法进行全局优化与稠密重建。针对多会话数据融合难题，论文利用固定位置的标定靶估计不同会话间的坐标变换矩阵，从而将各次采集统一到同一参考系中。该方法被实际应用于巴巴多斯海岸的&quot;帕米尔号&quot;沉船，首次实现了沉船外部结构与可进入内部区域在两次会话中的完整三维映射，并在第三次会话中同时使用两台不同视场的相机进行联合采集。

◆提出结合消费级运动相机、视觉惯性SLAM（SVIn2）与COLMAP的级联式水下多会话重建管线，实现从稀疏定位到稠密建图的全流程处理。

◆将潜水电脑测得的水深信息融入视觉惯性数据，有效解决了水下单目尺度漂移问题。

◆利用固定标定靶估计会话间坐标变换，无需依赖外部定位设备即可实现多时段数据在统一坐标系下的融合。

◆首次对沉船内外整体结构进行多会话联合建模，并验证了异构视场多相机配置下的协同建图可行性。</td></tr>
<tr><td>2026-07-11</td><td>CSI-Assisted Edge SLAM Testbed Platform for 5G Connected Unmanned Autonomous Vehicles<br><a href='http://arxiv.org/pdf/2607.10394'>论文</a></td><td>本文设计并实现了一个面向5G连接无人车的CSI辅助边缘SLAM测试床平台,系统性地整合了定制无人地面车、基于ROS2的SLAM框架以及5G O-RAN系统,提供从机器人传感器数据经5G网络传输到边缘服务器进行SLAM处理的端到端跨层视角。论文深入分析了ROS2 DDS通信、RTPS报文封装以及5G用户面传输机制,并探讨了如何通过O-RAN组件提取和传递信道状态信息(CSI)以融入SLAM流水线。核心创新点如下:

◆ 构建了首个集成CSI感知能力的端到端边缘SLAM测试床,将无线电感知与机器人定位建图在5G O-RAN架构下深度融合。

◆ 实现了ROS2传感器数据流经5G O-RAN用户面传输的完整链路,打通了机器人中间件与移动通信系统的跨层接口。

◆ 提出了基于O-RAN组件的CSI提取与交付机制,使信道信息可作为新型感知模态被SLAM流水线直接调用。

◆ 通过真实实验揭示了通信感知一体化场景下延迟、数据流、同步及跨系统集成等关键挑战,为6G机器人平台设计提供了工程参考。</td></tr>
<tr><td>2026-07-20</td><td>AnythingReality: Robust Online Gaussian Splatting SLAM for Open-Vocabulary VR Scene Exploration<br><a href='http://arxiv.org/pdf/2607.09260'>论文</a></td><td>本文提出AnythingReality系统，首次将在线3D高斯泼溅、实时VR探索与语音驱动的视觉语言模型交互三者进行端到端集成，面向开放词汇VR场景探索任务。
◆ 采用ORB-SLAM3位姿估计与在线高斯重建相结合的鲁棒架构，专门针对含噪声的真实数据进行设计，打破了以往方法依赖干净深度或外部位姿的假设
◆ 构建支持增量重建的VR沉浸式探索管线，实现对动态生成场景的实时交互式浏览
◆ 设计语音驱动的语义模块，可转录语音指令、生成场景描述并自动记录兴趣点
实验结果表明，该方法在自建数据集与TUM-RGBD上的图像质量均显著优于当前最优的在线高斯泼溅方法（PSNR最高提升14.5%，LPIPS最多降低21.6%），并通过质量-速度可调配置保持可比或更优的帧率，最终实现了88%的VLM目标识别率，验证了开放词汇交互的有效性。</td></tr>
</tbody>
</table>
</div>

<h2 id='sfm'>SFM</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-20</td><td>Ergodicity of FIRE: star formation variations within and between simulated galaxies<br><a href='http://arxiv.org/pdf/2607.18005'>论文</a></td><td>本文研究了FIRE-2项目高分辨率模拟星系中恒星形成的遍历性,聚焦于星系偏离恒星形成主序(SFMS)的程度,以及集合平均与时间平均的恒星形成历史是否一致。

◆研究发现无论采用何种SFMS定义和恒星形成示踪量,单个星系的SFMS偏差都随时间趋向遍历性行为。

◆该趋势在不同形态星系中均成立,但核球主导的星系比盘主导星系表现出更小的SFMS偏差范围。

◆基于短时标(10^7年)的恒星形成示踪量比长时标(10^9年)能更快地收敛到遍历性。

◆研究还指出当前结论受限于样本规模,高红移演化以及活动星系核的影响有待进一步研究。</td></tr>
<tr><td>2026-07-20</td><td>Stability and Comfort in Mobile Robot-Pedestrian Interactions<br><a href='http://arxiv.org/pdf/2607.17604'>论文</a></td><td>本文针对公共空间移动机器人需保障行人舒适度的问题,为非完整约束移动机器人(NMR)提出了社会感知导航算法,通过理论分析、仿真标定与真实行人交互实验系统验证了其有效性。

◆创新点一:将社会力模型(SFM)与投影碰撞时间社会力模型(TSFM)相结合,显式建模行人的主观安全感受,克服了传统导航算法将行人简单视为动态障碍的局限。

◆创新点二:首次形式化NMR与行人及障碍物的交互过程,并在有界非被动行人假设下严格证明了系统的稳定性,填补了非完整约束机器人社会导航的理论空白。

◆创新点三:构建兼顾舒适度与速度的混合代价函数进行模型标定,并通过问卷统计分析与遥控基线对比,验证了所提算法在改善行人舒适度方面相对于已有方法的显著优势。</td></tr>
<tr><td>2026-07-17</td><td>HETA++: Global Structure-from-Motion with Hybrid Explicit Translation Averaging<br><a href='http://arxiv.org/pdf/2607.15912'>论文</a></td><td>本文提出HETA++，一种全局式SfM框架，针对传统平移平均方法在共线相机运动下退化或受异常值影响的问题，融合相对平移与特征轨迹进行混合显式估计。方法首先利用全局相机旋转精化相对平移并剔除全局不一致的相对平移，再采用基于凸距离的目标函数估计初始相机位姿与三维点，并通过非双线性角度目标函数进行精化。鉴于平移平均阶段相机旋转固定会限制位姿精度，进一步通过有界角度精化与重投影光束法平差对旋转和位置进行鲁棒联合优化，同时选取空间均衡分布的特征轨迹以提升效率。最终对所有可靠特征轨迹执行完整光束法平差，在多个序列与非序列真实数据集上实现了优于现有方法的精度、鲁棒性与计算效率。

◆ 提出融合相对平移与特征轨迹的混合显式平移平均框架，弥补单一信息源的不足
◆ 引入全局旋转精化相对平移并剔除全局不一致项，提升共线运动场景的稳定性
◆ 采用凸距离目标函数初始化位姿，结合非双线性角度目标函数进行精化
◆ 通过有界角度精化与重投影BA联合优化旋转与位置，并以空间均衡采样的特征轨迹提升效率...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-07-10</td><td>What VGGT Knows About Overlap: Probing Geometric Foundation Models for Co-Visibility<br><a href='http://arxiv.org/pdf/2607.09503'>论文</a></td><td>本文揭示了VGGT这一几何基础模型隐式编码图像对共可见性（co-visibility）的涌现能力，无需任何任务监督即可实现。研究发现其内部表征呈现类似大语言模型的层级结构：早期层构建3D场景感知表示，而晚期层则专门用于共可见性推理，其中第17层被识别为稳定的&quot;负锚点&quot;层。

◆ 发现几何基础模型中存在类似LLM的层级功能分化，并定位L17层为非共可见对的负锚点，为层专业化提供了任务驱动的实证。

◆ 提出Co-VGGT方法，冻结VGGT主干网络，仅训练一个轻量化的层级混合专家（MoE）头（参数少于7.5M），将每层视为自适应加权的几何抽象专家，从单目RGB直接分类共可见性。

◆ 在Co-VisiON基准上超越人类标注基线，相较先前工作提升超过25%（成对）和10%（多视角），且预测具有良好校准度（ECE=0.030），可作为可见性图的边权重直接用于下游SfM和SLAM流程。</td></tr>
<tr><td>2026-07-10</td><td>Glob3R: Global Structure-from-Motion with 3D Foundation Models<br><a href='http://arxiv.org/pdf/2607.09225'>论文</a> | <a href='https://junyuandeng.github.io/Glob3r'>代码</a></td><td>Glob3R是一个结合3D基础模型与全局优化的SfM重建框架，旨在解决现有前馈基础模型（如VGGT/Pi3X）在长序列或大规模无序图像上精度不足、分块处理易产生漂移和不一致的问题。其核心思想是显式优化基础模型的前馈几何预测，融合深度学习的强先验与经典几何的全局一致性。

核心创新点：
◆ 在冻结的Pi3X骨干网络上增加轻量级稠密匹配头，预测参考帧与邻近视图间的图像形变，并将其转化为稀疏但可靠的多视图特征轨迹，为全局优化提供对应约束。
◆ 提出基于关键帧的滑动窗口关联策略，通过跨重叠窗口传播轨迹和相对位姿，实现可扩展的大规模场景重建。
◆ 通过全局运动平均和光束法平差精修相机位姿、消除尺度不一致，并恢复稠密场景几何。

在室内、室外、大规模驾驶和无序SfM等多类基准上，Glob3R显著优于前馈基础模型基线和现有可扩展重建方法，且比经典SfM更具鲁棒性；精修后的位姿还显著提升了神经渲染质量，验证了基础模型先验与全局几何优化结合的有效性。</td></tr>
<tr><td>2026-07-10</td><td>Empirical Pedestrian Safety Assessment in a Mobile Robot Using a Predictive Social Force Model<br><a href='http://arxiv.org/pdf/2607.09192'>论文</a></td><td>本文针对移动机器人在人行道上与行人共享空间的安全性问题，提出并实证评估了预测型社会力模型。
◆将预测的社会力向量在有限时间范围内进行积分，构建了预测型SFM（PSFM）和预测型TSFM（PTSFM），拓展了传统社会力模型的预测能力。
◆在非完整约束移动机器人平台上系统对比SFM、TSFM、PSFM和PTSFM四种模型，结合客观安全指标（最小PTTC、平均速度、最小距离、轨迹曲率）与Likert量表主观问卷进行全面的实证评估。
实验发现PTTC的引入能够显著提升客观安全性能指标，但预测机制的额外贡献较为有限。
主观评价方面，部分参与者感受到预测方法带来更平滑的运动和更安全的速度，但Mann-Whitney检验未显示统计显著差异。
研究表明基于PTTC的导航能有效增强安全性，但在单行人场景中预测机制的附加价值尚不明显。</td></tr>
<tr><td>2026-07-09</td><td>Deep Spectroscopic Follow-Up of Maisie&#x27;s Galaxy -- A Typical Galaxy in the Early Universe<br><a href='http://arxiv.org/pdf/2607.08749'>论文</a></td><td>本文对高红移星系Maisie&#x27;s Galaxy进行了深度光谱研究,利用JWST两个Cycle 3 NIRSpec G395M项目共19小时以上的曝光时间结合MIRILRS观测,精确测定了其红移(z=11.408)、恒星形成率、金属丰度与电离参数等关键物理量。

◆创新点:首次将双Cycle 3 NIRSpec深度光谱与MIRILRS中红外观测相结合,实现对z&gt;10亮源的多波段全面光谱表征
◆创新点:通过[OII]双线精确测定电子密度与恒星形成率,发现该星系位于恒星形成主序上,表明早期宇宙亮源并非都是极端天体
◆创新点:利用Ne3O2比值首次精确测定了该红移处的金属丰度(Z/Z☉=0.17±0.05)与电离参数,并与SED拟合结果交叉对比验证

研究表明,先前被标记为&quot;极端&quot;的早期宇宙亮源实为典型星系,未来需要更深度观测以理解早期星系的平均性质。</td></tr>
<tr><td>2026-07-17</td><td>NoDrift3R: Raymap-Guided Coupling for Drift-Robust Unposed Feed-Forward 3D Reconstruction<br><a href='http://arxiv.org/pdf/2607.07168'>论文</a> | <a href='https://xiangyu1sun.github.io/NoDrift3R-project-page/'>代码</a></td><td>该论文针对无位姿前馈三维高斯溅射在长序列中因位姿漂移导致重建质量退化的问题，提出了一种几何与外观显式协同的新框架。作者识别出位姿累积漂移是制约性能的主要瓶颈，并指出SfM伪真值引入传感器噪声、纯渲染监督易陷入局部最优等矛盾。

◆ 提出Raymap-Guided Coupling Module（RGC）模块，将高斯中心锚定到光线图诱导的几何上，在统一目标下联合优化RGB重建、光线图一致性与相机正则化，形成几何与外观之间的双向反馈循环。

◆ 设计Dual-Frequency Viewpoint Scheduling策略，结合由易到难的间隔扩展与短间隔对回放，稳定长时序学习过程。

在域内和跨域数据集上的大量实验表明，该方法在渲染质量与位姿估计上均取得一致提升，长序列鲁棒性显著增强，验证了几何-外观显式协同是实现可扩展、无漂移无位姿前馈三维重建的关键。</td></tr>
<tr><td>2026-07-08</td><td>The MAGPI Survey: Evidence for Non-Universal Resolved Dust Attenuation Relations Beyond the Local Universe<br><a href='http://arxiv.org/pdf/2607.07122'>论文</a></td><td>本文利用MAGPI巡天（0.25&lt;z&lt;0.42）中178个星系的巴耳末减幅图，系统研究了中等红移下尘埃消光（A_V）与恒星形成率面密度（Σ_SFR）的空间分辨关系，并与本地MaNGA样本进行对比分析。

研究发现MAGPI星系中A_V与Σ_SFR存在显著正相关，但在固定Σ_SFR下其消光系统性高于本地MaNGA样本，表明两者之间存在整体性偏离。

◆即使在匹配恒星质量（M*）和偏离主序程度（ΔSFMS）后，MAGPI星系仍表现出更高的消光，说明空间分辨的A_V-Σ_SFR关系并非普适。

◆消光偏差的大小强烈依赖于星系在主序上的位置：低于主序的星系偏差最大（ΔA_V约0.40 mag），主序上星系约0.28 mag，高于主序的星系仅约0.07 mag，呈现明显的渐进趋势。

◆该结果揭示了kpc尺度上的消光不仅受局部恒星形成活动调控，还受宿主星系整体演化状态的影响，提示本地校准的消光关系不能简单外推至更高红移的星系研究。</td></tr>
<tr><td>2026-07-12</td><td>Deep far-UV observations of the ELAIS N1 field using AstroSat: Source catalogue, spectral energy distribution modelling and star formation<br><a href='http://arxiv.org/pdf/2607.06143'>论文</a></td><td>本文利用AstroSat卫星上的紫外成像望远镜(UVIT)对ELAIS N1深场进行了F154W波段(far-UV)的深度观测,总曝光时间达30千秒,通过CCDLAB v3.0进行数据处理,获得了1637个3σ和458个5σ的FUV源目录,极限星等分别为25.69和25.13 mag(AB),为该天区提供了目前最深的FUV测光数据。

◆ 基于多波段交叉匹配,结合光学和红外数据以及光谱/测光红移,采用多波段判据剔除活动星系核(AGN),构建了清洁的恒星形成星系样本。

◆ 使用CIGALE进行SED建模,采用延迟型恒星形成历史(可叠加晚期暴发)、Bruzual &amp; Charlot恒星 population合成、Calzetti消光和SKIRTOR AGN模块,系统地推导了样本的恒星形成率(SFR)、总恒星质量和年轻恒星质量随红移的演化。

研究发现SFR随红移单调上升,符合恒星形成主序(SFMS)的演化趋势,同时年轻质量与总质量比值在0&lt;z≲0.76范围内近似为常数,表明样本中的星系主要以自调节的稳态恒星形成为主,而非星暴主导的演化模式。</td></tr>
<tr><td>2026-07-06</td><td>Reference-Induced Consensus for Selective Posed-Reference Visual Localization<br><a href='http://arxiv.org/pdf/2607.04722'>论文</a> | <a href='https://github.com/SNU-DLLAB/ric_loc'>代码</a></td><td>本文提出RIC-Loc（参考诱导共识定位），一种无需场景训练和SfM预建图的位姿参考定位方法。其核心思想是利用冻结的VGGT模型同时预测查询图像的局部位姿、深度以及查询与参考之间的对应轨迹，每个参考图像诱导生成一个SE(3)假设，通过鲁棒共识机制估计最终位姿，并基于保留的假设结构计算两种可靠性分数。

◆ 摆脱对预计算SfM三维点图、2D-3D匹配和PnP求解的依赖，仅利用已知参考位姿即可实现SfM-free的轻量级定位流程。

◆ 提出假设驱动的双可靠性分数互补机制（空间散布与轨迹条件协方差），在无需真值的条件下实现跨室内、室外及低纹理大场景的失败检测。

◆ 共识估计器无需逐场景训练，在室内与基于结构的定位方法具有竞争力，并优于同类前馈基线，为位姿参考定位提供了有效的选择性操作模式。</td></tr>
<tr><td>2026-07-04</td><td>PRISM3D: Probabilistic Refinement and Robust Initialization for Physically Consistent Scene Modeling under Extreme Motion Blur<br><a href='http://arxiv.org/pdf/2607.03855'>论文</a></td><td>本文针对极端运动模糊图像下的盲三维场景重建难题,提出统一框架PRISM3D,突破了传统SfM在严重退化输入下失效的瓶颈。其核心创新与贡献如下:

◆ 提出基于VGGSfM密集跟踪的鲁棒初始化策略,在特征匹配失败的极端模糊条件下恢复全局拓扑,是首个有效利用该范式从极端运动模糊引导3D高斯泼溅自举的工作。

◆ 提出概率-物理耦合优化方案,采用MCMC进行几何概率致密化以稳健填充稀疏先验,同时通过连续贝塞尔轨迹建模物理图像形成过程,有效避免确定性优化发散。

◆ 进一步提出多模态扩展PRISM3D-E,融合高时间分辨率事件流作为结构先验,显著提升重建保真度。

◆ 同步贡献了PRISM3D-E基准数据集,填补了严重退化条件下配对事件流数据缺失的空白。

大量实验表明,所提RGB单模态框架与多模态扩展均建立了新的最先进性能。</td></tr>
<tr><td>2026-07-03</td><td>Fast 3D Foundation Model Initialized Gaussian Splatting<br><a href='http://arxiv.org/pdf/2607.03209'>论文</a></td><td>本文提出了一种无需传统SfM的快速3D高斯泼溅重建方法,利用3D基础模型进行相机位姿和点云的初始化,并通过深度引导损失函数联合优化位姿与高斯基元,显著提升了收敛速度。实验表明,该方法在Mip-NeRF 360、Tanks and Temples和RobustNeRF数据集上取得了23.61 dB PSNR和0.19 LPIPS的竞争性重建质量,同时将训练时间压缩至每个场景约三分钟,适用于机器人、VR和自动驾驶等近实时应用场景。

◆ 采用3D基础模型替代传统SfM进行相机位姿和点云初始化,摆脱了对COLMAP等耗时预处理流程的依赖。

◆ 提出深度引导损失函数,实现相机位姿与高斯基元的联合优化,即使在50-60张稀疏视角的粗略初始化下也能快速收敛。

◆ 引入基于MLP的位姿精修模块,结合基础模型的深度监督,在稀疏视角场景下进一步提升重建质量。</td></tr>
<tr><td>2026-07-01</td><td>Planar-SfM: Camera Pose Estimation via Homography Graph Embeddings<br><a href='http://arxiv.org/pdf/2606.31979'>论文</a></td><td>◆论文提出Planar-SfM，将传统SfM中被视为退化问题的平面场景转化为可利用的几何约束来源。

◆其核心思想是利用多视图中每个可见平面，通过单应性分解独立估计相对相机位姿。

◆方法构建基于单应性估计的位姿图，并引入谱嵌入来识别和剔除不可靠边。

◆该框架可将几何与视觉一致性映射到实线上，从而高效提取最大一致生成树用于位姿恢复。

◆实验表明，该方法在篮球场等高度平面场景中显著优于传统方法，同时在IMC Phototourism等通用三维场景中达到或超过现有最优水平。</td></tr>
<tr><td>2026-07-09</td><td>PanoImager: Geometry-Guided Novel View Synthesis and Reconstruction from Sparse Panoramic Views<br><a href='http://arxiv.org/pdf/2606.27071'>论文</a></td><td>◆ PanoImager针对稀疏全景图在旋转主导、弱视差场景下SfM/SLAM初始化不稳定的问题，提出了一个无需SfM的三维重建框架。
◆ 方法将全景图分解为局部透视视图，并利用前馈式位姿与深度先验提供初始几何约束。
◆ 通过几何条件扩散模型合成辅助新视角，补充稀疏输入中缺失的观测信息。
◆ 结合深度引导的3D Gaussian Splatting优化，提升跨视角一致性并稳定重建过程。
◆ 实验表明，该方法在极端稀疏全景输入下具有更好的鲁棒性，可作为SfM/SLAM失败时的离线地图细化组件。</td></tr>
</tbody>
</table>
</div>

<h2 id='image-matching'>Image Matching</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-21</td><td>NGPS: GPS-Denied Aerial Geo-Localization and 2.5D Reconstruction via Deep Satellite Image Matching and Multi-Rate Sensor Fusion<br><a href='http://arxiv.org/pdf/2607.18936'>论文</a> | <a href='https://github.com/snktshrma/ngps_flight'>代码</a></td><td>本文针对高空无人机在GPS拒止环境下的定位难题，提出NGPS视觉地理定位框架，通过将下视图像与地理参考卫星影像进行深度特征匹配实现无GPS绝对定位。系统在60-150米高度的5个飞行序列上达到2.94米位置RMSE，最差情况下ATE为6.04米，相比单目VIO提升3.5倍，并在NVIDIA Jetson Orin NX上实时运行。

◆ 自适应置信度加权UKF融合，NGPS协方差由RANSAC内点率、重投影误差和匹配置信度联合调制
◆ 速度预测核提取，利用VIO速度预测卫星图像搜索区域，提升匹配效率与鲁棒性
◆ 异步多速率时间优先级队列，将绝对位姿（1-2Hz）、VIO（10-20Hz）和IMU（100-200Hz）按时间顺序交错融合
◆ 基于VINS位姿图全局优化并以NGPS校正锚定，实现实时2.5D地理参考正射影像重建...[摘要不完整，待更新]</td></tr>
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
<tr><td>2026-06-22</td><td>G-MASt3R-SfM: Graph-based View Pruning and Multi-stage Optimization for Robust SfM<br><a href='http://arxiv.org/pdf/2606.22856'>论文</a></td><td>◆论文提出G-MASt3R-SfM，针对MASt3R在非重叠图像对上产生错误匹配、进而影响SfM位姿估计的问题，构建了更鲁棒的SfM流程。
◆其核心创新之一是Graph-based View Pruning模块，利用匹配置信度构建场景图，并结合几何一致性剔除离群视图和不可靠连接。
◆第二个创新是Multi-Stage Optimization模块，通过从局部一致性到全局一致性的逐阶段优化，逐步细化相机参数。
◆该方法避免将错误匹配直接纳入全局优化，从源头上抑制噪声传播，提高了复杂场景下的位姿估计稳定性。
◆在ETH3D数据集上的实验表明，G-MASt3R-SfM在相机位姿估计和三维重建精度上达到当前最优水平。</td></tr>
<tr><td>2026-06-18</td><td>Evaluation of Image Matching for Art Skills Assessment<br><a href='http://arxiv.org/pdf/2606.20199'>论文</a></td><td>◆本文提出一种基于图像匹配的绘画技能评估方法，通过比较手绘作品与原始模板的相似度来量化绘画水平。

◆研究将计算机视觉用于替代传统人工评估，降低了评估过程的复杂性和主观性。

◆论文实现并对比了SIFT特征匹配与孪生网络两类图像相似度方法。

◆实验结果表明，利用图像相似度评估艺术技能是可行的，能够反映绘画与模板之间的差异。

◆关键发现是SIFT关键点匹配在该任务中表现更有效，更适合用于检测和衡量绘画技能。</td></tr>
<tr><td>2026-06-10</td><td>SalArt-VQA: Diagnosing Whether VLMs Understand Salient Artifacts in Generated Images<br><a href='http://arxiv.org/pdf/2606.12671'>论文</a></td><td>这篇论文针对视觉语言模型(VLMs)在AI生成图像伪影检测中的细粒度理解能力进行了诊断性研究。作者指出,尽管VLMs在图像级伪影检测上表现良好,但其判断可能依赖错误的视觉线索或区域,导致正确结论背后隐藏着推理失败。为此,论文构建了SalArt-VQA基准,包含950张图像和3681道人工标注的多项选择题,覆盖伪影图像、真实参考图像和配对生成参考图像,从存在性检测、语义定位、空间定位和证据支撑的缺陷识别四个维度系统评估模型。对20个VLMs的测试揭示,最强模型虽达到99.37%的检测召回率,但仅在53.26%的图像上同时答对四类问题,且模型存在敏感性与校准之间的权衡。

◆ 提出首个面向AI生成图像显著伪影细粒度理解的诊断性基准SalArt-VQA,填补了仅依赖图像级检测准确率所掩盖的评估盲区。
◆ 设计四类对齐问题(存在性检测、语义定位、空间定位、证据支撑的缺陷识别),系统检验VLMs的伪影判断是否建立在局部视觉证据之上。
◆ 引入伪影图像、真实参考图像和配对生成参考图像三类对照划分,可定量评估模型在无伪影场景下的校准能力与拒答行为。
◆ 揭示了VLMs普遍存在的敏感性-校准权衡现象:敏感模型易做出无依据的伪影声明,保守模型则通过漏检来规避误报。
◆ 实验证明高检测准确率并不等同于具备扎实的伪影理解能力,为后续模型改进指明方向。</td></tr>
<tr><td>2026-06-02</td><td>SAMatcher: Co-Visibility Modeling with Segment Anything for Robust Feature Matching<br><a href='http://arxiv.org/pdf/2606.03406'>论文</a></td><td>该论文提出SAMatcher框架，将图像匹配问题转化为共视性建模问题，通过预测跨视图共视区域作为结构化先验来指导匹配。
◆突破传统像素级匹配局限，首次利用共视区域掩码和边界框作为结构化先验进行对应点估计。
◆提出基于SAM的对称跨视图交互机制，实现双向特征交换与跨视图语义对齐。
◆设计统一监督方案，通过掩码学习、框回归及掩码-框一致性约束联合优化掩码预测与框定位。
实验表明该方法在大视角和尺度变化下优势显著，证明了单目分割基础模型可有效扩展至多视图推理，为图像匹配提供了新视角。</td></tr>
<tr><td>2026-05-30</td><td>BEVIO: Efficient Bird&#x27;s-Eye-View based Sparse-Update Visual-Inertial Odometry for Lunar Day-Night Navigation<br><a href='http://arxiv.org/pdf/2606.00709'>论文</a></td><td>本文针对月球漫游车计算资源受限及昼夜自带光源下特征关联困难的挑战，提出了基于鸟瞰图的稀疏更新视觉惯性里程计BEVIO。
◆提出基于鸟瞰图的图像匹配方案，有效增强了对更大帧间运动的鲁棒性。
◆在显著视觉外观变化下实现了更可靠的特征匹配，克服了夜间自带光源照明的干扰。
◆支持在极稀疏视觉更新率下进行可靠的里程计估计，大幅降低了对计算资源和功耗的依赖。
通过高保真月球仿真和半比例漫游车在真实环境中的长期昼夜部署实验，验证了该方法在低至0.25赫兹更新频率下仍能实现可靠的昼夜导航。</td></tr>
<tr><td>2026-07-01</td><td>SOCO: Benchmarking Semantic Object Correspondence in Vision Foundation Models<br><a href='http://arxiv.org/pdf/2605.31597'>论文</a></td><td>本文提出SOCO基准，旨在解决视觉基础模型中结构化对象理解评估协议不一致和部件级监督有限的问题。
◆构建了包含对应类型分类法的语义对象对应基准，在100个类别和超百万对应对上提供一致且具功能意义的关键点标注。
◆引入关键点语言描述，支持对大型视觉语言模型细粒度部件级理解能力的系统评估。
◆揭示视觉骨干网络虽编码强语义结构，但跨类别迁移对应能力差且仅部分捕获部件位置。
◆发现大视觉语言模型擅长文本提示定位但视觉参考跨图匹配较弱，暴露语言接地与视觉对应间的鸿沟。
◆证明对应性能比ImageNet分类性能更能强有力地预测分割、跟踪及3D检测等密集下游任务的表现。</td></tr>
<tr><td>2026-05-22</td><td>MASt3R-Nav: WayPixel Navigation in Relative 3D Maps<br><a href='http://arxiv.org/pdf/2605.24111'>论文</a></td><td>本文提出了一种基于像素相对连通性的新型地图表示方法MASt3R-Nav，实现了无需全局几何一致性的高精度几何导航。
◆提出像素相对连通性地图表示，既保留了局部几何准确性，又避免了传统3D地图对全局几何一致性的依赖。
◆通过图像对相对3D坐标系中的像素对应关系构建图像间连通性，从而从图像序列生成地图。
◆通过对图像内像素连通性进行近似和稀疏化，实现了基于像素级图的全局路径规划。
◆推导出路点像素代价图表示，并训练以此为条件的控制器来预测轨迹。
实验证明，基于相对几何的密集像素级代价图比图像或对象级条件变量更准确，在多种任务中显著提升了导航能力。</td></tr>
<tr><td>2026-05-11</td><td>3DReflecNet: A Large-Scale Dataset for 3D Reconstruction of Reflective, Transparent, and Low-Texture Objects<br><a href='http://arxiv.org/pdf/2605.10204'>论文</a></td><td>◆ Accurate 3D reconstruction of objects with reflective, transparent, or low-texture surfaces still remains notoriously challenging.
◆ Such materials often violate key assumptions in multi-view reconstruction pipelines, such as photometric consistency and the availability on distinct geometric texture cues.
◆ Existing datasets primarily focus on diffuse, textured objects, and therefore provide limited insight into performance under real-world material complexities.</td></tr>
<tr><td>2026-05-06</td><td>Creative Robot Tool Use by Counterfactual Reasoning<br><a href='http://arxiv.org/pdf/2605.05411'>论文</a></td><td>◆ We propose a causal reasoning framework for creative robot tool use where a suitable tool for a task is correctly identified for use beyond its primary objectives.
◆ The proposed framework first discovers the causal relationships between the tool and the task by conducting simulated experiments in a dynamics model.
◆ We decouple the causal discovery problem into two complementary components: VLM-based feature suggestion and counterfactual tool generation via targeted geometric and physical feature perturbations.</td></tr>
<tr><td>2026-05-02</td><td>SIFT-VTON: Geometric Correspondence Supervision on Cross-Attention for Virtual Try-On<br><a href='http://arxiv.org/pdf/2605.01296'>论文</a> | <a href='https://github.com/takesukeDS/SIFT-VTON'>代码</a></td><td>◆ Diffusion-based virtual try-on methods achieve photorealistic synthesis through cross-attention mechanisms that transfer garment features to target body regions.
◆ However, these approaches rely on implicit learning of spatial correspondences, struggling to preserve fine details such as text and illustrations.
◆ We propose a novel approach, which we call SIFT-VTON, that utilizes SIFT keypoint matching to provide explicit geometric guidance for diffusion-based virtual try-on.</td></tr>
<tr><td>2026-05-29</td><td>MAPRPose: Mask-Aware Proposal and Amodal Refinement for Multi-Object 6D Pose Estimation<br><a href='http://arxiv.org/pdf/2604.20650'>论文</a></td><td>本文针对杂乱场景中严重遮挡和噪声导致的6D姿态估计难题，提出了MAPRPose两阶段框架。
◆在姿态提案阶段，将2D对应关系提升至3D空间建立可靠关键点匹配，基于对应级评分生成几何一致的姿态假设选出Top-K候选。
◆在细化阶段引入AMPR模块，通过重建完整物体几何与动态调整ROI，有效缓解重度遮挡下的定位误差和空间错位。
◆设计GPU加速的RGB-XYZ重投影机制，在张量化渲染比较管线中实现单次前向传播同步细化所有姿态假设。
该方法在BOP基准上取得76.5%的最优平均召回率，精度超越FoundationPose 3.1%，且多目标推理速度提升43倍。</td></tr>
<tr><td>2026-05-01</td><td>Are Pretrained Image Matchers Good Enough for SAR-Optical Satellite Registration?<br><a href='http://arxiv.org/pdf/2604.10217'>论文</a></td><td>◆ Cross-modal optical-SAR (Synthetic Aperture Radar) registration is a bottleneck for disaster-response via remote sensing, yet modern image matchers are developed and benchmarked almost exclusively on natural-image domains.
◆ We evaluate twenty-four pretrained matcher families--in a zero-shot setting with no fine-tuning or domain adaptation on satellite or SAR data--on SpaceNet9 and two additional cross-modal benchmarks under a deterministic protocol with tiled large-image inference, robust geometric filtering, and tie-point-grounded metrics.
◆ Our results reveal asymmetric transfer--matchers with explicit cross-modal training do not uniformly outperform those without it.</td></tr>
</tbody>
</table>
</div>

<h2 id='obstacle-avoidance'>Obstacle Avoidance</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-21</td><td>STL-GCS: A Planner-Controller Framework for Signal Temporal Logic via Graphs of Time-varying Convex Sets<br><a href='http://arxiv.org/pdf/2607.19196'>论文</a></td><td>本文提出STL-GCS，一种针对信号时序逻辑（STL）规范定义在凸谓词上的统一轨迹规划与控制框架。该方法将STL任务编码为配置空间中的时变凸集，并提升到时间-配置联合空间，与图凸集（GCS）框架相结合，形成基于凸时空集合的最短路径规划问题。轨迹采用B样条参数化，从而能够在连续时间上强制执行STL满足、避障以及平滑性约束。在控制层，复用规划阶段的时变集合设计反馈控制器，使系统在存在跟踪误差和模型失配时仍能优先保证STL规范的满足。该方法在仿真以及空间机器人真实平台上均得到了实验验证。

◆创新点：将STL规范编码为时变凸集，通过前向不变性保证规范满足并具备规定的鲁棒裕度。
◆创新点：在时间-配置联合空间中利用GCS框架构建凸集图上的最短路径规划问题。
◆创新点：采用B样条参数化轨迹，实现STL约束、避障与平滑性的连续时间统一处理。
◆创新点：控制层与规划层共享时变集合结构，使反馈跟踪在扰动下优先保障STL满足。</td></tr>
<tr><td>2026-07-21</td><td>End-to-end Conditional Diffusion for Realistic and Controllable Visual Traffic Scenario Generation<br><a href='http://arxiv.org/pdf/2607.18637'>论文</a></td><td>本文针对自动驾驶闭环测试中交通场景生成面临的真实性与可控性难以兼顾的问题,提出了端到端条件扩散框架E2E-CDiff。该方法以前视视觉观测为条件,联合去噪未来运动状态与可执行的低层控制信号,实现统一的状态-动作生成,有效缓解了传统&quot;轨迹预测+控制器&quot;两阶段流水线中存在的规划-控制不匹配问题。通过引入可微分引导机制,模型能够灵活调节车速、约束可行驶区域,并支持避撞或主动碰撞等多种行为模式,从而同时支持自然驾驶与安全关键场景的生成。

◆ 首次提出端到端条件扩散框架,以前视图像为条件联合去噪车辆未来运动状态与可执行低层控制,实现统一的状态-动作生成,消除两阶段方法中的规划-控制不匹配。

◆ 设计可微分引导机制,支持速度调节、可行驶区域约束以及避撞/碰撞趋向等多模式行为控制,实现自然场景与安全关键场景的统一生成。

◆ 在Bench2Drive基准上实现可控性与真实性的良好平衡,其碰撞引导变体可有效生成对多种自动驾驶系统具有挑战性的交互场景。

◆ 框架同时具备作为学习型自车规划器的竞争力,验证了端到端状态-动作扩散范式在不同任务中的通用性。</td></tr>
<tr><td>2026-07-20</td><td>GeoWorldAD: Geometry World Action Model for Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.17521'>论文</a></td><td>本文提出GeoWorldAD，一种基于几何世界模型的自动驾驶动作决策方法，旨在解决现有视觉/视频-动作模型缺乏显式3D几何约束和未来感知空间引导的问题。

◆核心创新在于将轨迹规划锚定于以自车坐标系对齐的3D空间，利用显式几何信息提供安全规划所需的空间约束。

◆方法通过潜在未来几何token预测短时域场景演化，使模型能够预判周围智能体和自车可用空间的未来变化，从而在避免过度保守决策的同时保障安全性。

◆设计了渐进式多尺度几何聚合与迭代轨迹精修机制，高效融合当前几何与潜在未来几何信息。

◆在NAVSIM v1和v2基准上取得最优性能，验证了显式3D几何建模与未来世界建模对安全高效自动驾驶的有效性。</td></tr>
<tr><td>2026-07-19</td><td>An Update to the Level Set Theorems in Hamilton-Jacobi Reachability Analysis<br><a href='http://arxiv.org/pdf/2607.17435'>论文</a></td><td>本文针对Hamilton-Jacobi可达性分析（HJR）中的水平集定理进行了重要的技术更新。HJR是处理不确定性下安全关键系统控制的重要框架，其理论基础源于Hamilton-Jacobi偏微分方程所求解的值函数。水平集定理能够将值函数与定性目标（如目标到达或避障）的满足性进行关联解释，是控制器综合的关键工具。本文的核心贡献在于揭示并补充了原有水平集定理成立所需的额外条件，完善了相关理论体系。◆明确了原有水平集定理在应用中被忽略或缺失的附加判定准则，使定理的适用条件更加严格完整。◆通过补充这些技术条件，提升了HJR框架在目标到达和避障问题中的理论可靠性，为相关安全控制器的设计提供了更坚实的数学基础。</td></tr>
<tr><td>2026-07-19</td><td>From Perception to Assistance: Open-Vocabulary Shared Autonomy for Robotic Manipulation<br><a href='http://arxiv.org/pdf/2607.17323'>论文</a></td><td>本文针对工业遥操作机械臂在杂乱场景中精度不足、深度感知受限且易碰撞的问题，提出了一种基于共享自治的辅助操作框架，通过单台RGB-D相机无穿戴式地捕捉操作者臂部动作与手势，并以自由文本提示指定目标。

◆ 利用视觉-语言模型在腕部相机中完成开放词汇目标定位，并由可提示视频分割模型在各机载相机间持续跟踪，从而将抓取姿态与障碍物地图持续分离。

◆ 采用GPU加速模型预测控制器结合在线体素重建，强制执行自碰撞与环境避障，并通过势场在接近阶段将操作者参考轨迹修正至目标。

◆ 操作者可通过手势触发自主模式，在同一感知管线内完成目标抓取，无需切换独立模块。

该框架在四足移动机械臂上完成工业阀门操作与抓放任务，消融实验表明碰撞与辅助模块缺一不可，自主执行在两项任务中各五次试验成功四次。</td></tr>
<tr><td>2026-07-18</td><td>ADMM-Based Safety-Critical Distributed NMPC for Cooperative Transportation by Quadrupedal Robots<br><a href='http://arxiv.org/pdf/2607.17007'>论文</a></td><td>本文...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-18</td><td>How to Build Marcus&#x27;s Algebraic Mind: From Minsky&#x27;s Emotion-Machine Viewpoint<br><a href='http://arxiv.org/pdf/2607.16623'>论文</a></td><td>本文从Minsky《情感机器》的视角重新解读VaCoAl架构,为其代数心智提供纵向的&quot;反思维度&quot;,与同伴论文中横向的表征框架形成正交互补。

◆核心创新一:将VaCoAl的精确可逆性与Minsky反思层(Reflective Layer)直接对接,主张精确的结构表征保留与恢复机制是内省的神经基础,反射性解绑自身审议痕迹即为该层操作。

◆核心创新二:按痕迹忠实度将审议划分为三层——概率型(LLMs)、近似代数型、精确代数型(VaCoAl),唯独精确可逆性保证反思性恢复忠实无伪。

◆核心创新三:在同一基底上承载Minsky另外两个思想——泛类比通过内容可寻址检索实现(匹配精度即类比契合度,支持终身学习),以及信用赋值被重新框定为反思性反事实模拟,即手术式解绑过往选择并重新绑定反事实以做对比。

文章强调该基底既能攀爬Pearl因果阶梯,又能攀升Minsky内省栈,找到二者交汇点,同时严格区分已演示的痕迹执行与理论性反思论证,将元控制环路留作未来工作。</td></tr>
<tr><td>2026-07-17</td><td>A Task-Space Receding Horizon Controller for Fast Collision Avoidance<br><a href='http://arxiv.org/pdf/2607.15733'>论文</a></td><td>本文针对机械臂实时避障问题，提出了一种任务空间滚动时域控制器，旨在兼顾快速反应与前瞻规划。核心思路是采用短视域接触一致性展开（contact-consistent rollout）生成满足内部无穿透约束的终端运动学参考，再仅计算平滑最小加速度过渡的首次输入，从而避免完整约束轨迹优化的计算负担。控制器基于闭环逆运动学调节律，结合迭代动力学求解器在膨胀凸几何上运行，使机器人-障碍物接触、动态障碍运动及自碰撞都能影响终端参考。

◆ 提出任务空间滚动时域框架，仅计算首步控制输入而非完整轨迹，在保证前瞻性的同时大幅降低在线计算成本。
◆ 在展开阶段引入接触一致性机制与膨胀凸几何，使动态障碍、接触约束和自碰撞共同塑造终端参考，无需完整优化。
◆ 给出理论分析：非接触闭环在标准正则性假设下实现局部指数级任务空间调节，并对接触激活的离散更新及移动障碍对正则运行集的影响给出上界。
◆ 在40自由度多链系统仿真和6自由度硬件实验中验证了仿真到实际的一致性，且在动态杂乱场景下成功率优于动态优化织物和MPC基线，同时保持实时可执行的求解时间。</td></tr>
<tr><td>2026-07-17</td><td>RAVEN: Reinforcement-Adaptive Visibility-Graph Planning for Robust Humanoid Navigation with Collision-Free MPC<br><a href='http://arxiv.org/pdf/2607.15701'>论文</a></td><td>RAVEN提出了一种用于人形机器人在动态环境中导航的分层强化学习与模型预测控制（RL-MPC）框架，旨在解决传统可视化图规划依赖人工调参、难以应对控制延迟与跟踪误差的难题。
◆核心创新在于利用强化学习自适应调整可视化图规划器的几何构造，通过修改障碍物膨胀等图参数直接重塑自由空间几何，从而改变全局路径拓扑结构以补偿系统延迟和跟踪偏差。
◆结合无碰撞MPC层跟踪规划轨迹，显式施加速度边界和避障约束，在保留长期几何规划可解释性的同时保证短期安全约束。
◆训练过程中引入真实控制延迟和观测噪声，使学到的规划策略具备应对实际系统不确定性的能力。
对比手工调参基线和纯RL导航策略的实验表明，RAVEN在障碍物附近显著减少超调，在狭窄通道中鲁棒性更强，且在延迟与噪声条件下导航更加可靠，验证了强化学习自适应图构造与约束MPC相结合的方案相较于端到端学习的优越性。</td></tr>
<tr><td>2026-07-16</td><td>Learning Agile Navigation in Crowded Environments for Quadruped Robots<br><a href='http://arxiv.org/pdf/2607.15036'>论文</a></td><td>针对四足机器人在动态拥挤环境中导航的难题,本文提出VOP-Nav系统,融合速度障碍法的几何安全性与端到端学习的敏捷适应性。该系统仅依赖局部激光雷达观测,避免显式障碍物检测与跟踪流程,有效应对传感器遮挡问题。

◆创新点一:设计VOP-Net网络处理多帧LiDAR数据,隐式编码动态约束并预测基于速度障碍理论的安全速度区域,无需显式运动估计。

◆创新点二:将VO预测结果同时作为推理时的导航策略输入和训练时的奖励信号,实现双重作用,引导策略学习安全运动。

◆创新点三:在Isaac Gym仿真中取得高于所有基线方法的成功率,同时兼顾运动速度与避障能力。

◆创新点四:在Unitree Go2四足机器人上的真实部署验证了系统在复杂室内外动态环境中的鲁棒性与高效性。</td></tr>
<tr><td>2026-07-16</td><td>CosFly-VLA: A Spatially Aware Vision-Language-Action Model for UAV Tracking<br><a href='http://arxiv.org/pdf/2607.15004'>论文</a></td><td>该论文针对无人机在复杂城市环境中跟踪动态目标时面临的遮挡问题，提出了一种空间感知的视觉-语言-动作模型CosFly-VLA。该模型通过结构化预测接口联合实现目标定位、可见性估计和连续飞行动作生成，在目标被遮挡时仍能保持鲁棒的跟踪能力。

论文设计了一套大规模训练流程，包括在50万混合数据上进行空间基础继续预训练以注入深度、距离和三维空间推理能力，随后通过三阶段课程监督微调和思维链训练强化遮挡恢复推理能力，最后采用多组件奖励的强化学习阶段优化闭环跟踪行为。

◆在架构层面，提出统一的结构化预测接口，将目标定位、可见性估计和连续动作生成融合在单一VLA框架中，使模型能够在遮挡场景下做出空间感知的恢复性决策。

◆在训练策略层面，结合继续预训练、课程学习、思维链推理和强化学习的多阶段训练方法，显著提升模型对长时遮挡的鲁棒性和空间推理能力。

◆在实验效果层面，相比OpenVLA基线，CosFly-VLA-0.8B在开环和闭环评估中均取得显著提升，验证了从可见帧模仿到空间基础动作闭环控制的进展。</td></tr>
<tr><td>2026-07-16</td><td>Modeling and Validation of Quality of Control for Edge-Offloaded Collaborative Navigation<br><a href='http://arxiv.org/pdf/2607.14853'>论文</a></td><td>本文针对复杂环境下协作控制面临的无线时延随机性和可靠性变化问题，将原有的控制质量（QoC）框架扩展到实际机器人模型中，研究边缘卸载协作导航场景下的端到端网络效应对闭环性能的影响。论文系统性地探索了机器人运动控制参数对网络时延-可靠性的作用机制，并基于私有5G测试平台，在不同时延、可靠性和控制配置下进行了实验验证。研究给出了实际机器人系统的最优控制-通信协同设计工作区间，并对比了ROS 2标准QoS策略在真实条件下的QoC表现，发现RELIABLE策略在特定实验设置下比BEST-EFFORT策略的QoC提升51.5%。

◆ 创新点一：将QoC框架从抽象模型扩展到包含动态避障的实际机器人导航系统，实现了端到端网络效应对闭环控制性能的建模。

◆ 创新点二：系统性地分析了机器人运动控制参数与网络时延-可靠性之间的耦合关系，揭示了控制-通信协同设计的最优工作区域。

◆ 创新点三：在私有5G测试平台上进行了多维度实验验证，并定量比较了ROS 2不同QoS策略的实际QoC性能差异。</td></tr>
<tr><td>2026-07-16</td><td>NavCMPO: Critic-Guided MeanFlow Policy Optimization for Adaptive Navigation<br><a href='http://arxiv.org/pdf/2607.14643'>论文</a></td><td>NavCMPO提出了一种两阶段自适应导航框架,旨在解决端到端扩散策略在无地图视觉导航中推理延迟高以及行为克隆性能受限的问题。该方法通过少量步数的MeanFlow轨迹生成显著降低推理时延,并结合基于障碍物点云监督训练的评论家网络进行轨迹细化,在预训练阶段引入障碍物邻近度预测任务以增强视觉表征的避障能力。论文在InternVLA-N1基准上以匹配的训练预算取得了74.7%的平均成功率,较基线提升6.4个百分点,同时将推理延迟从85毫秒降至60毫秒,并在Unitree Go2上验证了良好的仿真到真实迁移效果。

主要创新点如下:

◆ 采用少量步数MeanFlow替代传统多步扩散,大幅降低轨迹生成的推理延迟,实现高效实时导航。

◆ 提出基于评论家梯度的轨迹细化方法CGTR,利用障碍物点云监督训练的评论家网络补偿少步生成带来的避障性能退化。

◆ 设计障碍物邻近度预测预训练任务,引导视觉编码器学习障碍感知的空间表征,提升对环境结构的理解。

◆ 在自适应阶段结合PPO强化学习微调与行为克隆正则化,并同步更新评论家以适应不同机器人本体观测变化,实现跨平台迁移。</td></tr>
<tr><td>2026-07-16</td><td>3D Geometric Tooth Alignment Planning via Deep Reinforcement Learning<br><a href='http://arxiv.org/pdf/2607.14544'>论文</a></td><td>该论文提出了一种基于深度强化学习的3D牙齿正畸对齐规划框架，将牙齿移动序列的规划问题建模为马尔可夫决策过程，以捕捉其顺序决策特性，并融合牙齿间碰撞避免与路径效率等空间约束。方法采用深度确定性策略梯度算法作为基础，并在10K例专家设计的临床正畸方案数据集上进行了验证，实验表明在路径安全性和几何效率方面均优于现有基线方法。

◆ 基于Transformer的智能体：有效建模牙齿之间复杂的空间交互关系，并应对高维状态-动作空间带来的挑战。

◆ 动态掩码机制：每步仅允许稀疏子集的牙齿进行移动，更贴合临床中分阶段、顺序调整的逻辑。

◆ 两阶段课程学习策略：逐步增加任务难度，提升训练稳定性并加速有效路径的发现。</td></tr>
<tr><td>2026-07-15</td><td>Discriminative Barrier Functions for Safe Adversarial Imitation Learning from Observation<br><a href='http://arxiv.org/pdf/2607.13938'>论文</a></td><td>这篇论文针对逆强化学习(IRL)依赖无约束探索导致实际部署不安全的问题,以及控制屏障函数(CBF)需要人工解析设计耗时困难的问题,提出了一种将两者优势结合的安全对抗式模仿学习框架。该方法通过将IRL中的奖励函数候选空间约束为CBFs空间,实现了从无标签专家观测中数据驱动地恢复屏障函数,并在保证安全的前提下支持在线控制与持续经验改进。

◆ 提出将IRL奖励函数候选空间限制为CBFs空间的新框架,首次实现了从无标签专家观测中自动恢复屏障函数
◆ 证明了恢复的屏障函数对专家数据中完全缺失的不安全状态具有鲁棒性
◆ 在仿真导航环境中系统对比了所提方法与标准IRL基线的安全性能,验证了显著改进
◆ 在仿真和真实世界避障任务中,深入分析了基于规划与基于策略的IRL方法之间的权衡

该工作为安全模仿学习从观察提供了一种理论严谨且可数据驱动的新方案,具有实际部署价值。</td></tr>
<tr><td>2026-07-14</td><td>MAMMOTH: A Multi-Modal End-to-End Policy for Off-Road Mobility Robust to Missing Modality<br><a href='http://arxiv.org/pdf/2607.12965'>论文</a></td><td>MAMMOTH是一种面向越野自主导航的端到端统一策略，旨在解决复杂非结构化环境中因光照剧烈变化和传感器退化导致的可靠性问题。该方法通过高效融合RGB、热成像、3D点云和自车速度等多模态观测，显著提升了对极端光照和恶劣地形的适应性。为克服现有方法对完整传感器输入的刚性依赖，模型在训练阶段引入模态随机丢弃机制，使其在推理时能够稳健应对任一模态缺失甚至完全失效的情况。此外，MAMMOTH采用扩散策略联合建模物理可行轨迹与内在可通行性启发式，使规划结果倾向于更安全、平滑的路径。该工作通过包含夜间场景在内的真实机器人实验进行了充分验证，在避障、地形感知规划及模态缺失泛化能力上均表现优异。代码与数据集将公开以促进后续研究。

◆ 提出融合RGB、热成像、3D点云与自车速度的统一端到端越野导航策略，提升对光照剧变和传感器退化的鲁棒性。
◆ 引入模态随机丢弃训练机制，使模型在推理时能稳健应对任意模态缺失或完全失效。
◆ 采用扩散策略联合建模物理可行轨迹与可通行性启发式，倾向于规划更安全平滑的路径。
◆ 支持视觉目标条件导航与无方向探索两种任务模式，并在真实夜间越野环境中完成验证。</td></tr>
<tr><td>2026-07-14</td><td>Globalized Constrained Stein Variational Inference for Diverse Feasible Robot Motion Planning<br><a href='http://arxiv.org/pdf/2607.12732'>论文</a></td><td>该论文针对机器人运动规划中多模态解与严格约束并存的核心难题,提出了一种名为SteinSQP(Stein变分序列二次规划)的新方法,在保证所有粒子满足碰撞避免、关节限制、接触条件及动力学一致性等硬约束的同时,维持解集的多样性,以覆盖多条低代价运动路径。

◆ 提出SteinSQP方法,将约束直接嵌入核空间下的SQP子问题,实现了变分推断与约束优化的统一框架,使粒子群在迭代过程中始终朝向可行且多样的低代价区域演化。

◆ 设计了GPU友好的无矩阵原始-对偶算法求解约束Stein-Newton子问题,支持批量粒子同步更新,显著提升计算效率。

◆ 引入粒子集合层面的全局价值函数,联合权衡目标函数值、约束违背程度与粒子多样性,实现了方法的全局收敛性。

◆ 在五类约束运动规划任务上的实验表明,SteinSQP在迭代次数、粒子可行性及批处理求解时间上均优于一阶约束Stein基线与串行多起点非线性规划方法,验证了其在机器人尺度复杂任务中的有效性与鲁棒性。</td></tr>
<tr><td>2026-07-14</td><td>Improving Autonomous Nano-drones Performance via Automated End-to-End Optimization and Deployment of DNNs<br><a href='http://arxiv.org/pdf/2607.12593'>论文</a></td><td>该论文针对亚10厘米纳米无人机的视觉自主导航任务，提出了一套端到端自动化的CNN部署流程，将PULP-Dronet神经网络从训练、优化到最终在Crazyflie 2.1超低功耗多核SoC上的闭环部署进行了全流程整合。相较于原始手工设计的网络，自动化流程在保持预测精度的同时，将内存占用缩减了2倍，推理速度提升了1.6倍，计算功耗仅占无人机总预算的1.6%以下。论文核心贡献与创新点如下：

◆ 构建了首个覆盖训练、优化到部署的端到端自动化工具链，取代了传统易错且劳动密集型的迭代开发流程。

◆ 提出了针对ULP多核SoC的CNN自动压缩与优化方法，在内存和推理速度上实现双重显著提升。

◆ 实现了卓越的实地飞行性能：障碍物躲避峰值制动速度达1.65 m/s，陌生环境自由飞行速度达1.96 m/s，并能完成90度弯道路径跟踪。

◆ 开源了与Crazyflie 2.1即用兼容的完整软件项目，促进该领域后续研究与新应用的开发。</td></tr>
<tr><td>2026-07-14</td><td>StratMamba: Strategic and Reactive Stream Partitioning for Path-Efficient LiDAR-Based Obstacle Avoidance<br><a href='http://arxiv.org/pdf/2607.12370'>论文</a></td><td>本文提出StratMamba，一种基于双流Mamba的时序建模架构，用于解决机器人在复杂障碍物环境中导航时对长时程依赖的建模问题。其核心思想是借鉴人类认知中的战略与反应分离机制，将记忆系统划分为快速衰减与慢速衰减两条并行流，分别承担不同时间尺度的任务。

◆ 创新点1：提出双流Mamba架构，结合快衰减与慢衰减记忆机制，分别处理高频LiDAR数据用于反应式避障，以及长时程目标信息用于战略性规划。

◆ 创新点2：在IsaacLab、Gazebo仿真及Unitree GO1四足机器人真机部署中验证了方法的有效性，展示了良好的sim-to-real迁移能力。

◆ 创新点3：相比LSTM、Transformer和Vanilla-Mamba等基线，在超时率、导航速度（576中位步数，比Vanilla-Mamba提升5.0%）和路径最优性（0.915）上均达到最优。

◆ 创新点4：双流划分设计使模型在扩展LiDAR感知范围下保持更鲁棒的性能，有效平衡了反应式安全与战略性导航之间的矛盾。</td></tr>
<tr><td>2026-07-13</td><td>More than a Manipulator: Planning Propellant-Free Attitude Maneuvers for Free-Floating Spacecraft<br><a href='http://arxiv.org/pdf/2607.12130'>论文</a></td><td>本论文针对自由漂浮航天器,提出了利用机械臂运动实现无推进剂姿态控制的新方法,突破了传统上将机械臂视为干扰源而非控制执行器的设计范式。研究者将该问题建模为一个带有关节限位和碰撞规避约束的轨迹优化非线性规划问题,并采用内点法求解器进行了高效求解。通过对不同运动学复杂度和质量参数航天器-机械臂系统的仿真,论文展示了复杂的回转(Slew)与消旋(Detumble)机动轨迹,并通过动量与力矩包络与反作用轮阵列的控制能力进行了直接对比,验证了机械臂作为冗余乃至主用姿态控制执行机构的可行性。

本文的核心创新点可总结如下:

◆ 提出将机械臂运动作为无推进剂姿态控制执行机构的全新设计理念,改变其传统&quot;干扰源&quot;角色定位。

◆ 构建了考虑关节限位、碰撞规避等关键约束的轨迹优化框架,实现复杂机动任务的安全规划。

◆ 通过动量与力矩包络对比方法,量化评估了机械臂相对反作用轮阵列的控制权限能力。

◆ 拓展了机械臂在太空组装与制造等任务中的多用途功能,尤其适用于抓取大质量比载荷的场景。</td></tr>
</tbody>
</table>
</div>

<h2 id='navigation'>Navigation</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-21</td><td>Eversion-based robots can enable safe access,steering and endoscopic imaging within the spinal subarachnoid space<br><a href='http://arxiv.org/pdf/2607.19274'>论文</a></td><td>该论文针对脊髓蛛网膜下腔内导航难题，提出一种直径2毫米的柔性外翻生长机器人平台，通过压力驱动的尖端外翻机制实现无摩擦扩展与转向，并集成微型内窥镜进行实时鞘内可视化。

◆采用外翻生长机制，将运动局限于远端尖端，显著减少部署体与组织的相对滑动，从根本上降低界面摩擦和剪切损伤风险。

◆结合计算建模、幻影体实验及完整人体尸体实验进行多层次机械验证，幻影实验中平均交互力较推送式降低65.2%，峰值力降低48%。

◆在人体尸体中实现从标准腰椎入路跨越多个椎体水平150毫米受控延伸，术后解剖未观察到硬脊膜或神经结构宏观损伤。

该研究首次在完整人类脊髓解剖中实现外翻机器人的机械表征与多模态验证，为未来鞘内干预技术奠定了量化和程序基础。</td></tr>
<tr><td>2026-07-21</td><td>NaviAIS: A Scenario-Level Vessel Trajectory Prediction Dataset withVectorized Lane Priors and the NaviLane Forecasting Framework<br><a href='http://arxiv.org/pdf/2607.18887'>论文</a></td><td>针对现有船舶轨迹预测数据集采样不统一、缺乏结构化航道信息的问题，本文提出了NaviAIS标准化场景级数据集与NaviLane预测框架两大贡献。NaviAIS将多船历史与未来轨迹组织在统一时间窗和局部坐标系下，并提供栅格化可航行地图、矢量化航道先验、航道图与结构化地图表示，弥补了公开AIS资源在环境感知与可复现性方面的不足。

◆ 贡献一：NaviAIS数据集，在统一时间窗口与局部坐标系下组织多船轨迹，融合矢量化航道先验与结构化地图，同时支持矢量化航道、多场景覆盖与开放访问。

◆ 贡献二：NaviLane预测框架，采用分层宏动作设计实现由粗到细的多模态轨迹生成。

◆ 提出轨迹-地图联合编码机制，构建统一的场景表征。

◆ 设计离散宏动作码本生成多模态候选轨迹，并结合残差细化模块提升局部几何与动力学一致性。

◆ 引入基于世界模型的后果感知评估器，对候选轨迹按交互风险与环境可行性进行排序。实验证明该框架在单模态与多模态设置下均优于代表性基线，验证了结构化航道先验、分层多模态生成与后果感知评估的有效性。</td></tr>
<tr><td>2026-07-21</td><td>Broken Gates: Re-evaluating Web Bot Defenses in the Age of LLM Agents<br><a href='http://arxiv.org/pdf/2607.18659'>论文</a></td><td>本文针对大语言模型驱动的浏览器智能体对Web安全的威胁，系统评估了现有机器人防御机制的有效性。研究覆盖了7种商业验证码求解服务与6种LLM智能体在hCaptcha、reCaptcha v2/v3及Cloudflare Turnstile上的对抗表现，涉及云端、自托管、AI辅助及浏览器扩展等多种部署形态。

◆ 证明交互式挑战型防御对商业求解服务几乎完全失效，后者以极低成本实现近乎100%的绕过率。

◆ 表明LLM智能体在配备专用求解模块时同样能高效击败各类验证码挑战。

◆ 通过细粒度交互轨迹分析，揭示非交互式防御（如reCaptcha v3）的韧性并不源于行为判别能力。

◆ 发现行为特征几乎相同的两个智能体在非交互式防御下结果截然不同，证实执行环境的真实性才是决定性因素。

◆ 指出当前非交互式防御的安全边界实际位于环境层，对机器人管理系统的设计与评估具有重要启示意义。</td></tr>
<tr><td>2026-07-20</td><td>Learning Adaptive Safety Margins for Visual Navigation<br><a href='http://arxiv.org/pdf/2607.18200'>论文</a></td><td>本文针对室内杂乱环境中固定安全裕度难以兼顾保守与激进这一痛点，提出了一种基于上下文条件的安全评论器，用于对扩散规划器生成的轨迹候选进行自适应排序与可靠筛选。该评论器将安全裕度分解为三个互补目标：包含净空预算惩罚与控制屏障函数残差的安全项、融合平滑度与安全门控绕行比惩罚的效率项，以及将学习预算锚定于实际ESDF净空的距离约束匹配项，从而在抑制绕路的同时避免近边捷径和裕度坍塌。训练阶段先在仿真中利用特权ESDF几何训练评论器，再通过两阶段师生蒸馏迁移为仅依赖RGB-D的感知版选择器。实验在HM3D与MP3D的PointGoal导航及跨数据集场景下取得了最高的成功率和SPL，并零样本部署到Unitree G1人形机器人，无需任务级调参。

◆ 提出上下文条件安全评论器，将自适应净空偏好分解为安全、效率与距离匹配三项耦合目标，缓解固定裕度在保守与激进之间的失衡。
◆ 设计安全门控绕行比惩罚与控制屏障函数残差联动机制，显式抑制近边捷径并防止裕度坍塌。
◆ 采用特权ESDF到纯感知的两阶段师生蒸馏，使评论器在仅输入RGB-D时仍逼近特权几何的评判能力。
◆ 实现从仿真训练到Unitree G1人形机器人真实室内场景的零样本跨平台迁移，无需任务级参数调整。</td></tr>
<tr><td>2026-07-20</td><td>Distilling Global Traversability Priors for Image-based Affordance Prediction in Off-road Environments<br><a href='http://arxiv.org/pdf/2607.17984'>论文</a></td><td>该论文针对非结构化越野环境中自主导航存在的短视问题展开研究。传统基于LiDAR或相机构建的度量地图受限于深度感知范围,导致机器人在长距离任务中只能做出次优的局部决策。为解决这一瓶颈,作者提出直接从第一人称视角图像中提取长距离可通行性前沿,弥补了测距范围之外的信息缺失。

◆ 利用卫星影像为图像/位姿数据集计算全局可行导航路径,以此作为监督信号训练网络,显著减少了对大量人工演示数据的依赖。

◆ 将全局可通行性先验知识蒸馏到基于图像的affordance预测模型中,使机器人能够感知超视距的可通行区域。

◆ 在多个离线基准测试中,所提方法相比现有方法性能提升超过10%,并在真实环境实验中有效减少了人工干预次数。</td></tr>
<tr><td>2026-07-20</td><td>Lifelong Localization in Dynamic Indoor Environments Combining Odometry with Sparse Distance Sampling<br><a href='http://arxiv.org/pdf/2607.17852'>论文</a></td><td>本文针对动态室内环境下的机器人终身定位问题,提出了一种结合里程计与稀疏距离采样的鲁棒定位框架。该方法利用少量距离样本为机器人位置提供鲁棒先验,能够实时解决&quot;机器人绑架&quot;问题,并在长时间运行中与里程计融合以收敛到真实位姿。

◆ 基于真实环境数据建立动态障碍物模型,使定位框架能够适应环境变化,在静态和动态环境下均能保证收敛性。
◆ 通过稀疏距离采样(仅16个样本)实现了与全LiDAR SLAM相当的定位精度,大幅降低传感器成本、存储空间和传输带宽需求,同时保护隐私。
◆ 方法具有理论保证,在环境静态或动态变化已被正确学习时,均可证明收敛到机器人真实位姿。</td></tr>
<tr><td>2026-07-20</td><td>SLAM in Low-Light Environments: Project Report<br><a href='http://arxiv.org/pdf/2607.17699'>论文</a></td><td>本文针对低光照环境下RGB相机的SLAM性能问题，系统评估了六种代表性系统在LaMARia数据集五个不同难度序列上的表现，涵盖特征法、直接法、滤波法和学习法四大范式。实验发现，仅有Kimera-VIO能完整跟踪全部序列，DPVO和DPV-SLAM虽不丢失但绝对误差约100米，而ORB-SLAM3、DSO和OpenVINS在困难或低光序列上普遍失败或发散。

◆首次对六种主流SLAM范式在低光环境下的鲁棒性进行统一基准对比，填补了该场景下评估体系的空白。

◆提出低光稳定跟踪需同时具备惯性融合与全局优化两个条件的结论性判断，为系统设计提供明确指引。

◆揭示纯视觉SLAM在极端光照下的能力边界，指出低光专用学习前端或多传感器互补是未来突破方向。</td></tr>
<tr><td>2026-07-20</td><td>Configuration-Induced Passive Self-Rotation for Perception-Enhanced Autonomous Flight<br><a href='http://arxiv.org/pdf/2607.17646'>论文</a></td><td>该论文针对受限与杂乱环境中自主飞行受限于机载传感器视场有限的问题，提出了一种构型诱导的被动自转三旋翼无人机以增强感知能力。研究首先指出，被动自转虽能扩展扫描视场覆盖，但存在扫描刷新率与飞行性能之间的固有权衡。核心思路是将后臂构型参数作为设计自由度来调节被动自转的工作点，从而在机体层级实现二者平衡。同时，论文构建了融合规划与控制的分层自主框架，保障持续自转条件下的敏捷鲁棒飞行。进一步地，针对航点巡检任务设计了引导点重规划策略以提升任务级覆盖。多场景真实飞行实验验证了该方法在高速轨迹跟踪、抗扰动与杂乱环境自主导航中的有效性。

◆ 利用后臂构型参数调节被动自转工作点，为视场刷新率与飞行性能之间的权衡提供无需额外传感器的机体级调节机制。

◆ 构建融合规划与控制的分层自主框架，支持持续被动自转下的敏捷鲁棒自主飞行。

◆ 引入引导点重规划策略，针对航点巡检任务有效提升任务级感知覆盖质量。</td></tr>
<tr><td>2026-07-19</td><td>DROID-ANCHOR: Odometry-Anchored Recurrent Metric Depth Estimation<br><a href='http://arxiv.org/pdf/2607.17058'>论文</a></td><td>本文提出Metric-DROID，一种端到端的循环神经网络架构，旨在解决单目视觉SLAM系统中长期存在的尺度模糊和尺度漂移问题。核心思路是将本体感知里程计信息作为度量锚点融入DROID-SLAM框架，使视觉重建结果与真实物理尺度对齐，从而实现精确的度量深度估计，为自主机器人导航提供可靠的尺度基准。

◆ LSTM更新算子：将高频里程计序列编码为空间特征图，为迭代优化过程提供持续的度量偏置信号。

◆ 不确定性感知度量后端（BA_odom）：将里程计视为具有学习异方差协方差的几何锚点，通过回归时变度量不确定性Σₒ，自适应平衡视觉重投影残差与度量平移残差，有效抑制轮式滑动和传感器噪声的影响。

◆ 选择性残差微调策略：在保留预训练几何先验的同时实现零样本度量对齐，避免传统微调对原始特征的破坏，提升泛化能力。</td></tr>
<tr><td>2026-07-18</td><td>G2-Nav: Grounded and Guarded Vision-Language Costmaps for Robot Social Navigation<br><a href='http://arxiv.org/pdf/2607.16956'>论文</a></td><td>G2-Nav提出了一种用于机器人社会导航的视觉语言代价地图框架,旨在解决现有VLM端到端方法不可预测以及指令跟随方法无法实现完全自主的问题。该框架将抽象的社会推理转化为可靠且可解释的视觉语言代价地图,让VLM评估可通行区域和社交目标,而非直接做出规划决策。

◆ 将VLM的社会推理结果翻译为视觉语言代价地图,实现语义推理与规划解耦,提升可解释性和可靠性。

◆ 利用VLM对上游追踪进行语义验证,并对开放集感知中的可通行区域与社交主体进行评估,增强真实场景鲁棒性。

◆ 引入高频安全检查机制以应对系统延迟,在轨迹生成前提供安全防护,保障真实世界部署安全。

通过真实环境实验验证,G2-Nav能够在非结构化场景中实现安全、高效且符合社会规范的自主导航,代码将开源。</td></tr>
<tr><td>2026-07-18</td><td>Splat-based 3D Scene Reconstruction with Extreme Motion-blur<br><a href='http://arxiv.org/pdf/2607.16926'>论文</a> | <a href='https://github.com/KAIST-VCLAB/gs-extreme-motion-blur'>代码</a></td><td>本文针对低光环境下由长曝光时间引起的极端运动模糊问题，提出了一种基于高斯溅射的RGB-D三维场景重建方法。该方法将相机位姿估计与图像去模糊统一在高斯溅射框架下，通过光流与ICP对齐连续RGB-D帧，并利用深度信息优化高斯点位置以提升三维几何精度。

◆ 提出基于光流与ICP的RGB-D帧对齐策略，在快速运动和有限视场条件下实现鲁棒的相机位姿估计。

◆ 将高斯溅射与深度输入结合，通过调整高斯点位置优化深度对齐，同时增强场景表示能力。

◆ 建模曝光期间的相机运动轨迹，通过对比输入模糊图像与一系列清晰渲染帧实现图像去模糊。

◆ 构建了一个包含极端运动模糊的RGB-D基准数据集，并发布代码和数据集以推动相关研究。

实验表明该方法在极端运动模糊条件下显著优于现有方法，对机器人、自动导航和增强现实等三维建图应用具有重要价值。</td></tr>
<tr><td>2026-07-18</td><td>A BIM-enabled, Agent-based Discrete-event Simulation Platform for Robotic Studies: A Method based on Graph Theory<br><a href='http://arxiv.org/pdf/2607.16920'>论文</a></td><td>本论文提出了一种基于BIM的智能体离散事件仿真平台,用于室内机器人在设施管理中的知识驱动导航与作业规划。针对现有导航方法(如SLAM和预设路径)仅能提供有限环境感知、无法获取建筑构件几何与语义信息的不足,作者将BIM的几何、语义和操作信息融入机器人决策过程。

室内环境被离散化为网格单元,并映射为图节点,根据与建筑构件的空间关系分类为目标、障碍或常规节点,边权重表示节点间通行代价,从而借助图论算法(如最短路径搜索)实现避障与高效路径规划。仿真结果验证了该图表示在无碰撞导航中的有效性。

同时,论文识别并解决了粗粒度离散化所导致的目标—障碍物栅格重叠问题,通过网格细化提升了空间精度与路径可行性。该平台支持机器人在部署前的虚拟评估,为BIM驱动的设施管理机器人系统奠定了基础。

◆ 构建了BIM与智能体仿真耦合的框架,首次将构件级几何、语义和操作属性整合到机器人导航决策中。
◆ 提出基于图论的室内环境离散化与节点分类方法,通过边权表达通行成本,实现知识驱动的无碰撞路径规划。
◆ 揭示粗粒度网格中目标与障碍物重叠的固有缺陷,采用网格细化策略提升空间精度与路径可行性。
◆ 搭建支持部署前虚拟测试的离散事件仿真平台,为BIM信息驱动的设施管理机器人系统提供研究基础。</td></tr>
<tr><td>2026-07-17</td><td>PRISM: Multimodal Terrain Mapping for Rover Navigation in Unstructured Environments<br><a href='http://arxiv.org/pdf/2607.16366'>论文</a></td><td>PRISM是一个针对非结构化环境中漫游车导航的多模态地形感知与建图系统,旨在通过融合RGB、深度和热成像数据,提升复杂地形下的可通行性判断可靠性。该系统采用自研的定制传感器套件采集对齐的RGB-D-T四模态图像,并基于资源受限的嵌入式计算平台运行,可直接生成驱动自主导航的地形图。

主要创新点如下:

◆ 提出OmniUnet,一种基于视觉Transformer的新型多模态语义地形分割网络,专为RGB-D-T四模态融合而设计。

◆ 构建定制化多模态传感器套件,实现RGB、深度与热成像的时空对齐采集。

◆ 发布两个新标注的多模态地形数据集BASEPROD和LAENTIEC,为相关研究提供基准。

◆ 实现了从感知、建图到GNC导航子系统的端到端集成,并通过真实野外物理实验验证了系统的实用性与鲁棒性。</td></tr>
<tr><td>2026-07-17</td><td>Toward Semantic Communication for Real-time Mobile 3D Reconstruction<br><a href='http://arxiv.org/pdf/2607.16128'>论文</a></td><td>本文针对实时移动三维重建场景，提出了一种面向几何估计的语义通信框架。该工作指出，现有的语义通信方法多针对图像或单视图质量优化，缺乏对几何估计可靠性的显式建模，难以满足实时多视图一致性的严苛需求。为此，作者设计了语义收发器与置信度引导的几何估计联合优化机制，在噪声信道下显著提升了位姿估计精度与三维结构一致性。仿真结果表明，该框架在保持图像质量的同时，相比传统分离信源信道编码和现有语义通信方案具有明显优势。

核心创新点如下：

◆ 提出了首个面向实时移动三维重建任务的语义通信整体框架，弥补了现有SemCom方案在几何一致性保障上的空白。

◆ 设计了同时输出重建图像与逐像素置信度图的语义收发器，将区域可靠性信息显式传递给下游几何估计模块。

◆ 提出了置信度引导的几何估计方法，将置信度融入RANSAC位姿初始化与捆绑调整过程，有效抑制不可靠区域对位姿与重建的负面影响。</td></tr>
<tr><td>2026-07-17</td><td>Embodied Active Learning under Limited Annotation and Navigation Budget for Object Detection<br><a href='http://arxiv.org/pdf/2607.15974'>论文</a> | <a href='https://mkabouri.github.io/embodied-active-learning-od'>代码</a></td><td>本文提出了一种具身主动学习框架，在机器人导航时间和标注预算双重约束下，将目标检测器自适应到未知环境。该方法将批量主动学习思想引入具身场景，每轮使用有限导航预算采集候选样本，再以有限标注预算对最相关图像进行人工标注。

◆ 核心创新在于利用空间一致性识别标签不一致的图像，从而定位检测器的失败案例，无需外部监督即可自动选取最有价值的训练样本。
◆ 方法以最大化模型改进为目标，联合优化机器人导航轨迹选择与图像样本筛选，使主动采集过程直接针对检测器薄弱环节。
◆ 在AI2-THOR仿真器大场景中系统对比了多种主动学习目标，并在真实环境中使用Boston Dynamics Spot机器人配合YOLOv5实时检测器完成了实地验证。
实验结果表明，在相同预算条件下该方法取得了最高的检测准确率，证实了基于空间不一致性的引导策略在具身场景下的有效性和实用性。</td></tr>
<tr><td>2026-07-17</td><td>Beyond Frontiers: Scene-Anomaly Guided Autonomous Exploration<br><a href='http://arxiv.org/pdf/2607.15828'>论文</a></td><td>本文针对未知三维环境自主探索任务，指出传统基于几何启发式的方法仅追求空间覆盖率而忽视重建质量，导致探索路径效率低下且重建精度受限。为此，作者提出了一种新范式：将自主探索重新定义为几何异常最小化问题，并设计实现了SCAGE（SCene Anomaly Guided Exploration）框架。

◆核心创新一：提出场景异常引导的探索新范式，将探索目标从&quot;追逐未覆盖体积边界&quot;转变为&quot;主动识别并消除重建质量异常区域&quot;，实现了空间发现与高精度建图的有机统一。

◆核心创新二：让机器人内置对标准室内建筑结构的基础先验知识，实时将采集的原始三维点云与学习到的结构先验进行比对，自动检测墙体碎片、家具残缺等几何不一致区域。

◆核心创新三：利用异常区域作为引导信号，使机器人从最优视角主动前往调查并完善这些结构异常，从而显著提升轨迹效率与三维重建的完整性。

◆核心创新四：框架直接对非结构化三维点云进行操作，无需依赖二维地图或语义标注，具备良好的通用性。

实验结果表明，SCAGE在多个室内场景中均能实现约90%的体积覆盖率，同时在三维重建质量上优于当前最先进方法。</td></tr>
<tr><td>2026-07-17</td><td>Difference-Based Relational Learning for Zero-Shot Object-Goal Visual Navigation With Direct Sim-to-Real Transfer<br><a href='http://arxiv.org/pdf/2607.15642'>论文</a></td><td>针对端到端深度强化学习在零样本目标视觉导航任务中面临的仿真到现实迁移鸿沟问题，特别是物体外观变化与相机视场受限带来的挑战，本文提出了一种时序差分关系网络T-DRN以实现稳健的零样本sim-to-real迁移。

◆ 采用Siamese差分特征提取器，通过计算目标物体与观测物体之间的关联差异生成域无关的特征表征，有效缓解物体外观变化所引起的sim-to-real差距。

◆ 设计双帧时序缓冲区，在窄视场条件下保持短时物体连续性，增强模型对视野受限场景的感知与决策能力。

在AI2-THOR仿真环境中的大量实验表明，T-DRN在零样本泛化成功率方面显著优于多个强基线方法。

进一步在真实轮式机器人平台上开展系统性验证，结果证明T-DRN在真实感知与执行约束下仍保持鲁棒性能，验证了直接sim-to-real迁移的可行性与实用价值。</td></tr>
<tr><td>2026-07-17</td><td>MemoGuard: An Adaptive Runtime for Guarding Against Memory Traps in Communication-Limited Robot Navigation<br><a href='http://arxiv.org/pdf/2607.15589'>论文</a> | <a href='https://github.com/hetheiin/memoguard'>代码</a></td><td>该论文针对通信受限机器人（如灾后巡检、搜救场景）在无法依赖远程算力时，使用情景记忆复用可能引入&quot;高相似但执行无效&quot;动作的安全隐患，提出了MemoGuard自适应运行时系统。其核心思想是在复用记忆前，依据拓扑、资源（电量）和历史结果三类契约对记忆进行校验，仅在校验失败时才调用本地推理兜底，从而在安全性与能耗之间取得平衡。论文在图结构走廊巡检仿真与NVIDIA Jetson AGX Xavier实物平台上均验证了有效性，相比纯相似度复用将电池安全违规降低76.6%，相比始终调用推理将回退次数减少21.4%，单次试验避免3.67秒与36.97焦耳的推理开销。

◆ 首次形式化提出&quot;记忆陷阱&quot;概念，揭示高检索相似度并不保证执行有效性，弥合了相似度匹配与安全决策之间的鸿沟。

◆ 设计基于拓扑、资源、结果三层契约的轻量级校验机制，实现记忆复用的自适应门控，无需额外模型即可拦截危险动作。

◆ 提出安全性与效率的显式权衡框架，仅在契约校验失败时回退到本地大模型推理，显著降低通信受限机器人对算力的依赖。

◆ 在真实边缘硬件上量化验证节能与加速效果，为资源受限场景下的记忆驱动自主决策提供了端到端可复现的工程方案。</td></tr>
<tr><td>2026-07-17</td><td>ImprovedVBGS: Real-time Continual Variational Bayes Gaussian Splatting<br><a href='http://arxiv.org/pdf/2607.15542'>论文</a></td><td>本文针对机器人与自主导航中实时在线重建的需求，提出了ImprovedVBGS加速框架，旨在解决原始VBGS方法因逐帧迭代所有观测点而难以满足严格实时性、内存和延迟要求的瓶颈。该框架通过两项关键创新显著提升了持续变分高斯泼溅的运行效率，同时保持了重建质量。

◆ 采用空间截断的变分推断策略，避免对全场景进行冗余计算，大幅降低单帧变分更新的计算开销。

◆ 改进高斯点的重分配机制，引入前向传播与截断操作，并消除了代价高昂的动态重编译过程。

在NeRF合成数据集上的实验表明，该方法在RTX 3070 Ti上将平均单帧延迟从约84.0秒降至约0.050秒，实现了约1680倍的加速比，同时维持了相当的重建精度。该工作为资源受限平台下的持续三维场景重建提供了一种高效实用的实时解决方案。</td></tr>
<tr><td>2026-07-16</td><td>NavCMPO: Critic-Guided MeanFlow Policy Optimization for Adaptive Navigation<br><a href='http://arxiv.org/pdf/2607.14643'>论文</a></td><td>NavCMPO是一个用于自适应导航的两阶段框架，旨在解决端到端扩散策略推理延迟高以及行为克隆受限于专家示范质量的难题。该方法在预训练阶段通过障碍物距离预测任务学习障碍感知的视觉表征，并结合少步MeanFlow轨迹生成将推理延迟从85ms降至60ms；在自适应阶段采用带行为克隆正则化的PPO进行微调，同时更新评论器以适应不同本体形态的观测变化。

◆ 提出少步MeanFlow轨迹生成机制，显著降低扩散策略的推理延迟。
◆ 设计障碍物距离预测预训练任务，使视觉表征显式编码障碍物空间信息。
◆ 提出评论器引导的轨迹精炼方法CGTR，利用障碍点云监督信号修正中间轨迹，缓解少步生成带来的避障性能下降。
◆ 提出融合行为克隆正则化的PPO微调策略，实现对新形态机器人的高效自适应。
◆ 在InternVLA-N1基准上达到74.7%成功率，并在Unitree Go2上验证了有效的仿真到真机迁移能力。</td></tr>
</tbody>
</table>
</div>

<h2 id='motion-planning'>Motion Planning</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-21</td><td>From Distances to Trajectories: Real-Time Signed Distance Function Mapping and Distance-Accelerated Motion Planning for UAVs<br><a href='http://arxiv.org/pdf/2607.19306'>论文</a></td><td>这篇论文针对无人机在杂乱环境中的自主飞行问题,提出将建图与运动规划围绕有符号距离场(SDF)这一统一表征进行协同设计,改变了两者作为独立阶段、依赖占据栅格的传统思路。

◆ 在建图方面,提出Octree REsidual Network(OREN),将显式八叉树先验与隐式神经残差相结合,既能利用体素方法的高效性,又具备神经方法的精度与可微性,实现了从点云在线重建SDF。

◆ 在规划方面,提出Bubble*搜索算法,利用距离信息生成最大无碰撞气泡,具备终止性、完备性和失败检测的形式化保证,通过气泡图显著减少碰撞检测次数,直接输出安全走廊用于轨迹优化。

◆ 将OREN与Bubble*集成部署在四旋翼上,在未知室内环境实现了实时自主导航。

实验表明OREN将SDF估计精度提升22%,Bubble*在约90米杂乱环境中的规划时间仅需1至3秒,而基线方法最多需要10秒。</td></tr>
<tr><td>2026-07-21</td><td>STL-GCS: A Planner-Controller Framework for Signal Temporal Logic via Graphs of Time-varying Convex Sets<br><a href='http://arxiv.org/pdf/2607.19196'>论文</a></td><td>该论文提出STL-GCS框架,将信号时序逻辑(STL)规划与反馈控制统一在时变凸集表示下。核心思路是将STL任务编码为配置空间中的时变凸集,使系统的前向不变性蕴含规格的鲁棒满足。规划层将时变凸集提升至时间-配置联合空间,结合图凸集(GCS)形成凸时空集合上的最短路径问题,并采用B样条参数化轨迹以在连续时间下强制满足STL、避障与光滑约束。控制层复用同一时变凸集设计反馈控制器,在存在跟踪误差和模型失配的情况下优先保障STL规格满足。该方法在仿真与空间机器人实物平台上均得到了验证。

◆ 将STL任务编码为时变凸集,以前向不变性保证规格的鲁棒满足
◆ 提升到时间-配置联合空间,与GCS结合形成凸时空集上的最短路径规划
◆ 采用B样条参数化实现连续时间STL、避障与平滑的联合约束
◆ 规划与控制共享时变凸集表示,控制层优先维护STL规格满足...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-21</td><td>Pose-Parameterized Motion Planning and CBF-QP Self-Collision Filtering for a Long-Reach Drilling Boom<br><a href='http://arxiv.org/pdf/2607.18855'>论文</a></td><td>本文针对Sandvik SB60长臂钻机的自主运动控制需求，提出了一种融合位姿参数化规划与胶囊型控制屏障函数二次规划(CBF-QP)的自碰撞规避方法。该方法采用固定的任务参数集，可自动生成路径点、绕行轨迹、时间参考和链式运动，无需针对每个目标重新调参。系统采用离线与在线相结合的两阶段架构：离线阶段使用23个杆段到身体区域距离筛选候选路径点，在线阶段在实测状态逆运动学中通过9个胶囊构成的全身模型和14组胶囊对约束来过滤关节速度。

◆ 创新点一：将位姿参数化规划与胶囊型CBF-QP相结合，应用于长臂钻机的自主运动控制与自碰撞规避。
◆ 创新点二：采用固定任务参数集生成路径点、绕行和时序参考，免去目标特定的参数重调。
◆ 创新点三：构建九胶囊全身模型，将CBF-QP集成到实测状态逆运动学中实现关节速度的实时安全滤波。
◆ 创新点四：通过23段杆-体距离离线筛选与14组胶囊约束在线过滤的协同设计，实现离线规划与在线执行的闭环防碰撞。
◆ 创新点五：在Simscape Multibody仿真模型上对五目标定向受限与三目标全位姿两种钻孔任务进行大规模验证，实现零IK失败和毫米级位置精度。</td></tr>
<tr><td>2026-07-20</td><td>RoboHarness: Memory-Driven Orchestration of Heterogeneous Robot Policies for Long-Horizon Planning<br><a href='http://arxiv.org/pdf/2607.18060'>论文</a></td><td>针对长时序机器人任务需要多样化能力而单一策略难以可靠完成的问题，论文提出RoboHarness统一框架，将VLA、RL、TAMP等异构机器人控制系统封装为可复用的智能体技能。

◆ 多模态执行记忆机制：通过积累跨策略执行轨迹，动态刻画各策略的能力边界与适用条件，实现能力感知的任务分解与路由。

◆ Memory Bridge策略交接机制：检索下一策略相关执行轨迹，估计其分布内状态区域并引导机器人平稳过渡，避免联合重训练。

◆ 通用兼容性：框架设计兼容导航策略、模型预测控制、世界-动作模型等多种策略类型，具备广泛适用性。

在三个公开基准、500个定制任务和135次真实机器人实验中验证了零样本长时序规划与分布外鲁棒性的显著提升。</td></tr>
<tr><td>2026-07-20</td><td>Manifold-Guided Motion Planning for Tight Assemblies<br><a href='http://arxiv.org/pdf/2607.17898'>论文</a></td><td>本文针对刚体紧密装配运动规划问题，提出了一种基于关键流形引导的采样规划方法CMG-RRT。研究的核心观察是，在紧密装配任务中，可行解路径通常位于或接近&quot;关键流形&quot;——即配置空间中至少存在一个接触点的位姿集合。基于此，CMG-RRT通过层次化细分配置空间，将采样自适应地偏向关键流形的邻域，从而高效探索狭窄通道。

◆ 创新点一：提出&quot;关键流形&quot;概念，将紧密装配问题中的可行路径结构化表征，揭示了接触构型在解空间中的核心地位。
◆ 创新点二：设计层次细分采样偏置机制，使RRT在近乎零间隙的困难区域能够保持有效探索。
◆ 创新点三：在标准间隙假设下证明算法具有概率完备性。
◆ 创新点四：在多个旋转装配基准测试中实现100%成功率，并首次全自动求解Elk解缠绕难题。</td></tr>
<tr><td>2026-07-20</td><td>Task-Space Constrained Stochastic Trajectory Optimization for Time-Optimal Forestry Crane Motion Planning<br><a href='http://arxiv.org/pdf/2607.17818'>论文</a></td><td>本文针对自主林业起重机在液压泵流量约束下的高效避障时间最优运动规划问题，对现有的基于路径点的随机轨迹优化算法(VP-STO)进行了关键扩展。该方法的核心思想是将严格的末端关节空间约束替换为任务空间约束，从而联合优化轨迹与冗余自由度的末端构型。具体创新点如下：

◆将固定末端关节构型约束松弛为任务空间约束，使规划器能够自适应调整末端构型以适应环境相关的运动与液压流量分配。

◆通过构型空间分解对方法进行形式化描述，并针对林业起重机运动学推导出具体的可达性约束。

◆实现了轨迹与冗余自由度末端构型的联合优化，显著提升了泵流量的均衡利用。

实验结果表明，该方法在多个规划目标和路径点配置下平均缩短轨迹时长12-15%，并改善了泵流量利用效率。该方法已通过完整的原木装载循环在真实林业起重机上完成了实际部署验证，证明了其工程实用性。</td></tr>
<tr><td>2026-07-20</td><td>Finite-Time Curvature-Constrained Vector Field for Saturation-Free Motion Planning of Nonholonomic Robots<br><a href='http://arxiv.org/pdf/2607.17542'>论文</a></td><td>本文针对非完整移动机器人运动规划中曲率约束与执行器饱和难以兼顾的难题，提出了一种结合有限时间曲率受限向量场（FT-C2VF）与无饱和控制律的统一框架。该框架可根据任务目标实现有限时间收敛至目标位姿或周期穿越目标位姿。

◆FT-C2VF通过互补增益设计，使积分曲线曲率连续、有界且随径向比单调递减，从向量场层面天然保证曲率约束，避免了传统方法依赖输入饱和的处理方式。

◆所提控制律几乎全局C1光滑，无需雅可比信息即可跟踪FT-C2VF，并在理论层面确保控制输入始终在执行器限幅之内，实现真正意义上的无饱和跟踪。

◆借助动力系统分析证明了目标平衡点的几乎全局有限时间稳定性，弥补了现有向量场方法仅能保证渐近收敛的不足。

仿真与户外阿克曼转向车辆实验均验证了所提方法在跟踪精度、收敛速度及曲率平滑性方面优于代表性向量场方法，具有良好的工程实用性。</td></tr>
<tr><td>2026-07-20</td><td>GeoWorldAD: Geometry World Action Model for Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.17521'>论文</a></td><td>本文提出GeoWorldAD，一种基于几何世界模型的自动驾驶动作决策框架，旨在解决现有视觉/视频动作模型缺乏显式几何约束和未来感知的问题。核心思路是将轨迹规划建立在以自车为中心的3D空间几何基础上，并利用潜在的未来几何令牌预测短时域场景演化，从而在安全避障与驾驶效率之间取得更好平衡。

◆在以自车坐标系对齐的3D空间中进行轨迹规划，引入显式几何约束提升安全性。

◆设计潜在未来几何令牌机制，预测周围交通参与者和自由空间的演化趋势，避免决策过于保守。

◆提出渐进式多尺度几何聚合与迭代轨迹精炼策略，高效融合当前与未来几何信息。

◆在NAVSIM v1和v2基准上取得最优性能，验证了显式3D几何建模和未来世界建模对自动驾驶安全与效率的有效性。</td></tr>
<tr><td>2026-07-20</td><td>Disturbance-Aware Flight for Aerial Robots in Narrow Space<br><a href='http://arxiv.org/pdf/2607.17476'>论文</a></td><td>针对四旋翼飞行器在狭窄空间内飞行面临的强气动扰动和空间受限问题，本文提出扰动感知规划与控制框架（DAPCF），将在线扰动估计融入规划与控制闭环。该框架依次通过双回路观测器实时估计扰动、利用扰动风险函数自适应调节参考速度，并通过基于电机动力学的非线性模型预测控制器实现扰动补偿下的鲁棒轨迹跟踪。

◆双回路观测器基于里程计和电机转速实时估计六自由度扰动力与力矩。
◆扰动风险函数根据扰动估计自适应调节规划器参考速度，扰动大时主动降速，扰动小时恢复速度。
◆基于电机动力学的非线性模型预测控制器（MDNMPC）集成扰动补偿，显著提升扰动下的轨迹跟踪鲁棒性。

实验表明，对角线长度仅0.39米的四旋翼可成功穿越宽度仅0.6米的直线、倾斜与弯曲隧道，在成功率和飞行效率上均超越人类飞行员。</td></tr>
<tr><td>2026-07-19</td><td>Planning for Mission Efficiency, Robustness, and Resilience for Unmanned Autonomous Systems (UASs) in Contested Environments<br><a href='http://arxiv.org/pdf/2607.17085'>论文</a></td><td>本文针对无人机集群在对抗性环境下的路径规划问题，研究了任务效率、鲁棒性和恢复力的综合优化。传统路径规划多关注效率指标，而本文创新性地将鲁棒性（抵御中断能力）和恢复力（中断后恢复能力）显式纳入规划框架。针对异构威胁环境下的区域覆盖任务，提出了允许无人机在航点位置重叠以及动态任务自适应调整的策略。

◆ 在路径规划中引入鲁棒性与恢复力维度，弥补了现有研究仅关注效率的不足

◆ 提出航点重叠分配机制，使多架无人机能够协同覆盖关键区域，增强抗干扰能力

◆ 设计动态任务自适应策略，使系统在中断后能够实时调整路径以恢复任务执行

◆ 在异构威胁场景下系统比较了效率型、鲁棒型、恢复力型三种策略的成败概率

实验结果表明，鲁棒型策略显著优于纯效率型策略，而恢复力型策略在三者中表现最佳，为未来无人机任务规划中显式整合鲁棒性与恢复力提供了有前景的研究方向。</td></tr>
<tr><td>2026-07-18</td><td>SAGE: A Socially-Aware Generative Engine for Heterogeneous Multi-Agent Navigation<br><a href='http://arxiv.org/pdf/2607.16619'>论文</a></td><td>该论文提出SAGE，一种面向异构多智能体导航的社会感知生成引擎，旨在解决开放人机环境中不同动力学与角色参与者之间的安全合规导航难题。SAGE将机器人与周围实体表示为有向异构图，通过异构图变换器编码类型特定的非对称交互，并基于扩散生成模块联合建模实体未来轨迹与机器人规划。核心创新如下：

◆ 构建异构图变换器HGT，显式建模不同类型智能体间的非对称交互关系，区分动力学、自主性与社会角色差异。

◆ 采用基于扩散的生成模块，将多智能体轨迹预测与机器人规划统一在同一框架内联合推理。

◆ 提出免训练的安全-社会能量引导机制，融合碰撞、运动学、任务进度与角色条件社会合规等可微分约束。

◆ 引导机制支持显式调控安全-精度-任务权衡且无需重训，可扩展至最多20台机器人的团队规模。</td></tr>
<tr><td>2026-07-18</td><td>An Indoor Navigation System for the Visually Impaired based on UWB Positioning and D* Lite Path Planning Algorithm<br><a href='http://arxiv.org/pdf/2607.16614'>论文</a></td><td>本文针对视障人士在室内复杂环境中的导航难题，提出了一种基于超宽带（UWB）定位技术与D* Lite路径规划算法相结合的室内导航系统。该系统利用UWB传感器在GPS信号缺失的室内环境中实现高精度定位，解决了传统定位技术精度不足的问题。D* Lite算法的引入使系统能够根据环境变化快速重规划路径，有效应对动态障碍物，显著提升了导航的实时性和灵活性。实验结果表明，该系统运行可靠、延迟低，能够为视障用户在复杂室内空间中的安全通行提供有力保障。

◆ 采用UWB超宽带技术实现室内高精度定位，克服了GPS信号不可用环境下传统定位手段精度受限的问题。

◆ 引入D* Lite增量式路径规划算法，支持动态环境下的快速路径重规划，显著提升对动态障碍物的响应能力。

◆ 将UWB定位与D* Lite算法深度融合，构建了低延迟、高可靠的视障人士室内导航完整解决方案。

◆ 系统设计兼顾安全性与灵活性，验证了在复杂室内场景中辅助视障用户独立通行的实用价值。</td></tr>
<tr><td>2026-07-17</td><td>Differentiable Reinforcement Learning for Path Tracking by an Agile Fish-Like Robot<br><a href='http://arxiv.org/pdf/2607.16508'>论文</a></td><td>本文针对类鱼机器人流体-结构相互作用难以精确建模、非线性欠驱动动力学控制困难的问题，提出了一种基于可微强化学习的路径跟踪方法。研究团队首先开发了一个计算高效的类鱼机器人运动仿真平台，弥补了现有仿真环境在速度与精度上的不足。在此基础上，方法将PID控制与可微强化学习相结合，通过时间反向传播和课程学习策略训练PID的可变增益，实现了运动控制与路径跟踪的端到端优化。最终，该方法成功实现了从仿真到真实物理平台的策略迁移，实验结果与仿真表现出良好的一致性，验证了所提方法的有效性和实用性。

◆ 开发了适用于类鱼机器人的高效近似仿真平台，解决了流体-结构相互作用难以精确建模且计算开销大的难题。
◆ 将传统PID控制与可微强化学习相结合，通过时间反向传播端到端优化PID可变增益，兼具经典控制的稳定性与学习的适应性。
◆ 采用课程学习策略对控制策略进行训练，提高了训练的收敛速度与最终性能。
◆ 实现了仿真到真实平台的无缝策略迁移，物理实验与仿真结果高度吻合，证明了方法的实用价值。</td></tr>
<tr><td>2026-07-17</td><td>When to Plan: Learning to Select Between Reactive Control and Deliberative Planning<br><a href='http://arxiv.org/pdf/2607.16421'>论文</a></td><td>本文研究如何...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-17</td><td>Vessel Trajectory Prediction using COLREGs-aware Optimal Planning<br><a href='http://arxiv.org/pdf/2607.15969'>论文</a></td><td>本文提出了一种基于最优规划的船舶轨迹预测方法，核心思想是将预测问题转化为从每艘周围船舶视角出发的序列轨迹规划任务。该方法分两步执行：首先利用A*搜索在考虑静态障碍物的前提下生成可行的初始轨迹作为热启动，随后通过数值优化器对该轨迹进行精细调整以确保符合国际海上避碰规则（COLREGs）。与基于学习的预测方法相比，本方法仅需输入周围船舶的当前位置、速度以及预期目的地（这些信息均可从AIS消息中直接获取），无需依赖长时段的历史观测数据，因此能够实现更快速的预测响应。论文还基于真实AIS数据构建了多种实际海上场景对所提方法进行了验证。整体而言，该工作将避碰规则显式嵌入到优化规划框架中，兼顾了物理可行性与规则合规性。

◆ 创新点一：采用A*搜索与数值优化相结合的两阶段框架，先快速生成避开静态障碍的初始轨迹，再通过优化保证COLREGs合规。
◆ 创新点二：将轨迹预测重新建模为从每艘周围船舶视角出发的序列规划问题，使多船交互场景下的预测更加合理。
◆ 创新点三：仅依赖AIS消息中的当前位置、速度与目的地信息即可完成预测，无需长时历史数据，显著提升预测速度。
◆ 创新点四：在真实AIS数据构建的实际场景上对方法进行了实证验证，增强了方法的实用性与可信度。</td></tr>
<tr><td>2026-07-16</td><td>Stigmergic Graph Memory: An Environment-Aware Approach for Many-to-Many Multi-Agent Pickup and Delivery<br><a href='http://arxiv.org/pdf/2607.15182'>论文</a></td><td>本文针对自动化履约仓库中多对多多智能体取送货（MAPD）问题，提出了一种基于环境感知的方法Stigmergic Graph Memory（SGM）。现有图引导方法主要在目标确定后影响路径规划，而请求的端点选择缺乏对近期交通状况的感知。SGM作为一层有界的衰减记忆层，在仓库节点和有向边上记录近期执行信号，用于对可行端点和路径偏好进行排序，同时不改变碰撞约束或规划器的有效性。

◆提出在规划器外部维护一个有界、衰减的记忆层，将环境反馈编码为节点和边上的执行信号，使记忆随时间自然淡化并控制资源占用。
◆将记忆机制与碰撞规划解耦，仅在端点选择和路径偏好排序阶段利用记忆，不破坏原规划器的可行性与完备性。
◆在五种仓库布局、三种负载、每种条件下25个随机种子的全面实验中，在全部15种地图-负载组合上均优于重构的多对多分配基线，配对吞吐量提升达20.5%至36.7%。

该工作表明近期执行记忆可通过塑形哪些可行目标进入规划器来提升吞吐，而不仅限于优化既定目标间的行进方式。</td></tr>
<tr><td>2026-07-16</td><td>Catch, Throw, Repeat: Planning for Human-Robot Partner Juggling<br><a href='http://arxiv.org/pdf/2607.15129'>论文</a></td><td>本文针对人机动态物体交换这一难题,聚焦于人机协作抛接球任务,提出了一种实时规划与控制架构,使机器人能够与人类伙伴完成多球同步抛接。系统的核心在于将预测性球体追踪、基于多重打靶法的自适应在线轨迹优化以及基于状态机的协调逻辑有机结合,实现了对人类动作不确定性的鲁棒适应。

◆ 基于多重打靶法的自适应在线轨迹优化,能够实时预测并调整机器人的接球与抛球动作,确保在人类运动存在变异性时仍保持同步

◆ 基于状态机的多球协调逻辑,实现了多球级联模式下的任务切换与节奏控制,支持机器人与人类共享三球级联

◆ 集成预测性球体追踪与反馈控制,显著提升了系统在感知、时机和接触交互不确定性下的可靠性

在8名不同水平参与者(从初学者到专家)的用户研究中,所有参与者在10分钟内均超过此前公开报道的最佳成绩,其中一人将共享三球级联接球的连续记录提升5倍至20次,另一人在单球回传任务中实现了40次连续接球的100%成功率,充分验证了该架构在真实人机协作中的有效性。</td></tr>
<tr><td>2026-07-16</td><td>BridgeFlow: Fast and Robust SE(2)-Equivariant Motion Planning with Flow Matching<br><a href='http://arxiv.org/pdf/2607.14725'>论文</a></td><td>BridgeFlow提出了一种快速且严格SE(2)等变的生成式运动规划框架,旨在解决现有学习型规划器在等变性与推理速度之间的两难困境。该方法通过轻量级的任务中心化规范化模块实现精确的空间等变性,无需依赖计算昂贵的专用等变网络,即可使用标准架构完成泛化。

◆ 设计了任务中心化规范化模块(task-centric canonicalization),以轻量化方式实现严格SE(2)等变性,使标准网络架构即可获得空间泛化能力。

◆ 采用布朗桥信息先验与上下文感知小批量最优传输相结合,构建拉直化的向量场,最小化传输成本并稳定训练过程。

◆ 引入无分类器引导(Classifier-Free Guidance)显式嵌入环境感知,提升轨迹生成对复杂环境的适应性。

◆ 在密集2D环境与7自由度Franka机械臂上的实验表明,推理速度提升最高达15倍,有效轨迹率比现有最优扩散基线提高2倍,并能稳健泛化到完全未见过的环境与任意空间变换。</td></tr>
<tr><td>2026-07-16</td><td>DRIFT: Drift and Aggregation for Motion Planning<br><a href='http://arxiv.org/pdf/2607.14507'>论文</a></td><td>DRIFT是一种用于端到端轨迹规划的固定深度规划器，针对多假设行为表达与单一可执行轨迹输出的矛盾问题提出解决方案。论文的核心在于将紧凑轨迹潜在空间中的一步漂移生成与场景感知的提议聚合相结合，实现高效的多假设运动规划。

◆ 一步漂移潜在空间生成：DRIFT解码器基于预训练视觉编码器特征，单次批量生成48个提议特征（32个α=0.5、16个α=0.9），无需迭代采样，实现高效并行推理。

◆ 轻量级聚合头设计：聚合头直接融合提议特征与场景、导航及自车状态信息，无需轨迹级质量标签即可预测最终轨迹，简化训练流程。

◆ 地图边界正则化器：利用可行驶区域多边形对路点施加惩罚，鼓励规划轨迹贴合可行驶边界，提升合规性。

◆ 在NAVSIM navtest基准上达到89.6 PDMS与90.4 EPDMS，提议生成与聚合模块在RTX 4090上仅需10.82毫秒，全模型推理66.43毫秒，验证了多假设规划的高效可行性。</td></tr>
<tr><td>2026-07-17</td><td>Worlds in One Demo: A Synthetic Data Engine for Learning Open-World Mobile Manipulation<br><a href='http://arxiv.org/pdf/2607.13154'>论文</a></td><td>本文针对开放世界移动操作策略学习所需海量数据的问题,提出了WANDA系统,通过单个真实演示即可扩展出大量多样化训练数据,显著降低了数据采集成本。核心思路是先从源RGBD观测中重建高斯泼溅背景和机器人-物体交互轨迹作为世界基底,再通过对接触丰富的交互片段进行空间重排与全身运动规划,链式生成全新轨迹。论文还提出纠正式状态扩展技术增强长时序鲁棒性,并利用日常照片生成多样化3D世界以实现跨环境泛化,最终通过渲染网格与高斯泼溅背景合成实现照片级真实观测。

◆提出基于单个演示的可扩展合成数据引擎WANDA,通过空间重排接触片段和全身运动规划实现轨迹自动扩展
◆设计纠正式状态扩展方法,在不同阶段增加机器人与物体状态多样性以提升长时序鲁棒性
◆利用日常照片生成多样化3D世界背景,实现跨环境场景泛化
◆结合高斯泼溅背景与渲染网格实现照片级真实观测合成
◆天然支持跨形态数据生成,可在形态不同的移动机械臂上零样本部署...[摘要不完整，待更新]</td></tr>
</tbody>
</table>
</div>

<h2 id='sensor-calibration'>Sensor Calibration</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
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
<tr><td>2026-06-30</td><td>Ground Plane-Aided Extrinsic Calibration of Inertial and RGB-D Sensors for Uncrewed Aerial Vehicles<br><a href='http://arxiv.org/pdf/2606.31019'>论文</a></td><td>◆本文提出了一种面向无人机IMU与RGB-D相机的无标靶外参标定方法，避免依赖棋盘格、专用设备和初始参数估计。
◆方法利用深度学习进行地面分割，从RGB-D深度图中提取地面点并估计其法向量。
◆核心创新是将地面法向量与加速度计测得的重力方向相结合，在鲁棒估计框架下求解传感器外参。
◆该方法特别适合无人机在自然环境中的快速部署与在线/离线标定需求。
◆实验表明，其性能优于MATLAB工具箱，并在无需棋盘格目标的情况下接近Kalibr的标定效果。</td></tr>
<tr><td>2026-06-28</td><td>HiReFF: High-Resolution Feedforward Human Reconstruction from Uncalibrated Sparse-View Video<br><a href='http://arxiv.org/pdf/2606.29333'>论文</a> | <a href='https://iridescentjiang.github.io/HiReFF'>代码</a></td><td>◆ HiReFF提出面向未标定稀疏视角视频的前馈式人体重建框架，可从四个相隔90°视角实现2K、360°动态人体视频重建。
◆ 它将任务分解为稀疏视频前景3D Gaussian重建和高效高分辨率合成，避免传统逐场景优化或依赖相机标定。
◆ 提出Scale-synchronized Camera Calibration，在多视角监督中同步尺度，缓解未标定输入带来的尺度歧义。
◆ 提出Gaussian-wise Foreground Masking，通过调制每个Gaussian参数获得更干净的前景重建并抑制背景干扰。
◆ 提出High-resolution Side-tuning，在主干保持0.5K计算量的同时实现低开销2K渲染，并显著优于现有方法。</td></tr>
<tr><td>2026-06-26</td><td>Robotic Arm-Based Spectral Sensing for Strawberry Positioning and Non-Destructive Sweetness Measurement<br><a href='http://arxiv.org/pdf/2606.28555'>论文</a></td><td>◆提出了一套基于机械臂的草莓光谱感知系统，实现草莓检测、定位、接近与无损甜度估计的闭环集成。
◆系统结合YOLOv11s实时检测、RGB-ToF标定和掩膜-深度对齐，提升了果实三维定位的几何一致性。
◆设计了定制化eye-in-hand手眼标定流程，将目标从相机坐标可靠转换到机器人基坐标，支撑稳定操作。
◆采用路点搜索与增量式闭环接近策略，使传感器能够自动到达适合甜度测量的工作距离。
◆实验达到88.10%的端到端成功率，检测成功率95.24%，目标被检测后的接近成功率为100%，验证了系统可行性。
◆论文还指出当前主要瓶颈在复杂深度和反射条件下的有效感测区域提取，并为未来引入学习型策略提供了可扩展基线。</td></tr>
<tr><td>2026-06-26</td><td>Co-Optimization of Analog Kolmogorov-Arnold Networks for Low-Power Function Approximation in Flexible Electronics<br><a href='http://arxiv.org/pdf/2606.27892'>论文</a></td><td>◆提出模拟Kolmogorov-Arnold网络（AKANs），面向柔性电子中的低功耗多变量函数近似，适用于可穿戴与IoT传感端计算。

◆通过硬件-软件协同优化，将电路级非理想误差纳入训练过程，使模型在实际模拟硬件偏差下仍保持较高精度。

◆设计了软件与硬件双层剪枝方法，在减少样条参数和电路资源的同时降低面积与功耗。

◆实验表明，剪枝不仅压缩硬件开销，还能通过正则化效应提升函数近似精度。

◆在多个基准任务上实现最高55%面积节省和50%功耗降低，平均节省近30%，证明AKANs具备通用性和实用价值。</td></tr>
<tr><td>2026-06-24</td><td>Calousel: Extrinsic Calibration of Non-overlapping Multi-camera Systems from Pure Rotation<br><a href='http://arxiv.org/pdf/2606.25646'>论文</a></td><td>◆论文提出Calousel，用纯旋转运动实现非重叠视场多相机外参标定，只需一块静态标定板，降低了传统大靶标或多靶标预先测量的部署成本。
◆其核心思想是让各相机在不同时间依次观测同一标定板，并通过共享几何参考把这些非同步观测统一起来。
◆方法引入潜在转台坐标系，并在SE(3)上构建三维误差的全局优化模型，以联合估计多相机外参。
◆相比常见运动标定方法，该方案缓解了漂移误差、尺度不确定性和运动退化等问题。
◆实验在受控相机架和真实车辆异构相机平台上验证，表明其在非理想旋转条件下仍具备较高精度和现场部署实用性。</td></tr>
<tr><td>2026-06-22</td><td>IOI: Decoupling Kinematics and Physics for Interactive World Models<br><a href='http://arxiv.org/pdf/2606.23296'>论文</a></td><td>◆ IOI提出一种混合式交互世界模型，将解析运动学先验与学习到的物理动态解耦结合，提升控制对齐和视觉物理合理性。
◆ 它由动作序列显式计算正向运动学轨迹，避免纯数据驱动方法常见的时空漂移。
◆ 论文将轨迹渲染为前、侧、顶三视角正交投影，无需外参标定，并通过多视角运动学聚合与注入模块引导视频生成。
◆ 这种设计让生成器专注建模随机物理交互，而确定性运动由运动学先验保证，形成解析仿真与世界模型的协同。
◆ 在RoboTwin和真实平台实验中，IOI实现了SOTA仿真效果、OOD零样本泛化，并可作为可靠策略评估器和合成数据来源。</td></tr>
<tr><td>2026-06-19</td><td>Online Learning of Robust Legged Odometry with Minimal Exteroceptive Supervision<br><a href='http://arxiv.org/pdf/2606.21669'>论文</a></td><td>◆提出一种即插即用的腿式里程计框架，无需显式外感-本体传感器标定，也不依赖平台特定运动学模型。

◆利用成熟外感运动估计管线作为连续弱监督信号，在线训练仅基于本体感知数据的速度神经网络。

◆将学习到的本体速度、可用外感速度与IMU通过Invariant EKF融合，提高状态估计稳定性与一致性。

◆当视觉/激光等外感在退化环境中失效时，系统可自动切换到学习的本体模型，实现鲁棒连续里程计。

◆在不同四足机器人上验证了方法的平台无关性和快速部署能力，展示其在复杂场景下的可靠运动估计效果。</td></tr>
<tr><td>2026-06-18</td><td>Geometry-Preserving in 3D Gaussian Splatting for LiDAR-Camera Extrinsic Calibration<br><a href='http://arxiv.org/pdf/2606.20103'>论文</a></td><td>◆ 论文针对无标靶LiDAR-相机外参标定中跨模态特征不足的问题，利用3D Gaussian Splatting构建可微的几何代理以支持外参优化。
◆ 作者指出现有3DGS方法过度追求图像渲染质量，容易使高斯空间结构偏离真实LiDAR几何，从而影响标定精度。
◆ 提出通过聚合多视角LiDAR观测生成稠密深度监督，增强高斯代理对真实度量几何的保持能力。
◆ 设计了阻断光度梯度更新高斯空间参数的机制，避免视觉重建目标破坏LiDAR几何结构。
◆ 在公开自动驾驶数据集上的实验表明，该方法在无标靶标定精度上稳定优于现有方法。</td></tr>
<tr><td>2026-06-12</td><td>LV-Calib: LiDAR-Camera Extrinsic Calibration with Boundary-Response Modeling<br><a href='http://arxiv.org/pdf/2606.15010'>论文</a></td><td>本文提出了LV-Calib标定框架，利用可打印平面标定板实现了激光雷达与相机的外参估计及激光雷达边界响应标定。
◆提出基于强度与几何约束的迭代精化方法，自动裁剪背景并估计目标平面，显式处理反射率不连续处因光束足迹和混合回波导致的过渡带展宽与失真问题，提取精确的雷达3D特征点。
◆设计了加权重投影一致的外参优化策略，将图像观测保留在重投影域，并利用精化置信度对雷达特征残差进行加权，提升外参标定精度。
◆利用估计的外参和提取的过渡带，通过计算边界重叠样本的俯仰-偏航-距离残差统计量，实现了激光雷达边界响应的标定。
实验验证了该方法具备亚像素级重投影精度与毫米级特征一致性，并有效提升了里程计性能。</td></tr>
<tr><td>2026-06-12</td><td>StereoGeo: an end-to-end stereo camera calibration method<br><a href='http://arxiv.org/pdf/2606.14619'>论文</a> | <a href='https://github.com/meddourimane/StereoGeo-dataset'>代码</a></td><td>本文提出了StereoGeo，一种基于端到端网络的立体相机标定方法。该方法能够同时估计左右相机的焦距与重力方向，以及它们之间的相对外参变换。
◆突破了现有方法依赖标定板或结构化环境的限制，无需多视角设置即可完成双目标定。
◆打破了传统方法仅局限于单目内参或外参估计的不足，实现了双目内外参的联合估计。
◆扩展了GeoCalib算法，将深度神经网络特征提取与可微优化器进行有效整合。
实验证明该方法在内参标定上极具竞争力，在外参估计上更超越了现有限于单目的方法。</td></tr>
<tr><td>2026-06-12</td><td>Fully Distributed Multi-View 3D Tracking in Real-Time<br><a href='http://arxiv.org/pdf/2606.13127'>论文</a></td><td>本文提出MV3DT,一个面向重叠视野多摄像头网络的全分布式实时三维多目标跟踪框架。该方法摒弃传统集中式融合架构,通过点对点协同实现身份传播与遮挡恢复,有效解决了集中式方法在大规模部署时的计算瓶颈问题。在WILDTRACK数据集上达到94.3%的IDF1和93.3%的MOTA,性能与最先进的集中式方法相当,同时在100个摄像头规模下仍能保持30 FPS的实时性能,摄像头间延迟低于10毫秒,通信开销仅为2.2%。此外,该方法无需场景特定训练,仅依赖摄像头标定即可零样本部署于新环境。

核心创新点如下:

◆ 首次提出完全分布式的多视角三维跟踪架构,通过点对点协调机制取代中心节点聚合,从根本上消除了集中式方法的计算瓶颈。

◆ 设计了轻量级模块化流水线,在每个摄像头节点本地执行单目三维感知、分布式多视图关联与协同融合,通过轻量消息传递实现跨节点协作。

◆ 实现卓越的可扩展性,在100摄像头规模下维持30 FPS实时性能,通信开销仅2.2%,显著优于集中式方案。

◆ 采用零样本运行模式,仅依赖摄像头标定信息,无需任何场景特定的训练或学习,可直接部署到新环境。

◆ 在WILDTRACK基准上取得与集中式SOTA方法相竞争的精度,验证了分布式架构在保持高精度的同时具备规模化部署的实用价值。</td></tr>
<tr><td>2026-06-11</td><td>RGB-S: Image-Aligned Tactile Saliency for Robust Dexterous Manipulation<br><a href='http://arxiv.org/pdf/2606.08765'>论文</a></td><td>本文提出RGB-S框架，旨在解决机器人灵巧操作中视觉遮挡下稀疏触觉与密集视觉难以对齐的问题。与隐式学习跨模态对应的方法不同，该框架通过将物理接触显式锚定在图像域中来提升空间推理能力。
◆利用机器人正运动学与相机校准，将触觉传感器位置直接投影到RGB图像平面，实现跨模态空间对齐。
◆渲染受力调制的高斯显著图，有效建模由运动学与校准误差带来的空间不确定性。
◆采用零初始化条件架构整合二维空间锚点，将物理接触先验注入视觉主干网络，同时保留预训练视觉表征。
在严重视觉遮挡的仿真与真实灵巧操作任务评估中，该方法展现出更强的抗遮挡鲁棒性，真实世界实验成功率较最强隐式基线提升了26.7个百分点。</td></tr>
<tr><td>2026-06-07</td><td>Language as a Sensor: Calibrated Spatial Belief Estimation in 3D Scenes from Natural Language<br><a href='http://arxiv.org/pdf/2606.08666'>论文</a></td><td>该论文提出将自然语言作为一种新型传感器，以解决机器人视场外3D空间推理与多传感器融合的难题。
◆提出语言传感器模型LSM，将语言描述及场景图上下文映射为多模态空间分布，通过混合权重编码指代歧义，分量协方差编码空间不确定性。
◆提出概率建图框架VL-Map，将语言预测视为随机观测，并与机载感知在统一的置信度地图中进行深度融合。
实验证明，LSM是唯一能够保持协方差估计处于校准状态的语言预测器。
将LSM融合进VL-Map后，系统对目标物体位置的预测更加准确，真值目标上的概率质量比最强基线高出约70%。</td></tr>
<tr><td>2026-06-06</td><td>Dexterity-BEV: Aligning 3D World and Actions for Generalizable Robot Policies Learning<br><a href='http://arxiv.org/pdf/2606.02274'>论文</a> | <a href='https://hnuzhy.github.io/projects/Dex-BEV'>代码</a></td><td>本文针对端到端操作策略依赖2D输入且缺乏跨机器人和相机的3D空间对齐的局限性，提出了Dexterity-BEV方法。
◆提出对齐顶点图与顶点频谱，利用相机标定和可选深度将2D视觉提升为像素级3D表示，融合了3D感知与2D大模型的泛化优势。
◆提出将操作策略的输入输出对齐至共享坐标系，并创新性地构建鸟瞰图图像，生成对相机位姿变化鲁棒的视角不变表示。
◆开发了全面的数据处理管线以实现大规模对齐，并引入了针对跨多种机器人、人类操作员和数据集轨迹的全新时间对齐方案。
这些贡献共同缓解了输入输出的时空不对齐问题，显著提升了真实世界机器人操作的连贯性与泛化能力。</td></tr>
</tbody>
</table>
</div>

<h2 id='sensor-undistortion'>Sensor Undistortion</h2>

<div class="table-container">
<table>
<thead><tr><th>日期</th><th>标题</th><th>摘要</th></tr></thead>
<tbody>
<tr><td>2026-07-20</td><td>Certified Training for Convolutional Perturbations<br><a href='http://arxiv.org/pdf/2607.18195'>论文</a></td><td>视觉模型在关键应用部署中容易受到运动模糊等卷积扰动的影响，可能导致检测器漏检等安全隐患。现有数据增强和对抗训练方法虽能改善经验鲁棒性，但缺乏形式化安全保证，难以识别和消除隐藏漏洞。本文提出一种新颖的认证训练方法，通过对卷积扰动进行高效编码来训练具有可证明鲁棒性的模型。该方法在CIFAR10数据集上针对合理强度的运动模糊实现了超过80%的鲁棒准确率，同时保持与标准模型相当的常规准确率，显著优于传统的对抗训练方法。

◆ 提出基于卷积扰动高效编码的认证训练框架，为视觉模型提供可证明的鲁棒性保证
◆ 在CIFAR10上对运动模糊扰动取得超过80%的鲁棒准确率，大幅超越对抗训练基线
◆ 在提升鲁棒性的同时不损失标准准确率，实现了鲁棒性与性能的有效平衡...[摘要不完整，待更新]</td></tr>
<tr><td>2026-07-20</td><td>Benchmarking NACTI Species Recognition in Long-Tailed Regimes<br><a href='http://arxiv.org/pdf/2607.18033'>论文</a> | <a href='https://github.com/ZehuaLiuY/Species-Classification'>代码</a></td><td>本文针对北美相机陷阱图像数据集NACTI中存在的严重长尾类别分布不均问题(最大类占据3.7M图像的50%以上),基于PyTorch Wildlife模型系统评估了长尾识别方法在物种识别任务上的表现。

◆ 提出了一套针对NACTI长尾场景的优化配置,通过专用损失函数与长尾敏感正则化策略,在测试集上达到了99.40%的Top-1准确率,刷新了该基准的最优性能。

◆ 首次将长尾物种识别模型在ENA-Detection、Caltech Camera Traps和Missouri Camera Traps三个独立分布外测试集上进行跨域鲁棒性评估,验证了LTR增强模型相比标准交叉熵方法具有显著更强的泛化能力。

◆ 揭示了当前长尾识别方法的局限性,发现其在严重域偏移下对稀有尾部类别仍存在灾难性预测失败,说明表示瓶颈尚未被完全克服。

◆ 公开了所有数据集划分、关键代码及网络权重,为该领域后续研究提供了高可复现性的实验基础。</td></tr>
<tr><td>2026-07-20</td><td>Does Robust VIO Need More Learning? Geometry-Verified Visual Measurements under Distribution Shift<br><a href='http://arxiv.org/pdf/2607.17956'>论文</a></td><td>本文针对分布偏移下视觉惯性里程计(VIO)的鲁棒性问题,提出一种&quot;极简学习&quot;立体VIO框架,主张将学习严格限制在视觉测量生成环节,时序跟踪、几何验证与状态估计仍采用显式建模。

◆ 仅使用SEA-RAFT网络生成稠密立体匹配并预测像素级不确定性,避免对整个管线进行端到端学习,体现&quot;学习越少越鲁棒&quot;的设计哲学。

◆ 在稀疏特征点处采样稠密光流,并通过预测不确定性和对极几何一致性进行双重筛选,过滤不可靠的测量。

◆ 在滑窗立体惯性优化器中加入不确定性加权重投影因子,实现紧耦合的鲁棒状态估计。

◆ 将匹配不确定性通过立体三角化传递至下游,用于各向异性3D高斯建图,提升地图质量。

消融实验表明,单纯依赖学习光流并不充分,真正的性能增益来自学习匹配与几何验证、不确定性加权的协同。该方法在EuRoC、VIODE和4Seasons数据集上,面对运动模糊、动态场景、光照变化及室内到室外的大幅分布偏移,均表现出准确且稳定的估计性能。</td></tr>
<tr><td>2026-07-20</td><td>SLAM in Low-Light Environments: Project Report<br><a href='http://arxiv.org/pdf/2607.17699'>论文</a></td><td>本文是一篇项目报告，系统评估了六种覆盖特征点法、直接法、滤波法和学习法的SLAM系统在低光照环境下的表现。研究基于LaMARia数据集中五个不同难度与光照条件的序列，采用绝对与相对位姿误差以及控制点召回率作为评价指标。实验结果表明，Kimera-VIO是唯一能够完成全部序列跟踪的系统，具有最低的相对位姿误差但因缺少回环闭合导致绝对误差持续累积；DPVO和DPV-SLAM虽不丢失跟踪，但在低光下绝对误差达到约100米；而经典单目系统ORB-SLAM3、DSO以及滤波法OpenVINS在低光照条件下普遍失败或发散。

◆首次在统一基准下系统对比了六种代表性SLAM系统(ORB-SLAM3、DSO、Kimera-VIO、OpenVINS、DPVO、DPV-SLAM)跨越四大范式在低光照场景下的鲁棒性与精度。

◆将低光跟踪性能与系统架构组件显式关联，揭示惯性融合与全局优化是RGB-only SLAM在低光下保持稳定跟踪的两个必要条件。

◆明确指出当前RGB-only方案的局限，并提出未来突破方向：开发针对低光照的学�的前端特征提取模块，或回归多传感器(深度、热成像)融合的解决方案。</td></tr>
<tr><td>2026-07-20</td><td>Luminosity-Adaptive Contrast Enhancement Using CLAHE for Retinal Fundus Images with Quantitative Validation and Comparative Analysis<br><a href='http://arxiv.org/pdf/2607.17691'>论文</a></td><td>该论文针对视网膜眼底图像普遍存在的光照不均、对比度低等问题，提出了一种结合HSV色彩空间亮度校正与CLAHE的两阶段增强流水线，通过仅在V通道上施加对比度受限的自适应直方图均衡来恢复图像结构与细节。实验在公开的DRIVE数据集上以PSNR、SSIM和CNR三项指标进行定量评估，并辅以二值掩膜分割用于高反射血管病变区域的提取与验证。结果显示所提方法在PSNR 29.3 dB、SSIM 0.91和CNR 3.12上均显著优于传统HE和AHE基线方法，且单张图像平均处理时间仅0.14秒，具备临床筛查的实时性潜力。论文还讨论了局限性与未来引入深度学习对比的研究方向。

◆ 创新点一：将HSV色彩空间解耦用于亮度分量校正，再单独对V通道施加CLAHE，避免了RGB直方图操作引起的色偏问题。
◆ 创新点二：在经典CLAHE框架前增加亮度归一化预处理，使对比度增强对非均匀光照具备自适应性。
◆ 创新点三：联合PSNR、SSIM与CNR进行多维度定量验证，并加入二值掩膜对血管高反射区域进行针对性评估，增强结果可解释性。
◆ 创新点四：实验效率达0.14秒/张，兼顾增强质量与临床实时部署需求。</td></tr>
<tr><td>2026-07-18</td><td>Splat-based 3D Scene Reconstruction with Extreme Motion-blur<br><a href='http://arxiv.org/pdf/2607.16926'>论文</a> | <a href='https://github.com/KAIST-VCLAB/gs-extreme-motion-blur'>代码</a></td><td>该论文提出了一种基于高斯溅射的RGB-D三维场景重建方法,专门针对低光环境下因长曝光时间产生的极端运动模糊问题。传统方法如COLMAP因模糊难以准确估计相机位姿,而NeRF和3DGS等方法又依赖精确的轨迹,ICP算法也因深度传感器视野有限和快速运动导致点云重叠不足而失效。论文的核心创新在于将相机位姿估计与图像去模糊统一在高斯溅射框架中,利用3D高斯点和深度信息增强场景表示。

◆ 通过光流和ICP对连续RGB-D帧进行初步对齐,再通过调整高斯点位置优化深度一致性,从而联合精化相机位姿与三维几何。

◆ 在曝光时间内对相机运动进行建模,通过将模糊输入图像与一系列清晰渲染帧进行对比,实现有效的图像去模糊。

◆ 提出了一个包含极端运动模糊的新RGB-D数据集,填补了该领域基准数据的空白。

实验表明该方法在极具挑战性的条件下仍能实现高质量重建,对机器人、自动导航和增强现实等三维建图应用具有重要价值。</td></tr>
<tr><td>2026-07-09</td><td>A Step Forward Towards Trustworthy Risk-Aware Facial Retrieval (RA-FR)<br><a href='http://arxiv.org/pdf/2607.16279'>论文</a> | <a href='https://github.com/MuhammadEmmadSiddiqui/RA-FR'>代码</a></td><td>本文针对无约束监控环境下人脸检索可靠性不足的问题，提出了风险感知人脸检索框架(RA-FR)，突破了传统固定Top-k检索的局限，能够根据用户指定的风险水平α和置信度1-δ自适应生成检索集合，并保证目标对象的纳入。该框架在IMFDB基准上以约10张图像的平均检索规模稳定满足5%的风险目标，为高风险监控场景提供了可审计的解决方案。其核心创新体现在三个方面：◆采用InterLCM与DiffBIR耦合的混合盲脸复原技术，有效降低低分辨率、运动模糊等域偏移带来的偶然不确定性。◆利用自监督DINOv1 ViT-B结合广义几何均值池化(GGeM)提取对复原过程鲁棒的判别性特征表示。◆引入基于Hoeffding不等式的保形预测机制，依据查询不确定性动态校准检索集合规模，实现具有统计保证的可信决策。整体而言，RA-FR将领域专用复原、鲁棒表征学习与可证明的决策规则相统一，显著提升了人脸检索在真实监控场景中的可靠性与可解释性。</td></tr>
<tr><td>2026-07-15</td><td>DriveFace: A Cross-Spectral Through-Glass Face Dataset for On-the-Move Vehicular Border Control<br><a href='http://arxiv.org/pdf/2607.13515'>论文</a></td><td>本文针对跨境边境检查中车载移动场景下人脸识别的数据缺失问题，提出了DriveFace数据集。该数据集采集自车辆通过检查站时的近红外(NIR)视频，并与基于智能手机的预注册人脸数据进行配对，覆盖了运动模糊、光照变化、遮挡及跨光谱注册等真实挑战。基准实验表明，现有最先进模型在该场景下性能明显受限，验证了数据集的必要性。

◆ 构建了首个面向车载移动边境控制的跨玻璃人脸数据集DriveFace，填补了该场景下公开基准的空白。

◆ 数据集融合NIR车辆通行视频与智能手机预注册图像，模拟真实跨光谱注册场景。

◆ 系统性地涵盖了运动模糊、复杂光照、遮挡及跨玻璃成像等实际挑战。

◆ 通过基线评测揭示了现有SOTA模型在真实车载场景下的性能局限，为后续算法研究指明方向。</td></tr>
<tr><td>2026-07-15</td><td>WNOJ-LIO: A White-Noise-on-Jerk Motion-Prior EKF for High-Dynamic LiDAR-IMU Fusion<br><a href='http://arxiv.org/pdf/2607.13405'>论文</a> | <a href='https://github.com/LvJohny/wnoj-ekf-lio.git'>代码</a></td><td>本文针对高动态场景下LiDAR-IMU里程计面临的扫描内运动畸变与IMU振动噪声耦合问题，提出了基于白噪声加速度先验（WNOJ）的扩展卡尔曼滤波融合框架WNOJ-LIO。该方法在R^3×SO(3)上采用解耦的WNOJ过程模型进行状态预测，并将IMU视为高频测量源而非状态传播驱动，从而避免惯性噪声直接污染去畸变结果和点云配准。

◆在平移和旋转空间上分别建立解耦的WNOJ先验过程模型，实现独立的运动学建模与状态传播。
◆将IMU从传统状态传播驱动角色转变为高频测量源，抑制振动噪声向点云配准环节的传递。
◆推导闭式协方差传播公式，弥合批式WNOJ高斯过程轨迹先验与递归滤波之间的理论鸿沟。

仿真与真实赛车实验（最高速度208 km/h）表明，该方法在去畸变、加速度/角速度去噪及定位精度上均优于FAST-LIO基线。</td></tr>
<tr><td>2026-07-13</td><td>Event-RGB Adaptive Tracking for Nighttime Highway Perception<br><a href='http://arxiv.org/pdf/2607.11646'>论文</a> | <a href='https://github.com/haidongwang96/SEHN'>代码</a></td><td>本文针对高速公路夜间场景下传统RGB相机感知性能退化问题，提出了一种新的多模态融合跟踪方案。其核心思想是打破现有方法中僵化的传感器优先级策略，将异步事件流与RGB帧统一到联合数据关联优化框架中。系统利用自适应扩展卡尔曼滤波，通过NIS统计量在线估计测量噪声，动态调节两种模态的融合权重，使事件流在暗光或高速运动下发挥主导作用，而RGB帧在明亮或静态条件下提供互补信息。此外，作者还基于CARLA仿真器构建了大规模合成数据集SEHN，涵盖白天、无路灯夜间、有路灯夜间等多种环境与交通密度，填补了事件相机高速公路感知领域公开数据集的空白。实验表明该方法在低光照、高速等挑战性场景下显著优于单一模态基线。整体工作为夜间智能交通感知提供了从算法到数据的基础支撑。

◆ 提出JEAT联合事件-RGB自适应跟踪框架，统一异步融合与数据关联，避免硬编码优先级。
◆ 设计基于NIS统计的自适应扩展卡尔曼滤波，动态估计噪声并自适应加权多模态测量。
◆ 发布大规模合成数据集SEHN，覆盖多样化光照与交通条件，弥补事件式高速公路数据集的空白。</td></tr>
<tr><td>2026-07-13</td><td>Diffusion MRI preprocessing affects ADC estimation and automatic PI-RADS v2.1 classification in bi-parametric prostate MRI<br><a href='http://arxiv.org/pdf/2607.11385'>论文</a></td><td>本文系统研究了扩散加权成像(DWI)预处理策略对前列腺MRI中表观扩散系数(ADC)估计和自动PI-RADS分类的影响。研究基于fastMRI前列腺队列的268例数据,依次应用去噪、吉布斯环形伪影校正和微分同胚配准进行磁敏感畸变校正,比较了线性最小二乘(LLS)和迭代加权LLS(IWLLS)两种ADC估计方法,并训练3分类DenseNet预测PI-RADS评分。结果显示,不同预处理流程之间ADC值存在统计学显著差异,LLS与IWLLS生成的ADC图数值上等价;多数数据集间ADC值保持高度线性关系(PCC约0.99),而畸变校正因将DWI重新对齐到T2w解剖结构,PCC降至约0.90;完整预处理数据集在高风险PI-RADS类别中取得了最佳的AUROC和灵敏度,且产生最少的高风险类过度自信错误预测,在临床分诊中具有重要价值。

◆ 首次系统比较了去噪、吉布斯校正和畸变校正等DWI预处理步骤对前列腺MRI下游分析的级联影响,揭示畸变校正是改变ADC值和提升分类性能的关键步骤。

◆ 证实LLS与IWLLS在ADC估计上数值等价,为临床和研究中选择计算更简单的LLS方法提供了依据。

◆ 证明完整DWI预处理流程能显著提升DenseNet对高风险PI-RADS类别的自动分类性能,并降低过度自信的假阴性预测,具有临床分诊价值。</td></tr>
<tr><td>2026-07-13</td><td>HandFlow: Fully Generative 4D Hand Recovery with Flow Matching<br><a href='http://arxiv.org/pdf/2607.11221'>论文</a></td><td>该论文提出HandFlow，一个基于流匹配的全生成式框架，用于从单目视频中恢复时序一致的3D手部姿态与形状。现有判别式方法缺乏时序上下文且预测易抖动，时间模型虽能提升一致性但作为确定性回归器在遮挡和运动模糊下表现脆弱，因此作者采用生成式建模范式学习合理手部运动先验。HandFlow通过单次ODE积分对整个时间窗口的MANO参数进行去噪，无需自回归解码，核心采用Flux风格双流Transformer捕获长程依赖，并引入置信度感知的连续掩码机制融合可学习掩码标记以处理噪声或缺失观测。实验表明该方法在DexYCB和HOT3D上达到最先进性能，世界空间姿态误差降低超30%，加速度误差最低，且在单GPU上以47fps重建150帧序列，速度约为此前最快视频方法的12倍。

◆ 提出基于流匹配的全生成式4D手部恢复框架，通过单次ODE积分对整段时序MANO参数去噪。
◆ 设计Flux风格双流Transformer，无需自回归解码即可捕获长程时序依赖。
◆ 提出置信度感知的连续掩码机制，融合可学习掩码标记以鲁棒处理噪声与缺失观测。</td></tr>
<tr><td>2026-07-12</td><td>MRUF: Multi-granularity Routing with Uncertainty-Aware Fusion for Robust Multimodal Sentiment Analysis<br><a href='http://arxiv.org/pdf/2607.10599'>论文</a></td><td>针对多模态情感分析中模态质量差异导致传统融合过度信任不可靠模态的问题，本文提出可靠性感知融合方法MRUF。该方法融合多粒度路由与不确定性校准，对情感相关表征进行子空间级与模态级路由分配。

◆ 利用留一法误差增量作为监督信号，自动估计各话语下模态的相对重要性，实现数据驱动的权重学习。
◆ 预测模态级不确定性并通过逆方差加权精修门控，使高不确定性模态获得更低融合权重，提升融合鲁棒性。
◆ 引入模态不变的对比对齐损失，稳定共享表征空间，增强跨模态语义一致性。

在CMU-MOSI和CMU-MOSEI数据集的对齐与非对齐实验设置中，MRUF均稳定优于强基线模型。机制分析进一步验证了预测不确定性越高的模态在融合时被赋予的权重越低，证实了方法的有效性与可解释性。</td></tr>
<tr><td>2026-07-11</td><td>BOCCHI: A More Realistic and Challenging Benchmark for Local Motion Blur Detection with MSDCT-UNet<br><a href='http://arxiv.org/pdf/2607.10427'>论文</a></td><td>本文针对局部运动模糊检测任务,指出现有基准测试使模型依赖梯度捷径而难以泛化的问题。为此作者提出了两大核心贡献:一方面构建了真实拍摄的BOCCHI基准数据集,其清晰区域与模糊梯度分布存在重叠,有效规避了梯度捷径问题;另一方面设计了MSDCT-UNet网络,采用频域感知的编码-解码结构,通过多尺度离散余弦变换先验提升检测性能。

◆ 构建BOCCHI真实拍摄基准,首次通过清晰区域与模糊梯度分布的重叠设计来消除梯度捷径,使评估更贴近真实应用场景。

◆ 提出MSDCT-UNet,引入多尺度DCT先验与DCT Attention及FiLM模块,在频域层面增强模型对模糊特征的捕获能力。

◆ 验证方法在BOCCHI上取得最优mIoU和边界定位性能,且仅用633张训练图像即在跨数据集迁移中超越其他训练来源,体现了强泛化能力。</td></tr>
<tr><td>2026-07-10</td><td>A Numerically-Robust ROS 2 Port of iG-LIO: Diagnosing and Fixing Toolchain-Induced Failures in Incremental GICP LiDAR-Inertial Odometry<br><a href='http://arxiv.org/pdf/2607.09947'>论文</a> | <a href='https://github.com/Forestry-Robotics-UC/ig_lio/tree/ros2-jazzy'>代码</a></td><td>本文报告了将iG-LIO（一种紧耦合的LiDAR-惯性里程计算法）从ROS 1迁移到ROS 2 Jazzy的开源移植工作，并重点诊断了迁移过程中出现的环境诱导型数值失效问题。研究发现，在保持估计算法完全不变的前提下，编译运行后仍出现NaN发散，其根源在于现代ROS 2工具链的两个问题：一是服务质量(QoS)配置不匹配导致IMU数据被静默丢弃和重排序，二是oneTBB与Eigen组合中并行归约累加器未初始化。

◆QoS不匹配导致IMU静默丢失与乱序的诊断与修复

◆oneTBB与Eigen并行归约累加器未初始化的根源定位与解决

◆修正Ouster点云字段解析以适配新版本硬件，实现正确去畸变

◆新增Velodyne Velarray M1600传感器支持

◆为Livox提供编译时门控CustomMsg路径与无驱动的PointCloud2标准路径（如Mid-360）

◆通过YAML文件暴露运行时参数配置

该移植结果已在Ouster OS0 Rev7、Ouster OS1 Rev7和Livox MID-360三款硬件上完成实测验证。</td></tr>
<tr><td>2026-07-10</td><td>Event Stream based Multi-Modal Video Anomaly Detection: A Benchmark Dataset and Algorithms<br><a href='http://arxiv.org/pdf/2607.09114'>论文</a></td><td>本文针对传统视频异常检测在光照变化、快速运动和复杂背景下鲁棒性不足的问题，提出了基于事件相机的多模态视频异常检测框架EVAD。该框架联合利用可见光视频和事件流，事件相机以高时间分辨率异步捕捉亮度变化，对运动模糊和极端光照具有天然鲁棒性。论文构建了大规模可见光-事件基准数据集TJUTCM-Pha，包含6.3亿事件和376,368帧视频，涵盖多样化光照、运动模式和背景复杂度，填补了事件异常检测数据集的空白。设计了对比式多模态预训练框架，通过对齐事件流、可见光视频和文本描述的语义嵌入来学习判别性事件表示，并采用自适应融合模块动态整合事件时序线索与视频空间语义。

◆ 构建大规模可见光-事件多模态异常检测基准数据集TJUTCM-Pha，涵盖6.3亿事件与37万余帧视频，填补该领域真实可扩展数据集的空白。
◆ 提出对比式多模态预训练框架，跨模态对齐事件流、视频与文本语义，习得判别性强的事件表示。
◆ 设计自适应融合模块，动态整合事件时序运动线索与视频空间语义特征，显著提升对光照变化等环境干扰的鲁棒性。</td></tr>
<tr><td>2026-07-09</td><td>EVIS: A Physics-Grounded Event Camera Plugin for NVIDIA Isaac Sim<br><a href='http://arxiv.org/pdf/2607.08098'>论文</a> | <a href='https://github.com/spikelab-jhu/isaac-sim-event-camera-plugin'>代码</a></td><td>该论文提出EVIS，一个基于物理的Isaac Sim事件相机插件，可在物理仿真环境中生成高速、完全标注的事件流，以缓解事件相机标注数据稀缺的问题。插件以极小改动从普通RGB相机迁移而来，继承Isaac Sim的物理引擎与帧级真值，输出可直接用于预训练事件网络的下游任务。

◆实现了基于对数强度对比度的事件生成模型，并采用逐像素异步参考更新策略以更贴近真实事件相机行为。

◆提出基于双向运动矢量扭曲的稀疏关键帧插值方法，仅渲染少量关键帧即可合成中间事件帧，实现单GPU实时生成。

◆引入可配置的传感器噪声与运动模糊模型，进一步缩小仿真到真实的差距。</td></tr>
<tr><td>2026-07-07</td><td>Why does Deep Learning Improve Visual SLAM?<br><a href='http://arxiv.org/pdf/2607.06023'>论文</a></td><td>本文针对深度学习视觉SLAM系统性能优越的根本原因进行了系统性探究。研究者通过精心设计的受控实验,分别剥离和组合&quot;学习式二维数据关联&quot;、&quot;不确定性估计&quot;以及&quot;循环神经网络架构&quot;三个关键组件,以揭示各自的贡献。

研究发现,深度学习SLAM系统的成功主要归功于学习式二维数据关联与不确定性建模的协同作用,而非循环架构本身。

◆ 首次以受控消融实验方式,定量分离并评估了学习式数据关联、不确定性估计和循环架构三者对DL-SLAM性能的独立贡献。

◆ 明确指出不确定性建模与数据关联学习是关键驱动因素,挑战了以往将性能提升简单归因于循环结构的普遍认知。

◆ 为未来SLAM系统的设计提供了明确指引,强调应聚焦于发展基于学习的二维数据关联与不确定性估计方法,而非过度依赖循环结构。

◆ 承诺开源代码以促进可复现研究,推动社区对深度学习SLAM内部机理进一步探索。</td></tr>
<tr><td>2026-07-06</td><td>A Reliable Context-Aware and Temporal Planning Framework for Autonomous Driving<br><a href='http://arxiv.org/pdf/2607.04689'>论文</a></td><td>这篇论文提出了RCT-AD框架，旨在解决自动驾驶中因相机观测退化（遮挡、运动模糊、光照变化等）导致规划不稳定、碰撞风险升高的问题。针对现有BEV方法不加区分地融合时序信息的缺陷，该框架显式建模特征质量与时序一致性以提升规划安全性与连贯性。

◆ 提出可靠上下文感知模块，对每帧特征进行可靠性评分，并设计质量门控的FILO记忆机制，选择性保留可信特征。

◆ 利用可靠历史上下文重构退化观测，避免损坏输入干扰共享BEV场景表示的稳定性。

◆ 构建时序轨迹规划器，捕捉长期依赖与多智能体交互，生成更平滑、安全感知的轨迹。

◆ 引入联合检测与分割头，将语义和运动线索注入共享BEV空间，强化场景理解。

在nuScenes基准上的实验表明，RCT-AD在感知精度、运动预测和规划鲁棒性上均优于近期端到端基线，同时保持适合实时部署的计算效率。</td></tr>
<tr><td>2026-07-15</td><td>Your Data Manifold is Secretly a Reward Model: Shell-LCC for Text-to-Video Generation<br><a href='http://arxiv.org/pdf/2606.30248'>论文</a></td><td>◆论文提出“数据流形本身就是奖励模型”的观点，通过显式建模高质量SFT数据的流形结构，为T2V扩散模型提供密集、可微且低成本的奖励信号。
◆方法基于Local Coordinate Coding捕捉数据流形的“骨架”，引导视频潜变量靠近高质量数据分布，从而提升生成真实感。
◆针对传统LCC容易产生均值回归、导致细节丢失的问题，论文提出Shell-LCC，将流形表面建模为各向同性“壳层”，更贴近真实高密度区域。
◆该方法无需额外奖励模型、大规模人工标注或昂贵DPO训练，即可改善视频质量，尤其缓解低层次失真问题。
◆实验表明，Shell-LCC能增强高频细节、减少过平滑伪影，并有效减轻运动模糊，提升文本到视频生成的整体视觉质量。</td></tr>
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
<tr><td><a href='https://github.com/hku-mars/FAST_LIO'>FAST_LIO</a></td><td>4982</td><td>A computationally efficient and robust LiDAR-inert</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO2'>FAST-LIVO2</a></td><td>4399</td><td>FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odo</td></tr>
<tr><td><a href='https://github.com/hku-mars/r3live'>r3live</a></td><td>2431</td><td>A Robust, Real-time, RGB-colored, LiDAR-Inertial-V</td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-LIVO'>FAST-LIVO</a></td><td>1618</td><td>A Fast and Tightly-coupled Sparse-Direct LiDAR-Ine</td></tr>
<tr><td><a href='https://github.com/hku-mars/loam_livox'>loam_livox</a></td><td>1615</td><td>A robust LiDAR Odometry and Mapping (LOAM) package</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR_IMU_Init'>LiDAR_IMU_Init</a></td><td>1454</td><td>[IROS2022] Robust Real-time LiDAR-inertial Initial</td></tr>
<tr><td><a href='https://github.com/hku-mars/Point-LIO'>Point-LIO</a></td><td>1286</td><td>Point-LIO</td></tr>
<tr><td><a href='https://github.com/hku-mars/livox_camera_calib'>livox_camera_calib</a></td><td>1275</td><td>This repository is used for automatic calibration </td></tr>
<tr><td><a href='https://github.com/hku-mars/FAST-Calib'>FAST-Calib</a></td><td>994</td><td>A Handy Extrinsic Calibration Tool for LiDAR-camer</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER'>SUPER</a></td><td>975</td><td>SUPER</td></tr>
<tr><td><a href='https://github.com/hku-mars/BALM'>BALM</a></td><td>925</td><td>An efficient and consistent bundle adjustment for </td></tr>
<tr><td><a href='https://github.com/hku-mars/ikd-Tree'>ikd-Tree</a></td><td>800</td><td>This repository provides implementation of an incr</td></tr>
<tr><td><a href='https://github.com/hku-mars/r2live'>r2live</a></td><td>782</td><td>R2LIVE: A Robust, Real-time, LiDAR-Inertial-Visual</td></tr>
<tr><td><a href='https://github.com/hku-mars/ImMesh'>ImMesh</a></td><td>743</td><td>ImMesh: An Immediate LiDAR Localization and Meshin</td></tr>
<tr><td><a href='https://github.com/hku-mars/STD'>STD</a></td><td>728</td><td>A 3D point cloud descriptor for place recognition</td></tr>
<tr><td><a href='https://github.com/hku-mars/VoxelMap'>VoxelMap</a></td><td>713</td><td>一种高效的概率自适应体素映射方法，用于激光雷达里程计，提升定位精度和效率。</td></tr>
<tr><td><a href='https://github.com/hku-mars/Voxel-SLAM'>Voxel-SLAM</a></td><td>648</td><td>Voxel-SLAM</td></tr>
<tr><td><a href='https://github.com/hku-mars/M-detector'>M-detector</a></td><td>642</td><td>M-detector</td></tr>
<tr><td><a href='https://github.com/hku-mars/mlcc'>mlcc</a></td><td>625</td><td>Fast and Accurate Extrinsic Calibration for Multip</td></tr>
<tr><td><a href='https://github.com/hku-mars/HBA'>HBA</a></td><td>597</td><td>[RAL 2023] A globally consistent LiDAR map optimiz</td></tr>
<tr><td><a href='https://github.com/hku-mars/ROG-Map'>ROG-Map</a></td><td>588</td><td>ROG-Map</td></tr>
<tr><td><a href='https://github.com/hku-mars/IKFoM'>IKFoM</a></td><td>562</td><td>A computationally efficient and convenient toolkit</td></tr>
<tr><td><a href='https://github.com/hku-mars/MARSIM'>MARSIM</a></td><td>551</td><td>MARSIM是一款轻量级、点云逼真的LiDAR无人机模拟器。</td></tr>
<tr><td><a href='https://github.com/hku-mars/GS-SDF'>GS-SDF</a></td><td>518</td><td>[IROS 2025] LiDAR-Augmented Gaussian Splatting and</td></tr>
<tr><td><a href='https://github.com/hku-mars/LTAOM'>LTAOM</a></td><td>501</td><td>LTAOM</td></tr>
<tr><td><a href='https://github.com/hku-mars/Swarm-LIO2'>Swarm-LIO2</a></td><td>446</td><td>[T-RO 24] Swarm-LIO2: Decentralized, Efficient LiD</td></tr>
<tr><td><a href='https://github.com/hku-mars/LIV_handhold_2'>LIV_handhold_2</a></td><td>430</td><td>LIV-Eye: A Low-Cost LiDAR-Inertial-Visual Fusion 3</td></tr>
<tr><td><a href='https://github.com/hku-mars/btc_descriptor'>btc_descriptor</a></td><td>350</td><td>btc_descriptor</td></tr>
<tr><td><a href='https://github.com/hku-mars/D-Map'>D-Map</a></td><td>343</td><td>D-Map provides an efficient occupancy mapping appr</td></tr>
<tr><td><a href='https://github.com/hku-mars/M2Mapping'>M2Mapping</a></td><td>265</td><td>[ICRA 2025] Neural Surface Reconstruction and Rend</td></tr>
<tr><td><a href='https://github.com/hku-mars/UMI-3D'>UMI-3D</a></td><td>259</td><td>UMI-3D SLAM and Data Processing Pipeline: https://</td></tr>
<tr><td><a href='https://github.com/hku-mars/IPC'>IPC</a></td><td>254</td><td>Integrated Planning and Control for Quadrotor Navi</td></tr>
<tr><td><a href='https://github.com/hku-mars/SLAM-HKU-MaRS-LAB'>SLAM-HKU-MaRS-LAB</a></td><td>238</td><td>In this repository, we present our research works </td></tr>
<tr><td><a href='https://github.com/hku-mars/dyn_small_obs_avoidance'>dyn_small_obs_avoidance</a></td><td>223</td><td>dyn_small_obs_avoidance</td></tr>
<tr><td><a href='https://github.com/hku-mars/decentralized_loam'>decentralized_loam</a></td><td>222</td><td>decentralized_loam</td></tr>
<tr><td><a href='https://github.com/hku-mars/SUPER-Hardware'>SUPER-Hardware</a></td><td>207</td><td>SUPER-Hardware</td></tr>
<tr><td><a href='https://github.com/hku-mars/LAMM'>LAMM</a></td><td>203</td><td>LAMM</td></tr>
<tr><td><a href='https://github.com/hku-mars/BDM'>BDM</a></td><td>177</td><td>Memory-Efficient Boundary Map for Large-Scale Occu</td></tr>
<tr><td><a href='https://github.com/hku-mars/PULSAR'>PULSAR</a></td><td>147</td><td>PULSAR</td></tr>
<tr><td><a href='https://github.com/hku-mars/iBTC'>iBTC</a></td><td>142</td><td>iBTC</td></tr>
<tr><td><a href='https://github.com/hku-mars/LiDAR-UAV-Autonomy'>LiDAR-UAV-Autonomy</a></td><td>120</td><td>LiDAR-UAV-Autonomy</td></tr>
</tbody>
</table>
</div>

<h3>ETH-ASL (苏黎世自主系统实验室)</h3>

<div class="table-container">
<table>
<thead><tr><th>项目</th><th>Stars</th><th>简介</th></tr></thead>
<tbody>
<tr><td><a href='https://github.com/ethz-asl/maplab'>maplab</a></td><td>2855</td><td>A Modular and Multi-Modal Mapping Framework</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox'>voxblox</a></td><td>1658</td><td>A library for flexible voxel-based mapping, mainly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis'>okvis</a></td><td>1362</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/segmap'>segmap</a></td><td>1096</td><td>A map representation based on 3D segments </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_align'>lidar_align</a></td><td>1041</td><td>A simple method for finding the extrinsic calibrat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hfnet'>hfnet</a></td><td>871</td><td>From Coarse to Fine: Robust Hierarchical Localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_active_3d_planning'>mav_active_3d_planning</a></td><td>701</td><td>Modular framework for online informative path plan</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_trajectory_generation'>mav_trajectory_generation</a></td><td>662</td><td>Polynomial trajectory generation and optimization,</td></tr>
<tr><td><a href='https://github.com/ethz-asl/polygon_coverage_planning'>polygon_coverage_planning</a></td><td>652</td><td>Coverage planning in general polygons with holes.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aerial_mapper'>aerial_mapper</a></td><td>623</td><td>Real-time Dense Point Cloud, Digital Surface Map (</td></tr>
<tr><td><a href='https://github.com/ethz-asl/dynablox'>dynablox</a></td><td>593</td><td>Real-time detection of diverse dynamic objects in </td></tr>
<tr><td><a href='https://github.com/ethz-asl/robust_point_cloud_registration'>robust_point_cloud_registration</a></td><td>575</td><td>Robust Point Cloud Registration Using Iterative Pr</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_voxblox_planning'>mav_voxblox_planning</a></td><td>570</td><td>MAV planning tools using voxblox as the map repres</td></tr>
<tr><td><a href='https://github.com/ethz-asl/wavemap'>wavemap</a></td><td>566</td><td>Fast, efficient and accurate multi-resolution, mul</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxgraph'>voxgraph</a></td><td>553</td><td>Voxblox-based Pose graph optimization</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hand_eye_calibration'>hand_eye_calibration</a></td><td>519</td><td>Python tools to perform time-synchronization and h</td></tr>
<tr><td><a href='https://github.com/ethz-asl/COIN-LIO'>COIN-LIO</a></td><td>499</td><td>🪙 COIN-LIO: Complementary Intensity-Augmented LiDA</td></tr>
<tr><td><a href='https://github.com/ethz-asl/voxblox-plusplus'>voxblox-plusplus</a></td><td>464</td><td>A volumetric object-level semantic mapping framewo</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_control_rw'>mav_control_rw</a></td><td>451</td><td>Control strategies for rotary wing Micro Aerial Ve</td></tr>
<tr><td><a href='https://github.com/ethz-asl/nbvplanner'>nbvplanner</a></td><td>448</td><td>A real-time capable exploration and inspection pat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/panoptic_mapping'>panoptic_mapping</a></td><td>335</td><td>A flexible submap-based framework towards spatio-t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/vgn'>vgn</a></td><td>314</td><td>Real-time 6 DOF grasp detection in clutter.</td></tr>
<tr><td><a href='https://github.com/ethz-asl/okvis_ros'>okvis_ros</a></td><td>300</td><td>OKVIS: Open Keyframe-based Visual-Inertial SLAM (R</td></tr>
<tr><td><a href='https://github.com/ethz-asl/versavis'>versavis</a></td><td>285</td><td>An Open Versatile Multi-Camera Visual-Inertial Sen</td></tr>
<tr><td><a href='https://github.com/ethz-asl/image_undistort'>image_undistort</a></td><td>279</td><td>A compact package for undistorting images directly</td></tr>
<tr><td><a href='https://github.com/ethz-asl/kitti_to_rosbag'>kitti_to_rosbag</a></td><td>257</td><td>Dataset tools for working with the KITTI dataset r</td></tr>
<tr><td><a href='https://github.com/ethz-asl/laser_slam'>laser_slam</a></td><td>247</td><td>This package provides an end-to-end system to lase</td></tr>
<tr><td><a href='https://github.com/ethz-asl/glocal_exploration'>glocal_exploration</a></td><td>222</td><td>Efficient local and global exploration on submap c</td></tr>
<tr><td><a href='https://github.com/ethz-asl/cblox'>cblox</a></td><td>209</td><td>Voxblox-based submapping</td></tr>
<tr><td><a href='https://github.com/ethz-asl/tsdf-plusplus'>tsdf-plusplus</a></td><td>207</td><td>TSDF++: A Multi-Object Formulation for Dynamic Obj</td></tr>
<tr><td><a href='https://github.com/ethz-asl/aslam_cv2'>aslam_cv2</a></td><td>202</td><td>aslam_cv2</td></tr>
<tr><td><a href='https://github.com/ethz-asl/BIEVR-LIO'>BIEVR-LIO</a></td><td>192</td><td>[RSS 2026] 🦫 BIEVR-LIO: Robust LiDAR-Inertial Odom</td></tr>
<tr><td><a href='https://github.com/ethz-asl/terrain-navigation'>terrain-navigation</a></td><td>186</td><td>Implementation for safe low altitude navigation in</td></tr>
<tr><td><a href='https://github.com/ethz-asl/hierarchical_loc'>hierarchical_loc</a></td><td>185</td><td>Deep image retrieval for efficient 6-DoF localizat</td></tr>
<tr><td><a href='https://github.com/ethz-asl/odom_predictor'>odom_predictor</a></td><td>177</td><td>Integrates an IMU to predict future odometry readi</td></tr>
<tr><td><a href='https://github.com/ethz-asl/orb_slam_2_ros'>orb_slam_2_ros</a></td><td>175</td><td>ROS interface for ORBSLAM2!!</td></tr>
<tr><td><a href='https://github.com/ethz-asl/mav_dji_ros_interface'>mav_dji_ros_interface</a></td><td>169</td><td>Interface of DJI autopilot based on its OSDK (3.2)</td></tr>
<tr><td><a href='https://github.com/ethz-asl/grid_map_geo'>grid_map_geo</a></td><td>168</td><td>Geolocalization for grid map using GDAL. </td></tr>
<tr><td><a href='https://github.com/ethz-asl/lidar_undistortion'>lidar_undistortion</a></td><td>160</td><td>Catkin package that provides lidar motion undistor</td></tr>
<tr><td><a href='https://github.com/ethz-asl/rio'>rio</a></td><td>156</td><td>Graph-based, sparse radar-inertial odometry estima</td></tr>
<tr><td><a href='https://github.com/ethz-asl/depth_segmentation'>depth_segmentation</a></td><td>138</td><td>A collection of segmentation methods working on de</td></tr>
<tr><td><a href='https://github.com/ethz-asl/sl_sensor'>sl_sensor</a></td><td>137</td><td>基于ROS的开源结构光传感器，实现实时高精度测量，适用于建筑机器人领域。</td></tr>
<tr><td><a href='https://github.com/ethz-asl/neuralblox'>neuralblox</a></td><td>132</td><td>Real-time Neural Representation Fusion for Robust </td></tr>
<tr><td><a href='https://github.com/ethz-asl/phaser'>phaser</a></td><td>131</td><td>A robust pointcloud registration pipeline based on</td></tr>
<tr><td><a href='https://github.com/ethz-asl/data-driven-dynamics'>data-driven-dynamics</a></td><td>130</td><td>Data Driven Dynamics Modeling for Aerial Vehicles</td></tr>
<tr><td><a href='https://github.com/ethz-asl/ssc_exploration'>ssc_exploration</a></td><td>111</td><td>Incremental 3D Scene Completion for Safe and Effic</td></tr>
<tr><td><a href='https://github.com/ethz-asl/active_grasp'>active_grasp</a></td><td>109</td><td>Closed-loop next-best view planning for grasp dete</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waypoint_navigator'>waypoint_navigator</a></td><td>108</td><td>Stand-alone waypoint navigator</td></tr>
<tr><td><a href='https://github.com/ethz-asl/waverider'>waverider</a></td><td>107</td><td>RMPs on multi-resolution occupancy maps for effici</td></tr>
<tr><td><a href='https://github.com/ethz-asl/reinmav-gym'>reinmav-gym</a></td><td>106</td><td>Reinforcement Learning framework for MAVs using th</td></tr>
<tr><td><a href='https://github.com/ethz-asl/navrep'>navrep</a></td><td>104</td><td>navrep</td></tr>
<tr><td><a href='https://github.com/ethz-asl/eth_supermegabot'>eth_supermegabot</a></td><td>102</td><td>Instructions for ETH center for robotics summer sc</td></tr>
<tr><td><a href='https://github.com/ethz-asl/unreal_airsim'>unreal_airsim</a></td><td>102</td><td>Simulation interface to Unreal Engine 4 based on t</td></tr>
<tr><td><a href='https://github.com/ethz-asl/3d_vsg'>3d_vsg</a></td><td>100</td><td>3D可变场景图，用于长期语义场景变化预测。</td></tr>
</tbody>
</table>
</div>

---
> 本列表自动生成 | [反馈问题](https://github.com/your-repo/issues)
> 更新于: 2026.07.22

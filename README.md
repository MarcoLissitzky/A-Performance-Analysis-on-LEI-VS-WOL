# A PERFORMANCE ANALYSIS ON LEI VS WOL
### 尝试解释范·尼斯特鲁伊的球队为何在英超迅速失败
### Python | pandas | mplsoccer | networkx ###
<br>
利用 Python 对英超莱斯特城 vs 狼队的比赛事件数据进行量化分析与战术网络拓扑可视化。<br>
TODO：撰写分析。<br>
比赛地址：https://www.whoscored.com/matches/1821238/live/england-premier-league-2024-2025-leicester-wolves

## 数据展示板：
<img width="3365" height="2619" alt="leicester_dashboard" src="https://github.com/user-attachments/assets/7a1c60ff-f924-4ac4-a456-3d6b2c788e9e" />

### 分析 <br>
1.介数中心性最高的节点为Victor Kristiansen，该节点的平均站位位于球场中线之后，靠近边线；
2.介数中心性最高的三个节点平均位置都位于球场中线之后；
3.出度最高的Soumare和Winks的介数中心性只居第二梯队；
4.Khannouss的Cluster Coefficient最高，即该节点周围形成了最多的三角结构；
5.然而，Khannouss的入度位于最后梯队，介数中心性接近0；
6.相对地，Vardy和Buonanotte的Cluster Coefficient接近0，这代表他们几乎孤立于球队进攻；
7.Ayew的该数据也很低；
基本上，球在左路后场运转，既没能形成有效推进，也未形成转移（Kristiansen的站位过于靠近边线，即使未统计传球长度数据，也应当认为其局限于局部安全球传递）。由此，球队的右路被孤立，而球队首发前锋Ayew与首发前腰Vardy站位均偏右，说明球队锋线并未充分参与进攻。

## 马尔可夫热度图：
<img width="1651" height="1369" alt="leicester_transition_heatmap" src="https://github.com/user-attachments/assets/27e7923d-216f-47a4-bde9-e8c82e139736" />

## 期望威胁
<img width="3165" height="1451" alt="leicester_tactical_05_xT" src="https://github.com/user-attachments/assets/4df1d393-651b-410a-8c76-89f53ac535d4" />

<img width="3582" height="2931" alt="leicester_tactical_09_dashboard" src="https://github.com/user-attachments/assets/190c973d-01fe-40cc-8e0a-71929195bc04" />

### 分析 <br>
1.Vardy是球队威胁最大的节点（XT 0.271），但很难接球；
2.即使接球，传球者大概率是Reid，Justin和Vestergaard。这说明球队的中场根本不能将球交给Vardy，要么依赖边路传递，要么依赖后场长传；
3.应该假设，边路传递并不能事实上牵扯防守，Vardy在很多时候面对的是结构化的防线；
4.除Vardy外，其他所有人拿球都很难制造威胁；
5.Buonanotte，Khannouss，Soumare，Winks等中场球员拿球后的威胁相当低，丢失球权率（指球经过该节点的进攻中最终丢失球权而非射门的概率）相当高，特别是Khannouss和Buonanotte；
6.球队的右前场处于瘫痪；
7.反映在象限图中，球队的右路仅有Skipp一个节点为“Core Creator”，尽管他并不擅长；
8.Winks替补Skipp上场后，右路完全瘫痪；
9.仅就进攻而论，Vestergaard的表现不错，用Faes替下前者的换人很可能让球队进攻雪上加霜；
10.球队控球呈现出典型的U型，即后场-边路的大半圆形倒脚，在本场比赛，Leicester明显为无效控球。

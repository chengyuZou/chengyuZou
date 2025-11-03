## About Me 🤺 

<img width="170" src="https://github.com/user-attachments/assets/49cdab2e-7d2e-4c73-a239-037176529e5f" align="right"/> 
 
<p>&emsp;&emsp;大三在校生，对数学竞赛，深度学习，强化学习，大模型感兴趣</p>
<p>&emsp;&emsp;目前正在做: <a href="https://github.com/chengyuZou/NLP-LLM/tree/main/Law" target="GitHub"> 基于Baichuan2-7B的法律微调大模型与RAG 系统</a></p>
<p>&emsp;&emsp;想学点前后端，实现自己的小程序</p>
<p>&emsp;&emsp;我的HuggingFace主页：<a href="https://huggingface.co/erfsdfds" target="HugingFace"> HugingFace </a></p> 
<p>&emsp;&emsp;我的Kaggle主页：<a href="https://www.kaggle.com/zouchengyu" target="Kaggle"> Kaggle </a></p>
<p>&emsp;&emsp;我的LeetCode主页：<a href="https://leetcode.cn/u/zouchengyu/" target="LeetCode"> LeetCode </a></p>
<p>&emsp;&emsp;我的CSDN主页：<a href="https://blog.csdn.net/Du5Ty?type=blog" target="CSDN"> CSDN </a></p>
<p>&emsp;&emsp;樱羽艾玛图片请自取 ➡</p>
  <!-- for beauty 留个空行好看点 -->
<div>&nbsp;</div>

## Want to do

<details close> 
<summary> <b>多模态手语翻译器</b> </summary>
# **多模态手语翻译器：项目构思与技术流程**

这是一个基于多模态大模型的双向手语翻译器项目构思。项目旨在实现手语到自然语言的实时翻译，以及自然语言到手语动作的实时合成。

## **流程一：手语翻译为语言 (手语 \-\> 文本/语音)**

**核心目标：** 将视频中的连续手语动作，翻译成对应的自然语言文本。

### **1\. 数据输入 (Input)**

* 摄像头捕捉到的用户打手语的视频流。

### **2\. 关键点提取 (Feature Extraction)**

这是多模态模型“看懂”手语的第一步。系统需要实时从视频帧中提取关键信息，这通常包括：

* **手部姿态估计 (Hand Pose):** 精确跟踪手指的弯曲、朝向和相对位置。  
* **身体姿态估计 (Body Pose):** 跟踪手臂、肩膀和上半身的动作。  
* **面部表情/口型 (Facial Expression / Mouthing):** 手语中，面部表情（如眉毛、眼神）和特定的口型是语法和语义的重要组成部分。

**技术栈:** 使用像 MediaPipe, OpenPose 这样的计算机视觉（CV）库，或者更先进的专门针对手语优化的姿态估计模型。

### **3\. 序列建模与多模态融合 (Sequence Modeling & Fusion)**

* 手语是一个时序动作。模型需要理解这些关键点随时间变化的**序列**。  
* 将提取到的手部、身体、面部关键点序列数据，以及可能的原始视频特征，融合（Fuse）在一起。

**技术栈:** 使用如 Transformer (尤其是其 Encoder 部分) 或循环神经网络 (RNN) 变体（如 LSTM/GRU）来学习这些时序特征，将其编码成一个“手语含义”的向量表示。

### **4\. 翻译生成 (Translation & Generation)**

* 将编码后的“手语含义”向量输入到一个解码器（Decoder）中。  
* 这个解码器（通常也是 Transformer 架构）会逐字生成目标语言（如中文）的文本序列。

**技术栈:** 这本质上是一个**序列到序列 (Seq2Seq)** 的任务，类似于机器翻译。多模态大模型（LMM）非常适合这个任务，因为它们可以将视觉序列（手语动作）翻译成文本序列（人类语言）。

### **5\. 输出 (Output)**

* 生成翻译后的文本。  
* （可选）将文本传入一个**语音合成 (TTS)** 模块，将其朗读出来。

## **流程二：语言翻译为手语 (文本/语音 \-\> 手语)**

**核心目标：** 将自然语言翻译为3D数字人的逼真手语动作。

### **1\. 数据输入 (Input)**

* 用户的语音或输入的文本。  
* （可选）如果输入是语音，首先需要一个**语音识别 (ASR)** 模块将其转换为文本。

### **2\. 文本到手语“脚本” (Text-to-Gloss/Pose Translation)**

这是翻译的核心。自然语言和手语的语法结构完全不同。

* 模型需要先将自然语言（如“你今天吃饭了吗？”）翻译成手语的“脚本”。这个脚本可以有两种形式：  
  * **手语词序 (Gloss):** 一种中间表示法，大致对应手语的词汇和顺序。  
  * **姿态序列 (Pose Sequence):** 更直接的方式，即直接生成一个代表手语动作的3D骨骼关键点（如BVH文件格式）的时间序列。

### **3\. 3D数字人生成 (Avatar Animation)**

* 获取到第2步生成的姿态序列后，需要一个3D渲染引擎来驱动一个“小人”（3D Avatar）模型。  
* 这个3D模型需要根据姿态序列数据，实时地渲染出流畅、自然的手语动作。  
* **关键点:** 这个模型必须能够**高保真**地渲染**手部细节**和**面部表情**，因为这两者对手语含义至关重要。

### **4\. 输出 (Output)**

* 屏幕上显示的3D数字人，实时打出翻译后的手语。
</details>

## 学习资料
注:排名不分先后顺序

记忆有限,只能想到这么多,后续会逐渐添加

若有侵权,请及时联系我删除
<details close> 
<summary> <b>学习网站</b> </summary>

- [MindMind](https://github.com/jingyaogong/minimind)
- [MiniMind-in-Depth](https://github.com/hans0809/MiniMind-in-Depth)
- [Deepseek-OCR](https://github.com/deepseek-ai/DeepSeek-OCR)
- [GPT-SoVITS](https://github.com/RVC-Boss/GPT-SoVITS)
- [ML-For-Beginners](https://github.com/microsoft/ML-For-Beginners)
- [LLaMA-Factory](https://github.com/hiyouga/LLaMA-Factory)
- [Book-Mathematical-Foundation-of-Reinforcement-Learning](https://github.com/MathFoundationRL/Book-Mathematical-Foundation-of-Reinforcement-Learning)
- [Langchain-Chatchat](https://github.com/chatchat-space/Langchain-Chatchat)
- [DISC-LawLLM](https://github.com/FudanDISC/DISC-LawLLM)
- [DoctorGLM](https://github.com/xionghonglin/DoctorGLM)
- [stanford-cs336-a1](https://github.com/Spectual/stanford-cs336-a1)
- [llm-universe](https://github.com/datawhalechina/llm-universe)
- [llm-cookbook](https://github.com/datawhalechina/llm-cookbook)
- [tiny-universe](https://github.com/datawhalechina/tiny-universe)
- [machine_learning_notebook](https://github.com/583/machine_learning_notebook)
- [Hands-On-Large-Language-Models-CN](https://github.com/bbruceyuan/Hands-On-Large-Language-Models-CN)
- [ZJU-LLMs/Foundations-of-LLMs](https://github.com/ZJU-LLMs/Foundations-of-LLMs)
- [study-progress-of-llm](https://github.com/mikelikeai/study-progress-of-llm)
- [llm-course](https://github.com/mlabonne/llm-course)
- [CS224n-Reading-Notes](https://github.com/LooperXX/CS224n-Reading-Notes)
- [happy-llm](https://github.com/datawhalechina/happy-llm)
- [self-llm](https://github.com/datawhalechina/self-llm)
- [transformers-code](https://github.com/zyds/transformers-code)
- [AI-Resources-Central](https://github.com/CoderSJX/AI-Resources-Central)
- [so-large-lm](https://github.com/datawhalechina/so-large-lm)
- [动手学深度学习2.0](https://zh.d2l.ai/chapter_preface/index.html)
- [ai-app](https://github.com/GuoCoder/ai-app)
- [大模型快速入门学习路径【持续更新】](https://zhuanlan.zhihu.com/p/685915213)
- [GitHub狂飙3万star的LLM公开资料 - 大模型入门教程](https://zhuanlan.zhihu.com/p/686277638)
</details>

<details close> 
<summary> <b>博主</b> </summary>

- Bili [东川路第一可爱猫猫虫](https://space.bilibili.com/675505667?spm_id_from=333.1387.follow.user_card.click)
- Bili [happy魇](https://space.bilibili.com/478929155?spm_id_from=333.1387.follow.user_card.click)
- Bili [偷星九月333](https://space.bilibili.com/349950942?spm_id_from=333.1387.follow.user_card.click)
- Bili [堂吉诃德拉曼查的英豪](https://space.bilibili.com/341376543?spm_id_from=333.1387.follow.user_card.click)
- Bili [你可是处女座啊](https://space.bilibili.com/21060026?spm_id_from=333.1387.follow.user_card.click)
- Bili [chaofa用代码打点酱油](https://space.bilibili.com/12420432?spm_id_from=333.1387.follow.user_card.click)
- CSDN [v_JULY_v](https://blog.csdn.net/v_JULY_v?type=blog)

</details>

<details close> 
<summary> <b>LeetCode</b> </summary>

- [LC-Rating](https://huxulm.github.io/lc-rating/zen)
- [灵茶山艾府](https://leetcode.cn/u/endlesscheng/)
- [codeforces-go](https://github.com/EndlessCheng/codeforces-go/tree/master)
- [Hello算法](https://www.hello-algo.com/)
</details>

## 电子书
等我上传


## Abstract
![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=chengyuZou&theme=dark)
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=chengyuZou&theme=dark)

![](https://stats.justsong.cn/api/leetcode?username=zouchengyu&cn=true&theme=dark)
![GitHub Streak](https://streak-stats.demolab.com/?user=chengyuZou&card_width=450&theme=dark)


<!--
**chengyuZou/chengyuZou** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

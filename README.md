# 常规赛：遥感影像地块分割baseline

## 项目描述
### 赛题介绍
本赛题由 2020 CCF BDCI 遥感影像地块分割 初赛赛题改编而来。遥感影像地块分割, 旨在对遥感影像进行像素级内容解析，对遥感影像中感兴趣的类别进行提取和分类，在城乡规划、防汛救灾等领域具有很高的实用价值，在工业界也受到了广泛关注。现有的遥感影像地块分割数据处理方法局限于特定的场景和特定的数据来源，且精度无法满足需求。因此在实际应用中，仍然大量依赖于人工处理，需要消耗大量的人力、物力、财力。本赛题旨在衡量遥感影像地块分割模型在多个类别（如建筑、道路、林地等）上的效果，利用人工智能技术，对多来源、多场景的异构遥感影像数据进行充分挖掘，打造高效、实用的算法，提高遥感影像的分析提取能力。
赛题任务
本赛题旨在对遥感影像进行像素级内容解析，并对遥感影像中感兴趣的类别进行提取和分类，以衡量遥感影像地块分割模型在多个类别（如建筑、道路、林地等）上的效果。

### 数据说明
本赛题提供了多个地区已脱敏的遥感影像数据，各参赛选手可以基于这些数据构建自己的地块分割模型。

### 训练数据集
样例图片及其标注如下图所示：

![](https://ai-studio-static-online.cdn.bcebos.com/8087a965609d48a19a5e60f0330fa9054d04097644de48ffa3d557e7a8ad64ad)
![](https://ai-studio-static-online.cdn.bcebos.com/d18664ecf0514cb686c95958d30bbf8a2f5efb0691bc4d66a5f6317ab511d6d0)

![](https://ai-studio-static-online.cdn.bcebos.com/e42f2c222f204094ac3a0ea8582ca331b0452fb2b1704eabaae379d499906977)
![](https://ai-studio-static-online.cdn.bcebos.com/d5260bd5a820486a85aeb2105adfb6fa10284bd94453459f892755bc43e10b8a)


训练数据集文件名称：train_and_label.zip

包含2个子文件，分别为：训练数据集（原始图片）文件、训练数据集（标注图片）文件，详细介绍如下：

* **训练数据集**（原始图片）文件名称：img_train

	包含66,653张分辨率为2m/pixel，尺寸为256 * 256的JPG图片，每张图片的名称形如T000123.jpg。
* **训练数据集**（标注图片）文件名称：lab_train

	包含66,653张分辨率为2m/pixel，尺寸为256 * 256的PNG图片，每张图片的名称形如T000123.png。
* **备注**： 全部PNG图片共包括4种分类，像素值分别为0、1、2、3。此外，像素值255为未标注区域，表示对应区域的所属类别并不确定，在评测中也不会考虑这部分区域。

### 测试数据集
测试数据集文件名称：img_test.zip，详细介绍如下：

包含4,609张分辨率为2m/pixel，尺寸为256 * 256的JPG图片，文件名称形如123.jpg。、
### 数据增强工具
PaTTA：由第三方开发者组织AgentMaker维护的Test-Time Augmentation库，可在测试时通过数据增强方式产生额外的推理结果，在此基础上进行投票即可获得更稳定的成绩表现。 https://github.com/AgentMaker/PaTTA

RIFLE：由第三方开发者对ICML 2020中的《RIFLE: Backpropagation in Depth for Deep Transfer Learning through Re-Initializing the Fully-connected LayEr》论文所提供的封装版本，其通过对输出层多次重新初始化来使得深层backbone得到更充分的更新。 https://github.com/GT-ZhangAcer/RIFLE_Module

### 提交内容及格式
* 以zip压缩包形式提交结果文件，文件命名为 result.zip；
* zip压缩包中的图片格式必须为单通道PNG；
* PNG文件数需要与测试数据集中的文件数相同，且zip压缩包文件名需要与测试数据集中的文件名一一对应；
* 单通道PNG图片中的像素值必须介于0~3之间，像素值不能为255。如果存在未标注区域，评测系统会自动忽略对应区域的提交结果。
### 提交示例
提交文件命名为：result.zip，zip文件的组织方式如下所示：

```
主目录                                                                        
├── 1.png         #每个结果文件命名为：测试数据集图片名称+.png                      
├── 2.png                                                              
├── 3.png                                                    
├── ...     
```                                                
    
**备注**： 主目录中必须包含与测试数据集相同数目、名称相对应的单通道PNG图片，且每张单通道PNG图片中的像素值必须介于0~3之间，像素值不能为255。


## 项目结构

### Main分支（Default）
该分支为主要的开发分支，与项目有关的说明和代码文件可放置于此，在仓库被访问时默认展示该分支。
```
-|
--LICENSE   开源协议文件，默认为MIT开源协议。
--README.md 项目说明文件，可使用Markdowm编辑器进行编辑。
--requirements.txt Python项目依赖列表
```  

## 使用方式
A：在AI Studio上[运行本项目](https://aistudio.baidu.com/aistudio/projectdetail/1785557?_=1626793420926&shared=1)


B：此处由项目作者进行撰写使用方式。

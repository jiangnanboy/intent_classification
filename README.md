# 利用深度模型实现意图识别
    基于对话语句的意图进行识别，主要实现一些神经网络分类模型。
    可参考作者另一个项目：https://github.com/jiangnanboy/movie_knowledge_graph_app。
    这里使用电影问答的相关数据进行测试。
  
## 安装pyhanlp用作分词与实体识别
    电影类型：ng
    电影名：nm
    演员名：nnt
    
    1.下载hanlp模型和hanlp的jar包放在目录Anaconda3\Lib\site-packages\pyhanlp\static
    
    2.在路径Anaconda3\Lib\site-packages\pyhanlp\static\data\dictionary\custom下放以下文件(演员名.txt；电影名.txt；电影类型.txt；other.txt)，当自定义词典
        演员名.txt
        电影名.txt
        电影类型.txt
        other.txt
        
    3.修改自定义词典配制D:\Anaconda3\Lib\site-packages\pyhanlp\static\hanlp.properties
        CustomDictionaryPath=data/dictionary/custom/CustomDictionary.txt; 现代汉语补充词库.txt; 全国地名大全.txt ns; 人名词典.txt; 机构名词典.txt; 上海地名.txt ns; 电影类型.txt ng; 电影名.txt nm; 演员名.txt nnt; other.txt;data/dictionary/person/nrf.txt nrf;

## 项目结构
```
.
├── classification_data //训练和测试用数据
│   
├── feedforward_network
│   
├── textcnn
│       
├── textrnn
│   
├── textrcnn
│ 
├── transformer-encoder
│   
│  
│ 
.
```

## 意图识别

    1.利用分类模型对用户输入的问题进行意图识别
    
    (1).训练数据在目录 intent_classification\classification_data下
        电影训练数据：classification_segment_data.txt与classification_data.csv
        教育学科训练数据：knowledge_point_qa_data.csv
    
    (2).有16个意图的电影数据，见目录 intent_classification\classification_data\question_classification.txt；
        有9个意图的教育学科数据，见目录 intent_classification\classification_data\knowledge_point_qa_classification.txt；
    
    (3).识别和预测
    
        a.分类模型1，这里使用feedforward-network进行意图识别
    
        训练代码：intent_classification\feedforward_network\train.ipynb
        
        预测代码：intent_classification\feedforward_network\predict.ipynb
        
        b.分类模型2，这里使用textcnn进行意图识别
    
        其中[sgns.sogou.char]使用了sogou的预训练向量可从这里下载(https://github.com/Embedding/Chinese-Word-Vectors)
        
        训练代码：intent_classification\textcnn\train.ipynb
        
        预测代码：intent_classification\textcnn\predict.ipynb
        
        c.分类模型3，这里使用textrnn进行意图识别
    
        其中[sgns.sogou.char]使用了sogou的预训练向量可从这里下载(https://github.com/Embedding/Chinese-Word-Vectors)
        
        训练代码：intent_classification\textrnn\train.ipynb
        
        预测代码：intent_classification\textrnn\predict.ipynb
        
        d.分类模型4，这里使用textrcnn进行意图识别
    
        其中[sgns.sogou.char]使用了sogou的预训练向量可从这里下载(https://github.com/Embedding/Chinese-Word-Vectors)
        
        训练代码：intent_classification\textrcnn\train.ipynb
        
        预测代码：intent_classification\textrcnn\predict.ipynb
        
        e.分类模型5，这里使用transformer-encoder进行意图识别
    
        同上，可以使用预训练向量[sgns.sogou.char]
        
        训练代码：intent_classification\transformer_encoder\train.ipynb
        
        预测代码：intent_classification\transformer_encoder\predict.ipynb

### 后续......
    1.实现更多的深度分类模型
    2.利用深度模型代替pyhanlp识别实体
    ...
  
### `作者的qq，如您有什么想法可以和作者联系：2229029156。`

### `如果您支持作者继续开发更加完善的功能，请动一动手为此项目打个星吧或fork此项目，这是对作者最大的鼓励。` 

### Requirements
    requirement.txt

### References
* https://github.com/jiangnanboy/movie_knowledge_graph_app
    
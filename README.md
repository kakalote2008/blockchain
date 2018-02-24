# 迷你区块链（比特币）DEMO



## 安装

1. 安装 [Python 3.6+](https://www.python.org/downloads/) is installed. 
2. 安装 [pipenv](https://github.com/kennethreitz/pipenv). 

```
$ pip install pipenv 
```

3. 创建virtual env. 

```
$ pipenv --python=python3.6
```

4. 安装依赖.  

```
$ pipenv install 
```

5. 运行节点:
    * `$ pipenv run python blockchain.py` 
    * `$ pipenv run python blockchain.py -p 5001`
    * `$ pipenv run python blockchain.py --port 5002`
    
## Docker运行

另一种方式是使用Docker运行：

1. 克隆库
2. 构建docker容器

```
$ docker build -t blockchain .
```

3. 运行

```
$ docker run --rm -p 80:5000 blockchain
```

4. 添加多个节点:

```
$ docker run --rm -p 81:5000 blockchain
$ docker run --rm -p 82:5000 blockchain
$ docker run --rm -p 83:5000 blockchain
```

## DEMO
1 启动一个节点

pipenv run python blockchain.py

pipenv run python blockchain.py —port 5001

2 第一次挖矿

<http://127.0.0.1:5000/mine> 

http://127.0.0.1:5001/mine> 

3 创建一个交易（使用postman）

![image](https://github.com/kakalote2008/blockchain/img/1.png)

4 第一个节点再次挖矿

http://127.0.0.1:5000/mine> 

5 查看当前区块链,可以看到已经有三个块了

![image](https://github.com/kakalote2008/blockchain/img/2.png)

6 在两个节点上相互注册对方，使节点可通讯，注意需要对两个节点都执行此操作，此处省略了第二张截图（注意不要加入自身节点，会死循环哦）

![image](https://github.com/kakalote2008/blockchain/img/3.png)

7 在节点2调用共识算法，解决不同节点的链冲突问题，并对全网内的区块链有效性进行验证。可以看到，由于节点1是更长的链，节点2的区块链会被节点1取代。

![image](https://github.com/kakalote2008/blockchain/img/4.png)
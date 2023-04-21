# alist-glitch
在glitch上部署alist

# 教程
1. 在glitch中新建项目引入本项目
2. 将在alist-org/alist项目的release中下载ist-linux-musl-amd64.tar.gz，并解压出其中的alist二进制程序，并想办法将其放到公网（例如创建个github仓库给它扔release,下文中以https://example.org/alist为例）
3. 在glitch项目中打开termial，输入
```bash
wget https://example.org/alist -O alist
```

至此基本完成alist在glitch中的部署，由于glitch可以永久保存文件信息，故而可以直接用默认的sqlite数据库即可，只不过glitch免费用户的项目是不加密的，而alist项目的数据本身也是明文存储，故而直接使用有帐号、token泄露的风险（直接用个随机来的项目名称，谁找得到你呀，懒得搞可以直接用就是了）。因此可以通过使用外置数据库的方式来避免信息泄露。

在.env文件中添加环境变量（详情见[文档](https://github.com/alist-org/alist/blob/main/internal/conf/config.go)）

完结撒花


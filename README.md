# VPS-SSL-证书
关于vps申请证书的一种方法总结
---------------------------

脚本来源于https://www.v2rayssr.com/ssl.html

脚本来源于https://mgxray.xyz/index.php/archives/362/

第一步：域名一个 托管域名到 Cloudflare  解析vpsIP

-----------------------------

Acme 脚本申请证书

Debian/Ubuntu 系统命令如下

第二步：`apt update -y`

第三步：`apt install -y curl`

第四步：`apt install -y socat`

CentOS 系统命令如下

第二步：`yum update -y`

第三步：`yum install -y curl`

第四步：`yum install -y socat`

---------------------------------

安装 Acme 脚本

第五步：`curl https://get.acme.sh | sh`

-----------------------------------------------

申请证书及密钥

第六步：`~/.acme.sh/acme.sh --register-account -m xxxx@gmail.com`

第七步：`~/.acme.sh/acme.sh  --issue -d 删掉中文修改成你解析的域名   --standalone`

-----------------------------------------------------------------------------------

下载证书及密钥到指定文件夹

第八步：`~/.acme.sh/acme.sh --installcert -d 删掉中文修改成你解析的域名 --key-file /root/private.key --fullchain-file /root/cert.crt`  以下画圈的就是你的证书和密钥啦  我是使用Finalshell  ssh工具查看的

![Inkedphoto_2021-11-30_19-42-29_LI](https://user-images.githubusercontent.com/94978556/144041552-469a1a71-5337-4562-af9d-9576a61cdc22.jpg)

-------------------------------------------------------------

更新 Acme 脚本

升级 Acme.sh 到最新版本

`~/.acme.sh/acme.sh --upgrade`

如果你不想手动升级, 可以开启自动升级:

`~/.acme.sh/acme.sh  --upgrade  --auto-upgrade`

之后, acme.sh 就会自动保持更新了

-------------------------------------------------

X-ui 面板设置公钥和密钥文件路径

直接鼠标右键复制路径

![Inkedphoto_2021-11-30_19-42-29_LI](https://user-images.githubusercontent.com/94978556/144042417-f36fef7e-ebd1-4f30-91d1-91ec830efd19.jpg)

成功后保存配置和重启面板

![image](https://user-images.githubusercontent.com/94978556/144042626-ccc56e0a-2b9a-44df-ab1c-e32ee8f42b96.png)

之后就可以用你的域名加`https://你的域名:X-ui端口`登录你的面板啦





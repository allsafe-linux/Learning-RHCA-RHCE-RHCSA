三.首先从红帽认证 Ansible 自动化专家、红帽认证高级自动化专家：Ansible 最佳实践开始学习
1.红帽认证 Ansible 自动化专家

技能与知识，获得红帽 Ansible 自动化专业技能证书的 IT 专业人员能够执行以下任务：
    使用 Ansible 清单 (inventory) 定义主机组
    创建 Ansible playbook
    使用 playbook，将系统配置为指定的状态
    创建和使用 Ansible 模板来为主机创建自定义的配置文件
    创建 Ansible 角色
    利用 playbook 中的 Ansible Vault 保护敏感数据
    安装 Ansible Tower 并用它来管理系统

以下人士可能有兴趣考取红帽 Ansible 自动化专业技能证书：
    需要管理大量系统的系统管理员
    在 DevOps 环境中工作、并想实现大部分日常作业量自动化的系统管理员
    具有基本系统管理背景、并想实现开发流程自动化的开发人员
    有兴趣获得红帽专业技能证书或 RHCA 证书的 红帽认证工程师 (RHCE®)) 。

红帽 Ansible 自动化专业技能证书考试 (EX407)，通过此项考试的 IT 人士将获得红帽专业技能证书，并将计入红帽认证架构师的认证成绩中。 

考试概述
红帽认证 Ansible 自动化专家考试（EX407）旨在测试您运用 Ansible 实现系统和应用配置自动化的能力。
通过此项考试后，您将成为红帽认证 Ansible 自动化专家，并将计入红帽认证架构师（RHCA）的认证成绩中。
本课程基于红帽® 企业 Linux® 7.5 和 Ansible 2.7。
现在，此项考试涵盖的材料包含在红帽认证工程师 (RHCE) 考试 (EX294) 的课程中。此项新考试旨在测试您能否使用红帽 Ansible 自动化使不同功能实现自动化并有效扩展基础架构。
考核对象
    需要管理大量系统的系统管理员
    在 DevOps 环境中工作、并想实现大部分日常作业量自动化的系统管理员
    具有基本系统管理背景、并想实现开发流程自动化的开发人员
    有兴趣成为红帽认证专家或红帽认证架构师（RHCA）的红帽认证工程师（RHCE）
考试前提条件
    成功完成利用 Ansible 实现自动化（DO407）课程，或具有使用 Ansible 配置系统的同等经验
    建议先成为红帽认证系统管理员（RHCSA）或具有同等或更高的系统管理经验，但不强制要求

考查要点
我们建议考生在参加此项考试前先成为红帽认证工程师（RHCE®）或至少成为红帽认证系统管理员（RHCSA®），但两者并不强制要求。为了帮助您备考，请查看本文给出的考试目标，其中列出了操作任务的考查范围。红帽保留添加、更改和删除考试目标的权利。此类变更将在考前公布。
您应能够：
    了解 Ansible 的核心组件
        Inventory（配置文件）
        模块
        变量
        Fact
        Play
        Playbook
        配置文件
    安装和配置 Ansible 控制节点
        安装所需软件包
        创建静态主机 inventory 文件
        创建配置文件
    配置 Ansible 托管的节点
        创建 SSH 密钥并将其分配给托管节点
        在托管节点上配置权限提升
        使用 ad-hoc Ansible 命令验证有效配置
    创建运行 ad hoc Ansible 命令的简单 shell 脚本
    使用静态和动态 inventory 定义主机群组
    使用现有的动态 inventory 脚本
    创建 Ansible play 和 playbook
        了解如何使用常用的 Ansible 模块
        使用变量检索命令运行的结果
        使用条件控制 play 的执行
        配置错误处理
        创建 playbook，将系统配置为指定的状态
    使用 Ansible 模块执行有关以下内容的系统管理任务：
        软件包和存储库
        服务
        防火墙规则
        文件系统
        存储设备
        文件内容
        归档
        计划任务
        安全性
        用户和群组
    创建和使用模板来创建自定义的配置文件
    使用 Ansible 变量和 fact
    创建和使用角色
    从 Ansible Galaxy 下载角色并使用
    并行管理
    利用 playbook 中的 Ansible Vault 保护敏感数据
    使用提供的文档查找有关 Ansible 模块和命令的特定信息
对于所有实际任务操作型的红帽考试，您的所有系统配置必须在重启后仍然有效（无需人工干预）。

我们基于以上建议，正式开始进入Ansible 自动化专家的概念学习与实际操作吧。

我的物理主机配置：华南金牌X58主板，Xeon(R) CPU X5690 ，GeForce GTX 1060 6GB，32GB内存，275GB固态。
操作系统是Red Hat Enterprise Linux Server 7.9 update。
虚拟机采用了VMware® Workstation 16 Pro。
我准备利用5台本地虚拟机，1台树莓派4B和1台阿里云云主机来搭建出共计7个托管节点操作环境。
从红帽官网下载安装镜像文件：
Red Hat Enterprise Linux 8.3 Binary DVD
最新修改的:
    2020-10-14
SHA-256 Checksum:
    30fd8dff2d29a384bd97886fa826fa5be872213c81e853eae3f9d9674f720ad0 
 Red Hat Enterprise Linux 7.9 Binary DVD 
最新修改的:
    2020-09-18
SHA-256 Checksum:
    19d653ce2f04f202e79773a0cbeda82070e7527557e814ebbce658773fbe8191 

记得用sha256sum命令校验下镜像文件

物理主机叫master，update后安装以下软件包：
根据https://fedoraproject.org/wiki/EPEL#Quickstart介绍说明，导入EPEL源，有红帽账户的还可以开启额外的源
    RHEL/CentOS 7:
   # yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
    on RHEL 7 it is recommended to also enable the optional, extras, and HA repositories since EPEL packages may depend on packages from these repositories:
   # subscription-manager repos --enable "rhel-*-optional-rpms" --enable "rhel-*-extras-rpms"  --enable "rhel-ha-for-rhel-*-server-rpms"
    RHEL/CentOS 8:
   # yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
    on RHEL 8 it is required to also enable the codeready-builder-for-rhel-8-*-rpms repository since EPEL packages may depend on packages from it:
   # ARCH=$( /bin/arch )
   # subscription-manager repos --enable "codeready-builder-for-rhel-8-${ARCH}-rpms"
    on CentOS 8 it is recommended to also enable the powertools repository since EPEL packages may depend on packages from it:
   # dnf config-manager --set-enabled powertools

安装ansible和python3，依赖会自动安装。
yum install ansible-2.9.17-1.el7.noarch
yum install python3-3.6.8-18.el7.x86_64

配置master主机，使用普通用户进行操作，我这里的用户为rhel，家目录为/home/rhel。
复制ansible两个配置文件到用户目录下
cp /etc/ansible/ansible.cfg /home/rhel/
cp /etc/ansible/hosts /home/rhel/

编辑主机列表文件hosts，参考以下内容，根据实际建立主机清单文件。
vim hosts
    [webserver]
    192.168.197.128
    
    [nfsserver]
    192.168.197.129
    
    [dbserver]
    192.168.197.130
    
    [mailserver]
    192.168.197.131
    
    [dhcpserver]
    192.168.197.132
    
    [aliyun]
    allsafe.com

    [router]
    192.168.1.1

 编辑ansible配置文件ansible.cfg，参考以下内容进行修改。
 vim ansible.cfg
    inventory      = /home/rhel/hosts
    remote_user = ansiblenode
    [privilege_escalation]
    become=True
    become_method=sudo
    become_user=root
    become_ask_pass=False

生成ssh-key公私钥对，把公钥上传给托管节点。
[rhel@master ~]$ ssh-keygen -t rsa -P ''
生成的公私钥在.ssh/目录下

配置托管节点：
yum install python3
useradd ansiblenode
usermod -a ansiblenode -G wheel
passwd ansiblenode 密码为了方便都设置成一样的即可
vim /etc/ssh/sshd_config
    PermitRootLogin no
visudo
    ## Allows people in group wheel to run all commands
    # %wheel        ALL=(ALL)       ALL

    ## Same thing without a password
    %wheel  ALL=(ALL)       NOPASSWD: ALL
在主机上用命令把公钥上传给每台托管主机。
例如：ssh-copy-id -i .ssh/id_rsa.pub ansiblenode@192.168.1.101

做完以上后，我们用ansible的ping模块来检测下各个托管节点。
ansible all -m ping
成功的如下所示
192.168.1.101 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    }, 
    "changed": false, 
    "ping": "pong"
}
失败的如下所示
192.168.197.129 | UNREACHABLE! => {
    "changed": false, 
    "msg": "Failed to connect to the host via ssh: ssh: connect to host 192.168.197.129 port 22: No route to host", 
    "unreachable": true
}

用command模块输入id命令查看是以什么用户身份执行的。
ansible all -m command -a "id"
    192.168.197.128 | CHANGED | rc=0 >>
    uid=0(root) gid=0(root) 组=0(root) 环境=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
    192.168.197.130 | CHANGED | rc=0 >>
    uid=0(root) gid=0(root) 组=0(root) 环境=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
    192.168.197.132 | CHANGED | rc=0 >>
    uid=0(root) gid=0(root) 组=0(root) 环境=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
    192.168.197.131 | CHANGED | rc=0 >>
    uid=0(root) gid=0(root) 组=0(root) 环境=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
    192.168.197.129 | CHANGED | rc=0 >>
    uid=0(root) gid=0(root) 组=0(root) 环境=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
可以看到，我们虽然定义了remote_user = ansiblenode用户，但是我们实现了ansiblenode免密执行root权限的命令。

配置webserver，安装httpd，开启httpd服务，并在防火墙放行http服务。
yum模块，可以使用ansible-doc yum查看具体使用参数及方法。
ansible webserver -m yum -a "name=httpd state=latest"
service模块，开启httpd服务。
ansible webserver -m service -a "name=httpd state=started enabled=yes"
firewalld模块，立即放行并永久放行http服务。
ansible webserver -m firewalld -a "service=http state=enabled immediate=yes permanent=yes"

ansible webserver -m yum -a "name=nfs-utils state=latest"

配置nfsserver，安装nfs-utils，开启nfs-server服务，并在防火墙放行nfs、rpc-bind、mountd三个服务。
ansible nfsserver -m yum -a "name=nfs-utils state=latest"
copy模块，在nfs配置文件exports中写入配置信息，注意星号跟括号之间没有空格，如果有空格到时候就挂载出错。
ansible nfsserver -m copy -a 'content="/mnt 192.168.197.*(rw,sync,root_squash)" dest=/etc/exports'







=======================
openSUSE 源使用帮助
=======================

地址
====

https://mirrors.ustc.edu.cn/opensuse/

说明
====

openSUSE 软件源

收录架构
========

i586, x86_64

支持的版本
========

Leap 15.1-15.3, tumbleweed

使用说明
========

手动配置软件源
--------------

.. attention::
    以下配置方法适用于从未自行配置软件源的用户，其他用户请根据具体情况自行配置 ，以下仅供参考。

禁用所有原有软件源；

::

  sudo zypper mr -da

添加中科大镜像源，以 openSUSE Leap 为例：

::

  sudo zypper ar -fcg https://mirrors.ustc.edu.cn/opensuse/distribution/leap/\$releasever/repo/oss USTC:OSS
  sudo zypper ar -fcg https://mirrors.ustc.edu.cn/opensuse/distribution/leap/\$releasever/repo/non-oss USTC:NON-OSS
  sudo zypper ar -fcg https://mirrors.ustc.edu.cn/opensuse/update/leap/\$releasever/oss USTC:UPDATE-OSS
  sudo zypper ar -fcg https://mirrors.ustc.edu.cn/opensuse/update/leap/\$releasever/non-oss USTC:UPDATE-NON-OSS
  
建议 openSUSE Leap 15.3 用户不禁用所有软件源，而是手动禁用以上命令对应的官方源，并添加 USTC 提供的镜像站源。

对于 15.3 或更高版本的 openSUSE Leap，还需添加或替换 SLE 更新源：

::

  sudo zypper ar -fcg https://mirrors.ustc.edu.cn/opensuse/update/leap/\$releasever/sle USTC:UPDATE-SLE

对于 openSUSE Tumbleweed，只需执行：

::

  sudo zypper ar -fcg https://mirrors.ustc.edu.cn/opensuse/tumbleweed/repo/oss USTC:OSS
  sudo zypper ar -fcg https://mirrors.ustc.edu.cn/opensuse/tumbleweed/repo/non-oss USTC:NON-OSS


命令中最后一个参数为每一个源指定了一个 alias （别称），可以根据个人喜好更改。

手动刷新软件源：

::

  sudo zypper ref

图形界面下配置方法
-------------------

以 openSUSE Leap 15.3 为例：

#. 打开 YaST；
#. 点击 Software 分组中的 Software Repositories；
#. 在打开的窗口上方的列表中点击 Main Repository，点击 Edit；
#. 将 download.opensuse.org 替换为 mirrors.ustc.edu.cn/opensuse，点击 OK；
#. 再用同样的方法编辑 Non-OSS Repository, Main Update Repository, Update Repository (Non-Oss) 和 Update repository with updates from SUSE Linux Enterprise 15。

注意事项
========

* 由于使用了 MirrorBrain 技术，中央服务器 (download.opensuse.org) 会按照 IP
  地理位置中转下载请求到附近的镜像服务器（但刷新软件源时仍从中央服务器获取
  元数据），所以更改软件源通常只会加快刷新软件源的速度，而对下载速度影响不
  大，但对于经常滚动或重置的系统仍然有帮助（如 openSUSE Kubic、openSUSE MicroOS）。
  参见 `openSUSE 中文论坛 <https://forum.suse.org.cn/t/opensuse/1759>`_ 。
* 如果您无法正常播放在线视频（例如爱奇艺），请尝试添加 `Packman 软件源 <http://mirrors.ustc.edu.cn/help/packman.html>`_ ，并安装VLC播放器。
* 我们不提供 backports, source 和 debug 源，如您需要，请考虑其他镜像站，提供 Ports 的镜像站列表参见 `openSUSE Mirrors 信息页 <https://mirrors.opensuse.org/>`_ 。
* Tumbleweed 滚动发行版软件源的地址与上述例子稍有不同，一般为：
  https://mirrors.ustc.edu.cn/opensuse/Tumbleweed/[文件相对路径]。

相关链接
========

:官方主页: https://www.opensuse.org/
:邮件列表: https://en.opensuse.org/Communicate/Mailinglists
:论坛: https://forums.opensuse.org/
:中文论坛: https://forum.suse.org.cn/
:英文 Wiki: https://en.opensuse.org/
:中文 Wiki: https://zh.opensuse.org/
:文档: https://en.opensuse.org/Documentation
:中文社区主页: https://suse.org.cn/
:openSUSE Guide: https://lug.ustc.edu.cn/sites/opensuse-guide/

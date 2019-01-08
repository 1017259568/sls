# Windows {#concept_j22_xnv_vdb .concept}

Logtail客户端是日志服务提供的日志采集Agent，请参考本文档，在Windows服务器上安装Logtail客户端。

## 支持的系统 {#section_ppj_ynv_vdb .section}

Windows版Logtail客户端支持以下操作系统：

-   Windows 7 \(Client\) 32bit
-   Windows 7 \(Client\) 64bit
-   Windows Server 2008 32bit
-   Windows Server 2008 64bit
-   Windows Server 2012 64bit

## 前提条件 {#section_t52_5zm_1fb .section}

1.  已拥有一台及以上的服务器。
2.  已根据服务器类型和所在Region，确定日志采集流量的网络类型。详细说明请参考[选择网络](intl.zh-CN/用户指南/Logtail采集/选择网络.md)。

    ![](images/12057_zh-CN.png "选择网络")


## 安装Logtail {#section_d1z_znv_vdb .section}

1.  下载安装包。

    下载地址：

    -   中国大陆：单击下载[Logtail安装包](http://logtail-release.oss-cn-hangzhou.aliyuncs.com/win/logtail_installer.zip)。
    -   海外：单击下载[Logtail安装包](http://logtail-release-global.log-global.aliyuncs.com/win/logtail_installer.zip)。
2.  解压缩 `logtail_installer.zip` 到当前目录。
3.  根据服务器类型和所在区域[选择网络类型](intl.zh-CN/用户指南/Logtail采集/选择网络.md)后，按照日志服务所在区域安装Logtail。

    以管理员身份运行Windows Powershell或cmd进入`logtail_installer` 目录，即您所下载安装包的解压目录，并根据地域和网络环境执行相应的安装命令。

    安装命令：

    |区域|阿里云内网（经典网络、VPC）|公网|全球加速|
    |:-|:--------------|:-|:---|
    |**华北 1（青岛）**|.\\logtail\_installer.exe install cn-qingdao|.\\logtail\_installer.exe install cn-qingdao-internet|.\\logtail\_installer.exe install cn-qingdao-acceleration|
    |**华北 2（北京）**|.\\logtail\_installer.exe install cn-beijing|.\\logtail\_installer.exe install cn-beijing-internet|.\\logtail\_installer.exe install cn-beijing-acceleration|
    |**华北 3 （张家口）**|.\\logtail\_installer.exe install cn-zhangjiakou|.\\logtail\_installer.exe install cn-zhangjiakou-internet|.\\logtail\_installer.exe install cn-zhangjiakou-acceleration|
    |**华北 5 （呼和浩特）**|.\\logtail\_installer.exe install cn-huhehaote|.\\logtail\_installer.exe install cn-huhehaote-internet|.\\logtail\_installer.exe install cn-huhehaote-acceleration|
    |**华东 1（杭州）**|.\\logtail\_installer.exe install cn-hangzhou|.\\logtail\_installer.exe install cn-hangzhou-internet|.\\logtail\_installer.exe install cn-hangzhou-acceleration|
    |**华东 2（上海）**|.\\logtail\_installer.exe install cn-shanghai|.\\logtail\_installer.exe install cn-shanghai-internet|.\\logtail\_installer.exe install cn-shanghai-acceleration|
    |**华南 1（深圳）**|.\\logtail\_installer.exe install cn-shenzhen|.\\logtail\_installer.exe install cn-shenzhen-internet|.\\logtail\_installer.exe install cn-shenzhen-acceleration|
    |**西南 1（成都）**|.\\logtail\_installer.exe install cn-chengdu|.\\logtail\_installer.exe install cn-chengdu-internet|.\\logtail\_installer.exe install cn-chengdu-acceleration|
    |**香港**|.\\logtail\_installer.exe install cn-hongkong|.\\logtail\_installer.exe install cn-hongkong-internet|.\\logtail\_installer.exe install cn-hongkong-acceleration|
    |**美国西部 1 （硅谷）**|.\\logtail\_installer.exe install us-west-1|.\\logtail\_installer.exe install us-west-1-internet|.\\logtail\_installer.exe install us-west-1-acceleration|
    |**美国东部 1（弗吉尼亚）**|.\\logtail\_installer.exe install us-east-1|.\\logtail\_installer.exe install us-east-1-internet|.\\logtail\_installer.exe install us-east-1-acceleration|
    |**亚太东南 1（新加坡）**|.\\logtail\_installer.exe install ap-southeast-1|.\\logtail\_installer.exe install ap-southeast-1-internet|.\\logtail\_installer.exe install ap-southeast-1-acceleration|
    |**亚太东南 2（悉尼）**|.\\logtail\_installer.exe install ap-southeast-2|.\\logtail\_installer.exe install ap-southeast-2-internet|.\\logtail\_installer.exe install ap-southeast-2-acceleration|
    |**亚太东南 3（吉隆坡）**|.\\logtail\_installer.exe install ap-southeast-3|.\\logtail\_installer.exe install ap-southeast-3-internet|.\\logtail\_installer.exe install ap-southeast-3-acceleration|
    |**亚太东南 5（雅加达）**|.\\logtail\_installer.exe install ap-southeast-5|.\\logtail\_installer.exe install ap-southeast-5-internet|.\\logtail\_installer.exe install ap-southeast-5-acceleration|
    |**亚太南部 1（孟买）**|.\\logtail\_installer.exe install ap-south-1|.\\logtail\_installer.exe install ap-south-1-internet|.\\logtail\_installer.exe install ap-south-1-acceleration|
    |**亚太东北 1（日本）**|.\\logtail\_installer.exe install ap-northeast-1|.\\logtail\_installer.exe install ap-northeast-1-internet|.\\logtail\_installer.exe install ap-northeast-1-acceleration|
    |**欧洲中部 1（法兰克福）**|.\\logtail\_installer.exe install eu-central-1|.\\logtail\_installer.exe install eu-central-1-internet|.\\logtail\_installer.exe install eu-central-1-acceleration|
    |**中东东部 1（迪拜）**|.\\logtail\_installer.exe install me-east-1|.\\logtail\_installer.exe install me-east-1-internet|.\\logtail\_installer.exe install me-east-1-acceleration|
    |**英国（伦敦）**|.\\logtail\_installer.exe install eu-west-1|.\\logtail\_installer.exe install eu-west-1-internet|.\\logtail\_installer.exe install eu-west-1-acceleration|

    **说明：** 在自建IDC或其他云厂商服务器使用Logtail时，由于日志服务无法获取非本账号下ECS、其他服务器的属主信息，请在安装Logtail后手动配置用户标识（AliUid），否则Logtail心跳异常、无法收集日志。详细说明请参见 [为非本账号ECS、自建IDC配置AliUid](intl.zh-CN/用户指南/Logtail采集/机器组/为非本账号ECS、自建IDC配置AliUid.md)。


## 查看Logtail版本 {#section_dxc_1gf_ggb .section}

Logtail会自动安装到 `C:\Program Files (x86)\Alibaba\Logtail` 或 `C:\Program Files\Alibaba\Logtail` 目录中，您可以进入该目录，使用记事本或其他文本编辑器打开文件 `app_info.json`，其中的 `logtail_version` 字段即为您当前安装的Logtail的版本号。

例如，以下内容表示Logtail的版本号为1.0.0.0：

```
{
	"logtail_version" : "1.0.0.0"
}
```

## 升级Logtail {#section_fks_lwg_cfb .section}

-   **自动升级**

    通常情况下，Windows版Logtail支持自动升级。但将1.0.0.0之前的旧版升级为1.0.0.0及以上版本时，必须手动升级。

-   **手动升级**

    将1.0.0.0之前的旧版升级为1.0.0.0及以上版本时，必须手动升级。手动升级的步骤和[安装Logtail](#)相同，您只需要下载并解压最新的安装包，然后按照步骤执行安装即可。

    **说明：** 手动升级相当于自动卸载并重新安装，所以会删除掉您原先安装目录中的内容，如有必要，请您在执行手动升级前做好备份工作。

    安装目录：`C:\Program Files (x86)\Alibaba\Logtail` 或 `C:\Program Files\Alibaba\Logtail`。


## 手动启动和停止Logtail {#section_u2t_4wg_cfb .section}

打开**控制面板**中的**管理工具**，打开**服务**。

根据您所安装的版本找到对应的服务：

-   0.x.x.x版本：**LogtailWorker**服务。
-   1.0.0.0及以上版本：**LogtailDaemon**服务。

-   **手动启动**：右键单击**启动**。

-   **停止**：右键单击**停止**。

-   **重启**：右键单击**重新启动**。


## 卸载Logtail {#section_bk1_14v_vdb .section}

以管理员身份运行Windows Powershell或cmd进入 `logtail_installer` 目录，即您所下载安装包的解压目录，执行命令：

```
.\logtail_installer.exe uninstall
```

卸载成功后，您的Logtail安装目录C:\\Program Files \(x86\)\\Alibaba\\Logtail或C:\\Program Files\\Alibaba\\Logtail会被完全删除，但是仍有部分配置会被保留在 C:\\LogtailData目录中，您可以根据实际情况进行手动删除。遗留配置信息包括：

-   checkpoint：保存所有插件（比如Windows event log插件）的checkpoint信息。
-   logtail\_check\_point：保存Logtail主体部分的checkpoint信息。
-   users：保存所配置的用户标识（Aliuid）信息。


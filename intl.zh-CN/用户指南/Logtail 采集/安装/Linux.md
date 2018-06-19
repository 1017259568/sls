# Linux {#concept_u5y_3lv_vdb .concept}

## 支持的系统 {#section_tjc_wlv_vdb .section}

支持如下版本的Linux x86-64（64位）服务器

-   Aliyun Linux
-   Ubuntu
-   Debian
-   CentOS
-   OpenSUSE

## 安装Logtail {#section_h2x_fmv_vdb .section}

覆盖安装模式，如之前已安装过Logtail，那么安装器会先执行卸载、删除`/usr/local/ilogtail` 目录后再重新安装。安装后默认启动Logtail并注册开机启动。

请根据机器所处的网络环境和日志服务所在Region下载安装器，选择不同参数进行安装。

请参考本文档安装方式执行安装步骤。如果安装失败，单击[工单系统](https://selfservice.console.aliyun.com/ticket/category/sls/today)提工单。

**安装方式**

安装Logtail只需下载安装脚本并执行即可，您需要根据不同地域、不同网络类型选择对应的**安装参数**。

**安装参数**

**说明：** Docker和Kubernetes安装中的`${your_region_name}` 即为下表中的参数，请直接拷贝。

各区域下不同网络环境安装参数如下（建议直接拷贝对应章节的安装方式）：

|区域|经典网|VPC|公网（自建IDC）|
|:-|:--|:--|:--------|
|华北 2（北京）|cn-beijing|cn-beijing\_vpc|cn-beijing\_internet|
|华北 1（青岛）|cn-qingdao|cn-qingdao\_vpc|cn-qingdao\_internet|
|华东 1（杭州）|cn-hangzhou|cn-hangzhou\_vpc|cn-hangzhou\_internet|
|华东 2（上海）|cn-shanghai|cn-shanghai\_vpc|cn-shanghai\_internet|
|华南 1（深圳）|cn-shenzhen|cn-shenzhen\_vpc|cn-shenzhen\_internet|
|华北 3（张家口）|cn-zhangjiakou|cn-zhangjiakou\_vpc|cn-zhangjiakou\_internet|
|华北 5（呼和浩特）|cn-huhehaote|cn-huhehaote|cn-huhehaote\_internet|
|西南 1|无此类型|cn-chengdu|cn-chengdu\_internet|
|香港|cn-hongkong|cn-hongkong\_vpc|cn-hongkong\_internet|
|美国西部 1（硅谷）|us-west-1|us-west-1\_vpc|us-west-1\_internet|
|美国东部 1（弗吉尼亚）|无此类型网络|us-east-1|us-east-1\_internet|
|亚太东南 1（新加坡）|ap-southeast-1|ap-southeast-1\_vpc|ap-southeast-1\_internet|
|亚太东南 2（悉尼）|ap-southeast-2|ap-southeast-2\_vpc|ap-southeast-2\_internet|
|亚太东南 3（吉隆坡）|ap-southeast-3|ap-southeast-3|ap-southeast-3\_internet|
|亚太东南 5（雅加达）|无此类型网络|ap-southeast-5|ap-southeast-5\_internet|
|亚太南部 1（孟买）|无此类型网络|ap-south-1|ap-south-1\_internet|
|亚太东北 1（日本）|ap-northeast-1|ap-northeast-1\_vpc|ap-northeast-1\_internet|
|欧洲中部 1（法兰克福）|eu-central-1|eu-central-1\_vpc|eu-central-1\_internet|
|中东东部 1（迪拜）|me-east-1|me-east-1\_vpc|me-east-1\_internet|
|华东 1金融云（杭州）|无此类型网络|cn-hangzhou-finance|无此类型网络|
|华东 2金融云（上海）|无此类型网络|cn-shanghai-finance|无此类型网络|
|华南 1金融云（深圳）|无此类型网络|cn-shenzhen-finance|无此类型网络|

## **ECS经典网络** {#section_m32_rmv_vdb .section}

数据通过阿里云内网写入日志服务，不消耗公网带宽。适用于阿里云ECS。

-   注：新开地域（海外、张北等）默认新开通ECS都是VPC网络，请查看VPC部分介绍。
-   华北 2（北京）

    ```
    wget http://logtail-release-bj.oss-cn-beijing-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-beijing
    ```

-   华北 1（青岛）

    ```
    wget http://logtail-release-qd.oss-cn-qingdao-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-qingdao
    ```

-   华东 1（杭州）

    ```
    wget http://logtail-release.oss-cn-hangzhou-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-hangzhou
    ```

-   华东 2（上海）

    ```
    wget http://logtail-release-sh.oss-cn-shanghai-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-shanghai
    ```

-   华南 1（深圳）

    ```
    wget http://logtail-release-sz.oss-cn-shenzhen-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-shenzhen
    ```

-   华北 3 （张家口）

    ```
    wget http://logtail-release-zjk.oss-cn-zhangjiakou-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-zhangjiakou
    ```

-   华北 5 （呼和浩特）

    ```
    wget http://logtail-release-huhehaote.oss-cn-huhehaote-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-huhehaote
    ```

-   香港

    ```
    wget http://logtail-release-hk.oss-cn-hongkong-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-hongkong
    ```

-   美国西部 1 （硅谷）

    ```
    wget http://logtail-release-us-west-1.oss-us-west-1-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install us-west-1
    ```

-   亚太东南 1 （新加坡）

    ```
    wget http://logtail-release-ap-southeast-1.oss-ap-southeast-1-internal.aliyuncs.com/linux64/logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-southeast-1
    ```

-   亚太东南 2 （悉尼）

    ```
    wget http://logtail-release-ap-southeast-2.oss-ap-southeast-2-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-southeast-2
    ```

-   亚太东南 3 （吉隆坡）

    ```
    wget http://logtail-release-ap-southeast-3.oss-ap-southeast-3-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-southeast-3
    ```

-   亚太东北 1 （日本）

    ```
    wget http://logtail-release-ap-northeast-1.oss-ap-northeast-1-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-northeast-1
    ```

-   欧洲中部 1 （法兰克福）

    ```
    wget http://logtail-release-eu-central-1.oss-eu-central-1-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install eu-central-1
    ```

-   中东东部 1 （迪拜）

    ```
    wget http://logtail-release-me-east-1.oss-me-east-1-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install me-east-1
    ```


## ECS 专有网络 VPC {#section_j33_smv_vdb .section}

数据通过阿里云专有网络写入日志服务。适用于阿里云 ECS VPC。

-   华北 2（北京）

    ```
    wget http://logtail-release-bj.vpc100-oss-cn-beijing.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-beijing_vpc
    ```

-   华北 1（青岛）

    ```
    wget http://logtail-release-qd.vpc100-oss-cn-qingdao.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-qingdao_vpc
    ```

-   华东 1（杭州）

    ```
    wget http://logtail-release.vpc100-oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-hangzhou_vpc
    ```

-   华东 2（上海）

    ```
    wget http://logtail-release-sh.vpc100-oss-cn-shanghai.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-shanghai_vpc
    ```

-   华南 1（深圳）

    ```
    wget http://logtail-release-sz.vpc100-oss-cn-shenzhen.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-shenzhen_vpc
    ```

-   华北 3 （张家口）

    ```
    wget http://logtail-release-zjk.oss-cn-zhangjiakou-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-zhangjiakou_vpc
    ```

-   华北 5 （呼和浩特）

    ```
    wget http://logtail-release-huhehaote.oss-cn-huhehaote-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-huhehaote
    ```

-   西南 1 （成都）

    ```
    wget http://logtail-release-cn-chengdu.oss-cn-chengdu-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-chengdu
    ```

-   香港

    ```
    wget http://logtail-release-hk.vpc100-oss-cn-hongkong.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-hongkong_vpc
    ```

-   美国西部 1 （硅谷）

    ```
    wget http://logtail-release-us-west-1.vpc100-oss-us-west-1.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install us-west-1_vpc
    ```

-   美国东部 1 （弗吉尼亚）

    ```
    wget http://logtail-release-us-east-1.vpc100-oss-us-east-1.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install us-east-1
    ```

-   亚太东南 1 （新加坡）

    ```
    wget http://logtail-release-ap-southeast-1.vpc100-oss-ap-southeast-1.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-southeast-1_vpc
    ```

-   亚太东南 2 （悉尼）

    ```
    wget http://logtail-release-ap-southeast-2.oss-ap-southeast-2-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-southeast-2_vpc
    ```

-   亚太东南 3 （吉隆坡）

    ```
    wget http://logtail-release-ap-southeast-3.oss-ap-southeast-3-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-southeast-3
    ```

-   亚太东南 5 （雅加达）

    ```
    wget http://logtail-release-ap-southeast-5.oss-ap-southeast-5-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-southeast-5
    ```

-   亚太东北 1 （日本）

    ```
    wget http://logtail-release-ap-northeast-1.oss-ap-northeast-1-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-northeast-1_vpc
    ```

-   欧洲中部 1 （法兰克福）

    ```
    wget http://logtail-release-eu-central-1.oss-eu-central-1-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install eu-central-1_vpc
    ```

-   中东东部 1 （迪拜）

    ```
    wget http://logtail-release-me-east-1.oss-me-east-1-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install me-east-1_vpc
    ```

-   亚太南部 1 （孟买）

    ```
    wget http://logtail-release-ap-south-1.oss-ap-south-1-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-south-1
    ```


## 公网（自建 IDC 或其它云主机） {#section_xc3_5mv_vdb .section}

数据通过公网写入日志服务，占用公网带宽。适用于非阿里云虚拟机或其它IDC。

**说明：** 日志服务无法获取非阿里云机器的属主信息，请在安装Logtail后手动配置用户标识，参见 [非本人ECS（或线下机器）](intl.zh-CN/用户指南/Logtail 采集/机器组/非本人ECS（或线下机器）.md)，否则 Logtail心跳异常、无法收集日志。

-   华北 2（北京）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-beijing_internet
    ```

-   华北 1（青岛）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-qingdao_internet
    ```

-   华东 1（杭州）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-hangzhou_internet
    ```

-   华东 2（上海）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-shanghai_internet
    ```

-   华南 1（深圳）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-shenzhen_internet
    ```

-   华北 3 （张家口）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-zhangjiakou_internet
    ```

-   华北 5 （呼和浩特）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-huhehaote_internet
    ```

-   西南 1 （成都）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-chengdu_internet
    ```

-   香港

    ```
    wget http://logtail-release-hk.oss-cn-hongkong.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-hongkong_internet
    ```

-   美国西部 1 （硅谷）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install us-west-1_internet
    ```

-   美国东部 1 （弗吉尼亚）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install us-east-1_internet
    ```

-   亚太东南 1 （新加坡）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-southeast-1_internet
    ```

-   亚太东南 2 （悉尼）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-southeast-2_internet
    ```

-   亚太东南 3 （吉隆坡）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-southeast-3_internet
    ```

-   亚太东南 5 （雅加达）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-southeast-5_internet
    ```

-   亚太东北 1 （日本）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-northeast-1_internet
    ```

-   欧洲中部 1 （法兰克福）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install eu-central-1_internet
    ```

-   中东东部 1 （迪拜）

    ```
    wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install me-east-1_internet
    ```

-   亚太南部 1 （孟买）

    ```
    wget http://logtail-release-ap-south-1.oss-ap-south-1.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install ap-south-1_internet
    ```


## ECS 金融云 {#section_xrx_wmv_vdb .section}

-   华东 1（杭州）

    ```
    wget http://logtail-release-hz-finance.oss-cn-hzjbp-a-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-hangzhou-finance
    ```

-   华东 2（上海）

    ```
    wget http://logtail-release-sh-finance.oss-cn-shanghai-finance-1-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-shanghai-finance
    ```

-   华南 1（深圳）

    ```
    wget http://logtail-release-sz-finance.oss-cn-shenzhen-finance-1-internal.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install cn-shenzhen-finance
    ```


## 查看Logtail版本 {#section_t5v_xyq_zdb .section}

Logtail会将版本信息记录在`/usr/local/ilogtail/app_info.json`中的`logtail_version`字段，例如：

```
$cat /usr/local/ilogtail/app_info.json
{
   "UUID" : "0DF18E97-0F2D-486F-B77F-*********",
   "hostname" : "david*******",
   "instance_id" : "F4FAFADA-F1D7-11E7-846C-00163E30349E_*********_1515129548",
   "ip" : "**********",
   "logtail_version" : "0.16.0",
   "os" : "Linux; 2.6.32-220.23.2.ali1113.el5.x86_64; #1 SMP Thu Jul 4 20:09:15 CST 2013; x86_64",
   "update_time" : "2018-01-05 13:19:08"
}
```

## 升级Logtail {#section_jcz_xmv_vdb .section}

升级Logtail和安装的操作步骤一致，如果您已经安装logtail，再次执行升级命令时将自动卸载并安装最新版本的Logtail。

## 手动启动和停止Logtail {#section_fvl_zmv_vdb .section}

-   启动

    以管理员身份执行：

    ```
    /etc/init.d/ilogtaild start
    ```

-   停止

    以管理员身份执行：

    ```
    /etc/init.d/ilogtaild stop
    ```


## 卸载Logtail {#section_c1m_1nv_vdb .section}

参考 [安装Logtail](#section_h2x_fmv_vdb) 下载安装器 **logtail.sh**，shell下以管理员身份执行：

```
wget http://logtail-release.oss-cn-hangzhou.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh uninstall
```


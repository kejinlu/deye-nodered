# 德业除湿机 + Node-RED + Homeassistant

通过Node-RED我们可以将德业除湿机接入诸如Homeassistant这样的服务，方便管理。

### 1.获取德业除湿机配置信息
首先通过 https://github.com/kejinlu/deyeinfo 的脚本我们可以很轻松的获得我们所需要的德业除湿机mqtt服务的相关信息。

MQTT协议分析可以参见 https://kejinlu.com/2022/10/deye-homeassistant/


### 2.Node-RED中导入流程
然后我们将[flows.json](https://github.com/kejinlu/deye-nodered/blob/main/flows.json)导入Node-RED，可以看到类似下面的Flows：

<img src="https://cdn.nlark.com/yuque/0/2022/jpeg/328998/1663416912321-f974b598-ae50-45c6-b498-bfefd271a356.jpeg?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_40%2Ctext_5Y2i5YWL%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10%2Fresize%2Cw_1402%2Climit_0" width="50%">

### 3.根据自己的情况完善修改流程配置和代码

<img src="https://cdn.nlark.com/yuque/0/2022/jpeg/328998/1663422712467-36400a18-7bc8-4de0-9d9f-33af0e576ae7.jpeg?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_49%2Ctext_5Y2i5YWL%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10%2Fresize%2Cw_1500%2Climit_0" width="50%">

<img src="https://cdn.nlark.com/yuque/0/2022/jpeg/328998/1663422712449-2fae570f-4c77-4157-bb75-6be48ed5b834.jpeg?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_36%2Ctext_5Y2i5YWL%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10" width="50%">

- “德业除湿机状态接受” 设置德业官方MQTT服务的配置以及状态的topic
- “状态转发”节点中设置好本地MQTT服务的配置。
- “自动刷新”节点可以设置主动刷新状态的时间间隔，德业这方便设计的不是特别好，状态的及时更新依赖于本地的轮询刷新命令
- 三个“设置”节点们需要配置好本地mqtt服务
- “德业除湿机命令发送”节点设置好德业官方MQTT命令topic
- “解析状态”和“设置命令”节点中，需要根据自己设备的MQTT协议抓包结果来做相关的修改适配，因为不同设备一些状态码，或者命令码有细微的差别。

### 4.接入Homeassistant中   
根据[configuration.yaml](https://github.com/kejinlu/deye-nodered/blob/main/configuration.yaml)中的示范配置，将除湿机和相关的传感器配置到自己的Homeassistant的配置中
<img src="https://cdn.nlark.com/yuque/0/2022/jpeg/328998/1663416912263-7d27931d-ab17-4566-a62c-7456620d62f3.jpeg?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_28%2Ctext_5Y2i5YWL%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10" width="50%">




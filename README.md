# 德业除湿机 + Node-RED

通过Node-RED我们可以将德业除湿机接入诸如Homeassistant这样的服务，方便管理。
首先通过 https://github.com/kejinlu/deyeinfo 的脚本我们可以很轻松的获得我们所需要的德业除湿机mqtt服务的相关信息，然后我们将flows.json导入Node-RED，可以看到类似下面的Flows：

<img src="https://cdn.nlark.com/yuque/0/2022/jpeg/328998/1663416912321-f974b598-ae50-45c6-b498-bfefd271a356.jpeg?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_40%2Ctext_5Y2i5YWL%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10%2Fresize%2Cw_1402%2Climit_0" width="50%">

流程中所有的MQTT的节点我们都需要根据自己获取的信息填上正确的配置。
> 德业官方MQTT服务配置1
<img src="https://cdn.nlark.com/yuque/0/2022/jpeg/328998/1663422712467-36400a18-7bc8-4de0-9d9f-33af0e576ae7.jpeg?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_49%2Ctext_5Y2i5YWL%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10%2Fresize%2Cw_1500%2Climit_0" width="50%">
> 德业官方MQTT服务配置2
<img src="https://cdn.nlark.com/yuque/0/2022/jpeg/328998/1663422712449-2fae570f-4c77-4157-bb75-6be48ed5b834.jpeg?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_36%2Ctext_5Y2i5YWL%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10" width="50%">



> 接入Homeassistant中   
<img src="https://cdn.nlark.com/yuque/0/2022/jpeg/328998/1663416912263-7d27931d-ab17-4566-a62c-7456620d62f3.jpeg?x-oss-process=image%2Fwatermark%2Ctype_d3F5LW1pY3JvaGVp%2Csize_28%2Ctext_5Y2i5YWL%2Ccolor_FFFFFF%2Cshadow_50%2Ct_80%2Cg_se%2Cx_10%2Cy_10" width="50%">




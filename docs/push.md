### Push ###

    clouda.mbaas.push

推送服务

**方法：**

- registerUnicast(options)
- unregisterUnicast(options)
- registerMulticast(options)
- unregisterMulticast(options)


#### registerUnicast ####
    registerUnicast(options)

**功能描述：**

轻应用单播服务订阅. Push绑定，为当前设备用户添加一个轻应用绑定关系。需要向Push服务端发起绑定，绑定成功后返回给应用channelid和userid，应用用它们来做单播推送。用这个接口，JS层可以给轻应用提供发帖、关注问题等推送。

**参数说明：**

options：为object类型，其中包括以下参数：

<table style="border-style: solid; border-width: 0pt;" border="1" cellspacing="0" cellpadding="5px">
    <tbody>
        <tr>
            <th>参数</th>
            <th>类型</th>
            <th>描述</th>
        </tr>
        <tr>
			<td>onsuccess</td>
			<td>function(data){}</td>            
			<td>订阅成功，返回PushInfo对象</td>  
		</tr>
        <tr>
			<td>onfail</td>
			<td>function(err){}</td>          
			<td>订阅失败，返回错误码信息</td>  
		</tr>
    </tbody>
</table>

**返回的PushInfo对象：**
<table style="border-style: solid; border-width: 0pt;" border="1" cellspacing="0" cellpadding="5px">
    <tbody>
        <tr>
            <th>参数</th>
            <th>类型</th>
            <th>描述</th>
        </tr>
        <tr>
			<td>pushToken</td>
			<td>string</td>            
			<td>channelid + userid + cuid的加密串，框用于推送的特定格式</td>  
		</tr>
        <tr>
			<td>error</td>
			<td>number</td>          
			<td>0 - 订阅成功；1 - 内部错误:功能的处理过程中出现错误, 具体错误信息查看error_msg字段 2 - 参数错误 3 – 超时 4 Referer非法 5 – sdcard无效</td>
		</tr>
    </tbody>
</table>



#### unregisterUnicast ####
    unregisterUnicast(options)

**功能描述：**

轻应用单播服务取消订阅. Push解绑定，为当前设备用户解除一个轻应用绑定关系。解绑定后，订阅消息、服务订阅消息、话题订阅消息都将收不到。

**参数说明：**

options：为object类型，其中包括以下参数：

<table style="border-style: solid; border-width: 0pt;" border="1" cellspacing="0" cellpadding="5px">
    <tbody>
        <tr>
            <th>参数</th>
            <th>类型</th>
            <th>描述</th>
        </tr>
        <tr>
			<td>onsuccess</td>
			<td>function(data){}</td>            
			<td>取消订阅成功，返回info对象</td>
		</tr>
        <tr>
			<td>onfail</td>
			<td>function(err){}</td>
			<td>取消订阅失败，返回错误码信息</td>
		</tr>
    </tbody>
</table>

**返回的info对象：**
<table style="border-style: solid; border-width: 0pt;" border="1" cellspacing="0" cellpadding="5px">
    <tbody>
        <tr>
            <th>参数</th>
            <th>类型</th>
            <th>描述</th>
        </tr>
        <tr>
			<td>error</td>
			<td>number</td>          
			<td>0 - 订阅成功；1 - 内部错误:功能的处理过程中出现错误, 具体错误信息查看error_msg字段 2 - 参数错误 3 – 超时 4 Referer非法 5 – sdcard无效</td>
		</tr>
    </tbody>
</table>


#### registerMulticast ####
    registerMulticast(options)

**功能描述：**

轻应用组播服务订阅. 在轻应用内为用户提供相关服务订阅的支持，即给轻应用绑定TAG，如果轻应用没有绑定，Push会自行绑定轻应用。

**参数说明：**

options：为object类型，其中包括以下参数：

<table style="border-style: solid; border-width: 0pt;" border="1" cellspacing="0" cellpadding="5px">
    <tbody>
        <tr>
            <th>参数</th>
            <th>类型</th>
            <th>描述</th>
        </tr>
        <tr>
			<td>onsuccess</td>
			<td>function(data){}</td>
			<td>订阅成功，返回PushInfo对象</td>
		</tr>
        <tr>
			<td>onfail</td>
			<td>function(err){}</td>          
			<td>订阅失败，返回错误码信息</td>  
		</tr>
		<tr>
			<td>tag</td>
			<td>string</td>      
			<td>tag，订阅的服务所用的tag名称</td>  
		</tr>
    </tbody>
</table>

**返回的info对象：**
<table style="border-style: solid; border-width: 0pt;" border="1" cellspacing="0" cellpadding="5px">
    <tbody>
        <tr>
            <th>参数</th>
            <th>类型</th>
            <th>描述</th>
        </tr>
        <tr>
			<td>error</td>
			<td>number</td>        
			<td>0 - 订阅成功；1 - 内部错误:功能的处理过程中出现错误, 具体错误信息查看error_msg字段 2 - 参数错误 3 – 超时 4 Referer非法 5 – sdcard无效</td>
		</tr>
        <tr>
			<td>tag</td>
			<td>string</td>
			<td>TAG信息</td>
		</tr>
    </tbody>
</table>




#### unregisterMulticast ####
    unregisterMulticast(options)

**功能描述：**

轻应用组播服务订阅. 在轻应用内为用户提供相关服务订阅的支持，即给轻应用绑定TAG，如果轻应用没有绑定，Push会自行绑定轻应用。

**参数说明：**

options：为object类型，其中包括以下参数：

<table style="border-style: solid; border-width: 0pt;" border="1" cellspacing="0" cellpadding="5px">
    <tbody>
        <tr>
            <th>参数</th>
            <th>类型</th>
            <th>描述</th>
        </tr>
        <tr>
			<td>onsuccess</td>
			<td>function(data){}</td>            
			<td>取消订阅成功，返回PushInfo对象</td>
		</tr>
        <tr>
			<td>onfail</td>
			<td>function(err){}</td>          
			<td>取消订阅失败，返回错误码信息</td>  
		</tr>
		<tr>
			<td>tag</td>
			<td>string</td>      
			<td>tag，订阅的服务所用的tag名称</td>  
		</tr>
    </tbody>
</table>

**返回的info对象：**
<table style="border-style: solid; border-width: 0pt;" border="1" cellspacing="0" cellpadding="5px">
    <tbody>
        <tr>
            <th>参数</th>
            <th>类型</th>
            <th>描述</th>
        </tr>
        <tr>
			<td>error</td>
			<td>number</td>        
			<td>0 - 订阅成功；1 - 内部错误:功能的处理过程中出现错误, 具体错误信息查看error_msg字段 2 - 参数错误 3 – 超时 4 Referer非法 5 – sdcard无效</td>
		</tr>
        <tr>
			<td>tag</td>
			<td>string</td>
			<td>TAG信息</td>
		</tr>
    </tbody>
</table>
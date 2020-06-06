---
title: Элемент <system.Net> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154560"
---
# <a name="systemnet-element-network-settings"></a>Элемент \<system.Net> (параметры сети)
Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[authenticationModules](authenticationmodules-element-network-settings.md)|Указывает модули, используемые для проверки подлинности интернет запросов.|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Указывает максимальное число подключений к узлу в Интернете.|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Настраивает прокси-сервер протокола передачи гипертекста (HTTP).|  
|[маилсеттингс](mailsettings-element-network-settings.md)|Настраивает параметры отправки почты по протоколу SMTP.|  
|[requestCaching](requestcaching-element-network-settings.md)|Управляет механизмом кэширования для сетевых запросов.|  
|[параметры](settings-element-network-settings.md)|Настраивает основные сетевые параметры для классов в <xref:System.Net> и связанных дочерних пространствах имен.|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Указывает модули, используемые для запроса информации от узлов Интернета.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Конфигурация](../configuration-element.md)|Содержит параметры для всех пространств имен.|  
  
## <a name="remarks"></a>Примечания  
 [\<system.net>](system-net-element-network-settings.md)Элемент содержит параметры для классов в <xref:System.Net> и связанных дочерних пространствах имен. Параметры настройки модулей проверки подлинности, управления подключениями, параметров почты, прокси-сервера и модулей запросов Интернета для получения данных от узлов Интернета.  
  
## <a name="example"></a>Пример  
 В следующем примере показана типичная конфигурация, используемая <xref:System.Net> классами.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров сети](index.md)

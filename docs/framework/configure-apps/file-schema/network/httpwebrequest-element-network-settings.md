---
title: Элемент <httpWebRequest> (параметры сети)
description: <httpWebRequest>Элемент Параметры сети настраивает параметры веб-запроса в .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 86960a33d0924013e2bfbfa743eab372181033b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195432"
---
# <a name="httpwebrequest-element-network-settings"></a>Элемент \<httpWebRequest> (параметры сети)

Настраивает параметры веб-запроса.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Attribute**|**Описание**|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|Задает максимальную длину заголовка ответа в килобайтах. Значение по умолчанию — 64. Значение-1 указывает на то, что в заголовках ответа ограничение размера не накладывается.|  
|`maximumErrorResponseLength`|Указывает максимальную длину ответа на ошибку в килобайтах. Значение по умолчанию — 64. Значение-1 указывает, что в ответе на ошибку не будет накладывается никаких ограничений на размер.|  
|`maximumUnauthorizedUploadLength`|Указывает максимальную длину отправки в ответ на несанкционированный код ошибки в байтах. Значение по умолчанию — -1. Значение -1 указывает на отсутствие ограничений.|  
|`useUnsafeHeaderParsing`|Указывает, включен ли анализ ненадежных заголовков. Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[параметры](settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Remarks  

 По умолчанию .NET Framework строго применяет RFC 2616 для синтаксического анализа URI. Некоторые серверные ответы могут содержать управляющие символы в запрещенных полях, что приведет к вызову <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> метода <xref:System.Net.WebException> . Если **усеунсафехеадерпарсинг** имеет значение **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> в этом случае не будет создаваться исключение, однако приложение будет уязвимо для нескольких форм атак с синтаксическим анализом URI. Лучшим решением является изменение сервера, чтобы ответ не включал управляющие символы.  
  
## <a name="configuration-files"></a>Файлы конфигурации  

 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как задать большую, чем нормальную максимальную длину заголовка.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [Схема параметров сети](index.md)

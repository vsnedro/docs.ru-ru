---
description: 'Дополнительные сведения о <webRequestModules> элементе: Element (параметры сети)'
title: Элемент <webRequestModules> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: 851aec2bf38910239874cb5792239a48de6efb70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698431"
---
# <a name="webrequestmodules-element-network-settings"></a>Элемент \<webRequestModules> (параметры сети)

Указывает модули, используемые для запроса сведений от сетевых узлов.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  

 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[add](add-element-for-webrequestmodules-network-settings.md)|Добавляет пользовательский модуль веб-запросов в приложение.|  
|[пусто](clear-element-for-webrequestmodules-network-settings.md)|Удаляет из приложения все зарегистрированные модули веб-запросов.|  
|[remove](remove-element-for-webrequestmodules-network-settings.md)|Удаляет пользовательский модуль веб-запросов из приложения.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.|  
  
## <a name="remarks"></a>Remarks  

 Элемент `webRequestModules` регистрирует потомки класса <xref:System.Net.WebRequest>, чтобы обработать запросы информации к сетевым узлам. Модули веб-запросов должны реализовывать <xref:System.Net.IWebRequestCreate> интерфейс.  
  
 Платформа .NET Framework включает модули веб-запросов для URI, которые начинаются с `http://` , `https://` и `file://` . Модули по умолчанию можно переопределить только путем регистрации пользовательского модуля в файле конфигурации.  
  
## <a name="configuration-files"></a>Файлы конфигурации  

 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  

 В следующем примере регистрируется HTTP-модуль по умолчанию. Необходимо заменить значения для Version и PublicKeyToken правильными значениями для указанного модуля.  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [Схема параметров сети](index.md)

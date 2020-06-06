---
title: Элемент <system.web> (веб-параметры)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152845"
---
# <a name="systemweb-element-web-settings"></a>Элемент \<system.web> (веб-параметры)
Содержит сведения о том, как уровень размещения ASP.NET управляет поведением всего процесса.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  

Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|Задает параметры конфигурации для пулов приложений IIS в файле aspnet. config.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Указывает корневой элемент в каждом файле конфигурации, который используется средой CLR и .NET Framework приложениями.|  
  
## <a name="remarks"></a>Примечания  

`system.web`Элемент и его дочерний `applicationPool` элемент были добавлены в .NET Framework в .NET Framework 3,5 с пакетом обновления 1 (SP1). При запуске IIS 7,0 или более поздних версий в интегрированном режиме эта комбинация элементов позволяет настроить, как ASP.NET управляет потоками и как она помещает запросы в очередь, когда ASP.NET размещается в пуле приложений IIS. При запуске IIS 7,0 или более поздних версий в классическом или режиме ISAPI эти параметры игнорируются.  
  
## <a name="example"></a>Пример  

В следующем примере показано, как настроить поведение ASP.NET на уровне процесса в файле aspnet. config, если ASP.NET размещается в пуле приложений IIS. В примере предполагается, что службы IIS работают в режиме интеграции и что приложение использует .NET Framework 3,5 с пакетом обновления 1 (SP1) или более поздней версии. Такое поведение не происходит в версиях .NET Framework более ранних, чем .NET Framework 3,5 с пакетом обновления 1 (SP1). Значения в примере являются значениями по умолчанию.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Сведения об элементе  
  
|||  
|-|-|  
|Пространство имен||  
|Имя схемы||  
|Файл проверки||  
|Может быть пустым||  
  
## <a name="see-also"></a>См. также

- [\<applicationPool>Элемент (веб-параметры)](applicationpool-element-web-settings.md)

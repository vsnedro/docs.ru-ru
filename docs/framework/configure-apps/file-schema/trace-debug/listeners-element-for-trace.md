---
title: Элемент <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: fd12be1b775d7611ef3f16d23147470313bf9866
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153377"
---
# <a name="listeners-element-for-trace"></a>Элемент \<listeners> для \<trace>
Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения. Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|Добавляет прослушиватель в коллекцию `Listeners`.|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|Очищает коллекцию `Listeners` для трассировки.|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|Удаляет прослушиватель из `Listeners` коллекции.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
  
## <a name="remarks"></a>Примечания  
 <xref:System.Diagnostics.Debug>Классы и <xref:System.Diagnostics.Trace> совместно используют одну и ту же коллекцию **Listeners** . При добавлении объекта прослушивателя в коллекцию в одном из этих классов другой класс использует тот же прослушиватель. Классы прослушивателей, поставляемые с .NET Framework, являются производными от <xref:System.Diagnostics.TraceListener> класса.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать **\<listeners>** элемент для добавления прослушивателей `MyListener` и `MyEventListener` в коллекцию **Listeners** . `MyListener`создает файл с именем `MyListener.log` и записывает выходные данные в файл. `MyEventListener`создает запись в журнале событий.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"
          type="System.Diagnostics.TextWriterTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.TraceListener>
- [Схема параметров трассировки и отладки](index.md)

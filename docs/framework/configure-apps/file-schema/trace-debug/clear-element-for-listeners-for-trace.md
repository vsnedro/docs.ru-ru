---
description: 'Дополнительные сведения о: <clear> Element для <listeners> for <trace>'
title: <clear> Элемент для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 3c1b3816f4ccd0ceb9e9bc0fc6acfd9b6e8ade85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725978"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<clear> Элемент для \<listeners> для \<trace>

Очищает коллекцию `Listeners` для трассировки.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  

 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
|`listeners`|Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения. Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.|  
  
## <a name="remarks"></a>Remarks  

 `<clear>`Элемент удаляет все прослушиватели из `Listeners` коллекции для трассировки. Элемент можно использовать `<clear>` перед использованием `<add>` элемента, чтобы убедиться в отсутствии других активных прослушивателей в коллекции.  
  
 Можно очистить `Listeners` коллекцию программным путем, вызвав <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> метод для <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> Свойства ( `System.Diagnostics.Trace.Listeners.Clear()` ).  
  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.  
  
> [!NOTE]
> `<clear>`Элемент удаляет <xref:System.Diagnostics.DefaultTraceListener> из `Listeners` коллекции, изменяя поведение <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> методов,, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> . Вызов `Assert` метода или `Fail` обычно приводит к отображению окна сообщения. Однако окно сообщения не отображается, если объект <xref:System.Diagnostics.DefaultTraceListener> отсутствует в `Listeners` коллекции.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как использовать `<clear>` элемент перед использованием `<add>` элемента для добавления прослушивателя `console` в `Listeners` коллекцию для трассировки.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [Схема параметров трассировки и отладки](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)

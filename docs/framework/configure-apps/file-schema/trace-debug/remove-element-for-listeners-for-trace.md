---
description: 'Дополнительные сведения о: <remove> Element для <listeners> for <trace>'
title: <remove> Элемент для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 8b863cb535c28f090374e284717d5bf38f22e881
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750602"
---
# <a name="remove-element-for-listeners-for-trace"></a>\<remove> Элемент для \<listeners> для \<trace>

Удаляет прослушиватель из коллекции **Listeners** .  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**name**|Обязательный атрибут.<br /><br /> Имя прослушивателя, удаляемого из коллекции **прослушивателей** .|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`listeners`|Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения. Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`trace`|Настройка службы трассировки ASP.NET.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> При удалении <xref:System.Diagnostics.DefaultTraceListener> из `Listeners` коллекции изменяется поведение <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> методов,, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> . Вызов `Assert` метода или `Fail` обычно приводит к отображению окна сообщения, однако окно сообщения не отображается, если объект <xref:System.Diagnostics.DefaultTraceListener> отсутствует в `Listeners` коллекции.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как удалить прослушиватель трассировки по умолчанию из коллекции **прослушивателей** трассировки.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [Схема параметров трассировки и отладки](index.md)

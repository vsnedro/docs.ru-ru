---
title: Элемент <source>
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: e9c6a06ca9e481ecc2277e1d1ea76a0b99edb158
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173826"
---
# <a name="source-element"></a>Элемент \<source>

Содержит источник трассировки, который инициирует сообщения трассировки.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`name`|Необязательный атрибут.<br /><br /> Задает имя источника трассировки.|  
|`switchName`|Необязательный атрибут.<br /><br /> Задает имя экземпляра переключателя трассировки в приложении. Если параметр не определен в `<switches>` элементе, значение указывает уровень для переключателя.|  
|`switchType`|Необязательный атрибут.<br /><br /> Указывает тип переключателя трассировки. При наличии тип должен быть допустимым именем класса и не может быть пустой строкой.|  
|`extraAttribute`|Необязательный атрибут.<br /><br /> Задает значение для атрибута, зависящего от источника трассировки, определяемого <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> методом для этого источника трассировки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sources`|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
  
## <a name="remarks"></a>Remarks  

 Этот элемент можно использовать в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как с помощью `<source>` элемента добавить источник трассировки `mySource` и задать уровень для коммутатора источника с именем `sourceSwitch` . Добавляется прослушиватель трассировки консоли, который записывает данные трассировки на консоль.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>
  </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Схема параметров трассировки и отладки](index.md)
- [Переключатели трассировки](../../../debug-trace-profile/trace-switches.md)

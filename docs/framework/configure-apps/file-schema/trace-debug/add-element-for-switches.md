---
description: 'Дополнительные сведения о: <add> Element для <switches>'
title: Элемент <add> для <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: fc47a8518aca1e4e6390d9d7eba97d5fb7a7664e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639722"
---
# <a name="add-element-for-switches"></a>Элемент \<add> для \<switches>

Задает уровень, на котором установлен ключ трассировки.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**name**|Обязательный атрибут.<br /><br /> Указывает имя переключателя. Значение этого атрибута соответствует параметру *DisplayName* , переданному в конструктор переключателя.|  
|**value**|Обязательный атрибут.<br /><br /> Задает уровень переключателя.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`switches`|Содержит ключи трассировки и уровень, на котором они установлены.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
  
## <a name="remarks"></a>Remarks  

 Уровень переключателя трассировки можно изменить, поместив его в файл конфигурации. Если параметр имеет значение <xref:System.Diagnostics.BooleanSwitch> , его можно включить и отключить. Если параметр имеет значение <xref:System.Diagnostics.TraceSwitch> , можно назначить для него разные уровни, чтобы указать типы трассировки или сообщения отладки, выданные приложением.  
  
## <a name="example"></a>Пример  

 В следующем примере показано использование **\<add>** элемента для задания `General` переключателя трассировки на <xref:System.Diagnostics.TraceLevel> уровне и включения `Data` логического переключателя трассировки.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [Схема параметров трассировки и отладки](index.md)

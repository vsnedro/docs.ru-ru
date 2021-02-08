---
description: 'Дополнительные сведения о: <legacyCorruptedStateExceptionsPolicy> element'
title: Элемент <legacyCorruptedStateExceptionsPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: 34082c0779b09400a875894359cf7cf501173508
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786958"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a>Элемент \<legacyCorruptedStateExceptionsPolicy>

Указывает, позволяет ли среда CLR использовать управляемый код для перехвата нарушений доступа и других исключений поврежденного состояния.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, что приложение будет перехватывать сбои исключения состояния, такие как нарушения прав доступа.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Приложение не будет перехватывать сбои повреждения состояния, такие как нарушения прав доступа. Это значение по умолчанию.|  
|`true`|Приложение будет перехватывать сбои исключения состояния, такие как нарушения прав доступа.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  

 В платформа .NET Framework версии 3,5 и более ранних версиях среда CLR позволяла управляемому коду перехватывать исключения, которые были вызваны поврежденными состояниями процессов. Нарушение прав доступа — это пример исключения этого типа.  
  
 Начиная с платформа .NET Framework 4 управляемый код больше не перехватывает исключения этих типов в `catch` блоках. Однако это изменение можно переопределить и обрабатывать исключения поврежденного состояния двумя способами:  
  
- Задайте `<legacyCorruptedStateExceptionsPolicy>` `enabled` для атрибута элемента значение `true` . Этот параметр конфигурации применяется процессвиде и влияет на все методы.  
  
 -или-  
  
- Примените <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> атрибут к методу, содержащему `catch` блок исключений.  
  
 Этот элемент конфигурации доступен только в платформа .NET Framework 4 и более поздних версиях.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как указать, что приложение должно вернуться к поведению до платформа .NET Framework 4, и перехватить все сбои исключений состояния.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)

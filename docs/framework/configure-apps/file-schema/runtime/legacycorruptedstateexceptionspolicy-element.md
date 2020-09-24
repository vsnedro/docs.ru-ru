---
title: Элемент <legacyCorruptedStateExceptionsPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: f36e27a1b85cff2ba8c7e838bace37890a5aa760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151211"
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

 В .NET Framework версии 3,5 и более ранних версиях среда CLR позволяла управляемому коду перехватывать исключения, которые были вызваны поврежденными состояниями процессов. Нарушение прав доступа — это пример исключения этого типа.  
  
 Начиная с .NET Framework 4 управляемый код больше не перехватывает исключения этих типов в `catch` блоках. Однако это изменение можно переопределить и обрабатывать исключения поврежденного состояния двумя способами:  
  
- Задайте `<legacyCorruptedStateExceptionsPolicy>` `enabled` для атрибута элемента значение `true` . Этот параметр конфигурации применяется процессвиде и влияет на все методы.  
  
 -или-  
  
- Примените <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> атрибут к методу, содержащему `catch` блок исключений.  
  
 Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как указать, что приложение должно вернуться к поведению до .NET Framework 4, и перехватить все сбои исключений состояния.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)

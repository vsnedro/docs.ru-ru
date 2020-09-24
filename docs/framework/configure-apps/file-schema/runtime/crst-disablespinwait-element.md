---
title: Элемент <Crst_DisableSpinWait>
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 45052d99bb297ac39d058fa405fe57a7c991f738
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151354"
---
# <a name="crst_disablespinwait-element"></a>\<Crst_DisableSpinWait> - элемент

Указывает, следует ли отключать режим ожидания для критической секции, если это не так.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**доступной**|Указывает, отключен ли режим ожидания для критических разделов, если они не включены.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|1|Отключите режим ожидания, если критическая секция не может быть получена.|  
|0|Не отключайте режим ожидания, если критическая секция не может быть получена. Это значение по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о различных параметрах конфигурации среды выполнения.|  
  
## <a name="example"></a>Пример  

В следующем примере отключается ожидание в критических разделах, если это не так.  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)

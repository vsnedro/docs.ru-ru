---
title: Элемент gcAllowVeryLargeObjects
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 1e54b0780ffb5bbe81ab1be2b376ff7a038ee05c
ms.sourcegitcommit: 0273f8845eb1ea8de64086bef2271b4f22182c91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2021
ms.locfileid: "98058133"
---
# <a name="gcallowverylargeobjects-element"></a>Элемент \<gcAllowVeryLargeObjects>

На 64 разрядных платформах позволяет использовать массивы, размер которых превышает 2 гигабайта (ГБ).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<gcAllowVeryLargeObjects enabled="true|false" />  
```  
  
## <a name="attributes"></a>Атрибуты
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, включены ли на 64-разрядных платформах массивы размером более 2 ГБ.|  
  
### <a name="enabled-attribute"></a>Включенный атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Массивы объемом более 2 ГБ не включены. Это значение по умолчанию.|  
|`true`|Массивы объемом более 2 ГБ включены на 64-разрядных платформах.|  
  
## <a name="child-elements"></a>Дочерние элементы  

Отсутствует.  
  
## <a name="parent-elements"></a>Родительские элементы
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Комментарии  

 Использование этого элемента в файле конфигурации приложения позволяет использовать массивы размером более 2 ГБ, но не изменяет другие ограничения на размер объекта или размер массива:  
  
- Максимальное число элементов в массиве — <xref:System.UInt32.MaxValue?displayProperty=nameWithType> .  
  
- Максимальный размер в одном измерении — 2 147 483 591 (0x7FFFFFC7) для массивов байтов и массивов однобайтовых структур, а также 2 146 435 071 (0X7FEFFFFF) для массивов, содержащих другие типы.  
  
- Максимальный размер строк и других объектов, не являющихся массивами, не изменяется.  
  
> [!CAUTION]
> Перед включением этой функции убедитесь, что приложение не включает в себя ненадежный код, который предполагает, что размер всех массивов меньше 2 ГБ. Например, ненадежный код, использующий массивы как буферы, может быть уязвим для переполнения буфера, если он написан на основе предположения, что массивы не будут превышать 2 ГБ.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как включить эту функцию для приложения.  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a>Поддерживается в

.NET Framework 4,5 и более поздних версий

## <a name="see-also"></a>См. также раздел

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)

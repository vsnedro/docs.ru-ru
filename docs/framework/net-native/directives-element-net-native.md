---
title: <Directives> Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 524c30872e218f6428491507bbfb4ca54b6061b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251104"
---
# <a name="directives-element-net-native"></a>\<Directives> Элемент (.NET Native)

Корневой элемент в каждом файле директив среды выполнения для .NET Native.  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`xmlns`|Пространство имен XML. Его значение всегда равно `http://schemas.microsoft.com/netfx/2013/01/metadata` .|  
  
## <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.|  
|[\<Library>](library-element-net-native.md)|Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.|  
  
## <a name="remarks"></a>Примечания  

 Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.  
  
 `<Directives>`Элемент может содержать ноль или один [\<Application>](application-element-net-native.md) элемент, а также ноль, один или несколько [\<Library>](library-element-net-native.md) элементов.  
  
## <a name="see-also"></a>См. также

- [Ссылка на файл конфигурации директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)

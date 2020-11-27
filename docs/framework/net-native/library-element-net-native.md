---
title: <Library> Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
ms.openlocfilehash: aeaa6b1a9c3c4ceebdd0eab3f331a044971398bf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287921"
---
# <a name="library-element-net-native"></a>\<Library> Элемент (.NET Native)

Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения.  
  
 Элемент \<Directives>  
Элемент \<Library>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`Name`|Обязательный атрибут. Задает имя сборки. Дочерние элементы данного элемента `<Library>` определяют политику отражения среды выполнения для типов и членов типов в этой сборке.|  
  
## <a name="name-attribute"></a>Name - атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|*assembly_name*|Простое имя сборки без расширения файла. Этот атрибут соответствует свойству <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>. Например, имя сборки с именем Extensions.dll является «Extensions». Сведения об особой форме имени сборки *assembly_name* с поддержкой условного включения метаданных сборки см. в разделе "Примечания".|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|Применяет политику ко всем типам в определенной сборке.|  
|[\<Namespace>](namespace-element-net-native.md)|Применяет политику ко всем типам в определенном пространстве имен.|  
|[\<Type>](type-element-net-native.md)|Применяет политику для конкретного типа, например, класса или структуры.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Применяет политику к сконструированному универсальному типу. Например, [\<TypeInstantiation>](typeinstantiation-element-net-native.md) элемент можно использовать для определения политики для `List<String>` типа.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|Корневой элемент файла директив среды выполнения.|  
  
## <a name="remarks"></a>Примечания  

 [\<Directives>](directives-element-net-native.md)Элемент может содержать ноль, один или несколько `<Library>` элементов.  
  
 Элемент `<Library>` используется как контейнер для определения программных элементов, метаданные которых требуются во время выполнения. Этот элемент не выражают политики. Во время компиляции средства компилятора осуществляют поиск только в библиотеке, назначенной с помощью элемента `<Library>`, на наличие программных элементов, определенных его дочерними элементами. В отличие от этого, средства компилятора выполняют поиск всех библиотек, including.NET Framework Core Library, для программных элементов, идентифицируемых дочерними элементами [\<Application>](application-element-net-native.md) элемента.  
  
 Директивы `<Library>` могут использоваться условно. Если имя `<Library>` элемента начинается и заканчивается звездочкой ( \* ), `<Library>` директива действует только в том случае, если приложение ссылается на сборку, указанную между звездочками. Например, следующая директива среды выполнения применяется только в том случае, если приложение ссылается на Utilities.dll сборку.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a>См. также

- [\<Application> Элемент](application-element-net-native.md)
- [\<Directives> Элемент](directives-element-net-native.md)
- [Ссылка на файл конфигурации директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)

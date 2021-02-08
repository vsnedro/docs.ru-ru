---
description: 'Дополнительные сведения: взаимодействующие ссылки на объекты'
title: Взаимодействующие ссылки на объекты
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 27c801fb3954c7ea3f821a6588a2229502702989
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802688"
---
# <a name="interoperable-object-references"></a>Взаимодействующие ссылки на объекты

По умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> сериализует объекты по значению. Можно использовать свойство, <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> чтобы указать сериализатору контрактов данных сохранять ссылки на объекты при сериализации объектов.  
  
## <a name="generated-xml"></a>Созданный идентификатор XML  

 В качестве примера рассмотрим следующий объект:  
  
```csharp  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass
{  
}  
```  
  
 Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `false` (по умолчанию), создается следующий код XML:  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `true`, создается следующий код XML:  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 Однако <xref:System.Runtime.Serialization.XsdDataContractExporter> не описывает `id` `ref` атрибуты и в своей схеме, даже если `preserveObjectReferences` свойство имеет значение `true` .  
  
## <a name="using-isreference"></a>Использование IsReference  

 Чтобы создать сведения о ссылке на объект, которые действительны в соответствии со схемой, которая ее описывает, примените <xref:System.Runtime.Serialization.DataContractAttribute> атрибут к типу и установите <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> для флага значение `true` . Следующий пример изменяет класс `X` в предыдущем примере, добавляя `IsReference` :  
  
```csharp
[DataContract(IsReference=true)]
public class X
{  
     SomeClass someInstance = new SomeClass();
     [DataMember]
     public SomeClass A = someInstance;
     [DataMember]
     public SomeClass B = someInstance;
}
  
public class SomeClass
{
}  
````

 Созданный код XML выглядит следующим образом:  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 Использование `IsReference` обеспечивает совместимость для цикла обработки сообщений. Без него, когда тип создается из схемы, выходные данные XML для этого типа не обязательно должны быть совместимы с изначально предполагаемой схемой. Другими словами, несмотря на сериализацию атрибутов `id` и `ref`, первоначальная схема могла предотвратить появление этих атрибутов (или всех атрибутов) в XML. `IsReference`При применении к элементу данных элемент остается распознанным как *ссылочный* при обращении с поддержкой цикла обработки.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>

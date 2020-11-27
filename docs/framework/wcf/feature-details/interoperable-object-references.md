---
title: Взаимодействующие ссылки на объекты
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: bf395c187c46e88406bfb81798c7e359b48255e3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263234"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="69db5-102">Взаимодействующие ссылки на объекты</span><span class="sxs-lookup"><span data-stu-id="69db5-102">Interoperable object references</span></span>

<span data-ttu-id="69db5-103">По умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> сериализует объекты по значению.</span><span class="sxs-lookup"><span data-stu-id="69db5-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="69db5-104">Можно использовать свойство, <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> чтобы указать сериализатору контрактов данных сохранять ссылки на объекты при сериализации объектов.</span><span class="sxs-lookup"><span data-stu-id="69db5-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="69db5-105">Созданный идентификатор XML</span><span class="sxs-lookup"><span data-stu-id="69db5-105">Generated XML</span></span>  

 <span data-ttu-id="69db5-106">В качестве примера рассмотрим следующий объект:</span><span class="sxs-lookup"><span data-stu-id="69db5-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="69db5-107">Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `false` (по умолчанию), создается следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="69db5-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="69db5-108">Если <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> задано как `true`, создается следующий код XML:</span><span class="sxs-lookup"><span data-stu-id="69db5-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="69db5-109">Однако <xref:System.Runtime.Serialization.XsdDataContractExporter> не описывает `id` `ref` атрибуты и в своей схеме, даже если `preserveObjectReferences` свойство имеет значение `true` .</span><span class="sxs-lookup"><span data-stu-id="69db5-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="69db5-110">Использование IsReference</span><span class="sxs-lookup"><span data-stu-id="69db5-110">Using IsReference</span></span>  

 <span data-ttu-id="69db5-111">Чтобы создать сведения о ссылке на объект, которые действительны в соответствии со схемой, которая ее описывает, примените <xref:System.Runtime.Serialization.DataContractAttribute> атрибут к типу и установите <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> для флага значение `true` .</span><span class="sxs-lookup"><span data-stu-id="69db5-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="69db5-112">Следующий пример изменяет класс `X` в предыдущем примере, добавляя `IsReference` :</span><span class="sxs-lookup"><span data-stu-id="69db5-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
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

 <span data-ttu-id="69db5-113">Созданный код XML выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="69db5-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="69db5-114">Использование `IsReference` обеспечивает совместимость для цикла обработки сообщений.</span><span class="sxs-lookup"><span data-stu-id="69db5-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="69db5-115">Без него, когда тип создается из схемы, выходные данные XML для этого типа не обязательно должны быть совместимы с изначально предполагаемой схемой.</span><span class="sxs-lookup"><span data-stu-id="69db5-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="69db5-116">Другими словами, несмотря на сериализацию атрибутов `id` и `ref`, первоначальная схема могла предотвратить появление этих атрибутов (или всех атрибутов) в XML.</span><span class="sxs-lookup"><span data-stu-id="69db5-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="69db5-117">`IsReference`При применении к элементу данных элемент остается распознанным как *ссылочный* при обращении с поддержкой цикла обработки.</span><span class="sxs-lookup"><span data-stu-id="69db5-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69db5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="69db5-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>

---
title: Выборочная сериализация
description: В этой статье показано, как пометить поля с использованием атрибута NonSerialized, который не позволяет сериализовать такие поля.
ms.date: 08/07/2017
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
ms.openlocfilehash: 74113979f0ebe77319ae308c2a669e91d8cb4209
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "84278419"
---
# <a name="selective-serialization"></a><span data-ttu-id="475a2-103">Выборочная сериализация</span><span class="sxs-lookup"><span data-stu-id="475a2-103">Selective serialization</span></span>
<span data-ttu-id="475a2-104">Класс часто содержит поля, которые не должны быть сериализованы.</span><span class="sxs-lookup"><span data-stu-id="475a2-104">A class often contains fields that shouldn't be serialized.</span></span> <span data-ttu-id="475a2-105">Например, рассмотрим класс, содержащий идентификатор потока в переменной-члене.</span><span class="sxs-lookup"><span data-stu-id="475a2-105">For example, assume a class stores a thread ID in a member variable.</span></span> <span data-ttu-id="475a2-106">При десериализации класса поток, в котором хранился идентификатор во время сериализации класса, может уже не использоваться, поэтому сериализация такого значения не имеет смысла.</span><span class="sxs-lookup"><span data-stu-id="475a2-106">When the class is deserialized, the thread stored the ID for when the class was serialized might no longer be running; so serializing this value doesn't make sense.</span></span> <span data-ttu-id="475a2-107">Предотвратить сериализацию переменных-членов можно, маркировав их атрибутом [NonSerialized](xref:System.NonSerializedAttribute) следующим образом.</span><span class="sxs-lookup"><span data-stu-id="475a2-107">You can prevent member variables from being serialized by marking them with the [NonSerialized](xref:System.NonSerializedAttribute) attribute as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

<span data-ttu-id="475a2-108">Для объекта, содержащего важные для обеспечения безопасности данные, следует, если это возможно, запретить сериализацию.</span><span class="sxs-lookup"><span data-stu-id="475a2-108">If possible, make an object that could contain security-sensitive data nonserializable.</span></span> <span data-ttu-id="475a2-109">Если же для данного объекта сериализация необходима, примените к соответствующим полям с важной информацией атрибут `NonSerialized`.</span><span class="sxs-lookup"><span data-stu-id="475a2-109">If the object must be serialized, apply the `NonSerialized` attribute to specific fields that store sensitive data.</span></span> <span data-ttu-id="475a2-110">Учтите, что если не исключить эти поля из сериализации, хранимые в них данные предоставляются любому коду с разрешением сериализации.</span><span class="sxs-lookup"><span data-stu-id="475a2-110">If you don't exclude these fields from serialization, be aware that the data they store are exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="475a2-111">Дополнительные сведения о написании безопасного кода сериализации см. в разделе [Безопасность и сериализация](../../framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="475a2-111">For more information about writing secure serialization code, see [Security and Serialization](../../framework/misc/security-and-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="475a2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="475a2-112">See also</span></span>

- [<span data-ttu-id="475a2-113">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="475a2-113">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="475a2-114">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="475a2-114">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="475a2-115">Безопасность и сериализация</span><span class="sxs-lookup"><span data-stu-id="475a2-115">Security and Serialization</span></span>](../../framework/misc/security-and-serialization.md)

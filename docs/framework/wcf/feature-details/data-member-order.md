---
title: Порядок членов данных
description: Сведения о порядке членов данных в WCF. Приложениям может потребоваться знать или изменить порядок, в котором элементы данных отправляются или ожидаются.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
ms.openlocfilehash: 5c192d3bda65a7364345df4310dccd96cbe04056
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247368"
---
# <a name="data-member-order"></a><span data-ttu-id="0ed0f-104">Порядок членов данных</span><span class="sxs-lookup"><span data-stu-id="0ed0f-104">Data Member Order</span></span>
<span data-ttu-id="0ed0f-105">В некоторых приложениях полезно знать порядок передачи или предполагаемого приема данных от различных элементов данных (например, порядок, в котором данные появляются в сериализованной форме XML).</span><span class="sxs-lookup"><span data-stu-id="0ed0f-105">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="0ed0f-106">Иногда может потребоваться изменить этот порядок.</span><span class="sxs-lookup"><span data-stu-id="0ed0f-106">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="0ed0f-107">В этом разделе рассматриваются правила упорядочивания.</span><span class="sxs-lookup"><span data-stu-id="0ed0f-107">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="0ed0f-108">Основные правила</span><span class="sxs-lookup"><span data-stu-id="0ed0f-108">Basic Rules</span></span>  
 <span data-ttu-id="0ed0f-109">Ниже перечислены основные правила упорядочивания данных.</span><span class="sxs-lookup"><span data-stu-id="0ed0f-109">The basic rules for data ordering include:</span></span>  
  
- <span data-ttu-id="0ed0f-110">Если тип контракта данных является частью иерархии наследования, элементы данных базовых типов всегда идут первыми.</span><span class="sxs-lookup"><span data-stu-id="0ed0f-110">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
- <span data-ttu-id="0ed0f-111">Затем следуют (в алфавитном порядке) элементы данных текущего типа, для которых не задано свойство <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0ed0f-111">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
- <span data-ttu-id="0ed0f-112">Затем следуют любые элементы данных, для которых задано свойство <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0ed0f-112">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="0ed0f-113">Они упорядочиваются сначала по значению свойства `Order` и затем по алфавиту, если существует несколько элементов определенного значения `Order`.</span><span class="sxs-lookup"><span data-stu-id="0ed0f-113">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="0ed0f-114">Значения свойства "Order" могут быть пропущены.</span><span class="sxs-lookup"><span data-stu-id="0ed0f-114">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="0ed0f-115">Алфавитный порядок устанавливается посредством вызова метода <xref:System.String.CompareOrdinal%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ed0f-115">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0ed0f-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="0ed0f-116">Examples</span></span>  
 <span data-ttu-id="0ed0f-117">Рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="0ed0f-117">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="0ed0f-118">Создаваемый XML-код подобен приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="0ed0f-118">The XML produced is similar to the following.</span></span>  
  
```xml  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>
</DerivedType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ed0f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0ed0f-119">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- [<span data-ttu-id="0ed0f-120">Эквивалентность контрактов данных</span><span class="sxs-lookup"><span data-stu-id="0ed0f-120">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="0ed0f-121">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="0ed0f-121">Using Data Contracts</span></span>](using-data-contracts.md)

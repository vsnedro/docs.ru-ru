---
title: Практическое руководство. Создание базового контракта данных для класса или структуры
description: Выполните приведенный ниже пример, чтобы узнать, как создать контракт данных с помощью класса или структуры в WCF с помощью атрибута DataContractAttribute.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: a45fde58795947c3e46fa45750ae1a3faddd8849
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247173"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="082d1-103">Практическое руководство. Создание базового контракта данных для класса или структуры</span><span class="sxs-lookup"><span data-stu-id="082d1-103">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="082d1-104">В этом разделе приведены основные этапы создания контракта данных с использованием класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="082d1-104">This topic shows the basic steps to create a data contract using a class or structure.</span></span> <span data-ttu-id="082d1-105">Дополнительные сведения о контрактах данных и их использовании см. в разделе [использование контрактов данных](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="082d1-105">For more information about data contracts and how they are used, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="082d1-106">Инструкции по созданию службы Basic Windows Communication Foundation (WCF) и клиента см. в [руководстве по начало работы](../getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="082d1-106">For a tutorial that walks through the steps of creating a basic Windows Communication Foundation (WCF) service and client, see the [Getting Started Tutorial](../getting-started-tutorial.md).</span></span> <span data-ttu-id="082d1-107">Рабочий пример приложения, состоящего из базовой службы и клиента, см. в разделе [базовый контракт данных](../samples/basic-data-contract.md).</span><span class="sxs-lookup"><span data-stu-id="082d1-107">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="082d1-108">Создание базового контракта данных для класса или структуры</span><span class="sxs-lookup"><span data-stu-id="082d1-108">To create a basic data contract for a class or structure</span></span>  
  
1. <span data-ttu-id="082d1-109">Объявите, что типы имеют контракт данных, применив атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к классу.</span><span class="sxs-lookup"><span data-stu-id="082d1-109">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="082d1-110">Обратите внимание, что все открытые типы, включая типы без атрибутов, сериализуемы.</span><span class="sxs-lookup"><span data-stu-id="082d1-110">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="082d1-111">Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> выводит контракт данных при отсутствии атрибута <xref:System.Runtime.Serialization.DataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="082d1-111">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> <span data-ttu-id="082d1-112">Дополнительные сведения см. в разделе [сериализуемые типы](serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="082d1-112">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
2. <span data-ttu-id="082d1-113">Определите члены (свойства, поля или события), сериализуемые путем применения атрибута <xref:System.Runtime.Serialization.DataMemberAttribute> к каждому члену.</span><span class="sxs-lookup"><span data-stu-id="082d1-113">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="082d1-114">Эти члены называются членами данных.</span><span class="sxs-lookup"><span data-stu-id="082d1-114">These members are called data members.</span></span> <span data-ttu-id="082d1-115">По умолчанию все открытые типы сериализуемы.</span><span class="sxs-lookup"><span data-stu-id="082d1-115">By default, all public types are serializable.</span></span> <span data-ttu-id="082d1-116">Дополнительные сведения см. в разделе [сериализуемые типы](serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="082d1-116">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="082d1-117">Можно применить атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> к закрытым полям, в результате чего данные будут предоставлены другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="082d1-117">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="082d1-118">Убедитесь, что член не содержит конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="082d1-118">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="082d1-119">Пример</span><span class="sxs-lookup"><span data-stu-id="082d1-119">Example</span></span>  
 <span data-ttu-id="082d1-120">В следующем примере показано создание контракта данных для типа `Person` путем применения атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> к классу и его членам.</span><span class="sxs-lookup"><span data-stu-id="082d1-120">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="082d1-121">См. также</span><span class="sxs-lookup"><span data-stu-id="082d1-121">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="082d1-122">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="082d1-122">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="082d1-123">Учебник по начало работы</span><span class="sxs-lookup"><span data-stu-id="082d1-123">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
- [<span data-ttu-id="082d1-124">Начало работы</span><span class="sxs-lookup"><span data-stu-id="082d1-124">Getting Started</span></span>](../samples/getting-started-sample.md)

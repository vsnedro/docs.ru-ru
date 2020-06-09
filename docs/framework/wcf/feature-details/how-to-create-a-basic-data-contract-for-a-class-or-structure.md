---
title: Практическое руководство. Создание базового контракта данных для класса или структуры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: 0fd7bbea4d6e8d315566aa798ed89a0fd2657f58
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599039"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="a3574-102">Практическое руководство. Создание базового контракта данных для класса или структуры</span><span class="sxs-lookup"><span data-stu-id="a3574-102">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="a3574-103">В этом разделе приведены основные этапы создания контракта данных с использованием класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="a3574-103">This topic shows the basic steps to create a data contract using a class or structure.</span></span> <span data-ttu-id="a3574-104">Дополнительные сведения о контрактах данных и их использовании см. в разделе [использование контрактов данных](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="a3574-104">For more information about data contracts and how they are used, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="a3574-105">Инструкции по созданию службы Basic Windows Communication Foundation (WCF) и клиента см. в [руководстве по начало работы](../getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="a3574-105">For a tutorial that walks through the steps of creating a basic Windows Communication Foundation (WCF) service and client, see the [Getting Started Tutorial](../getting-started-tutorial.md).</span></span> <span data-ttu-id="a3574-106">Рабочий пример приложения, состоящего из базовой службы и клиента, см. в разделе [базовый контракт данных](../samples/basic-data-contract.md).</span><span class="sxs-lookup"><span data-stu-id="a3574-106">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="a3574-107">Создание базового контракта данных для класса или структуры</span><span class="sxs-lookup"><span data-stu-id="a3574-107">To create a basic data contract for a class or structure</span></span>  
  
1. <span data-ttu-id="a3574-108">Объявите, что типы имеют контракт данных, применив атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к классу.</span><span class="sxs-lookup"><span data-stu-id="a3574-108">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="a3574-109">Обратите внимание, что все открытые типы, включая типы без атрибутов, сериализуемы.</span><span class="sxs-lookup"><span data-stu-id="a3574-109">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="a3574-110">Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> выводит контракт данных при отсутствии атрибута <xref:System.Runtime.Serialization.DataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a3574-110">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> <span data-ttu-id="a3574-111">Дополнительные сведения см. в разделе [сериализуемые типы](serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="a3574-111">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
2. <span data-ttu-id="a3574-112">Определите члены (свойства, поля или события), сериализуемые путем применения атрибута <xref:System.Runtime.Serialization.DataMemberAttribute> к каждому члену.</span><span class="sxs-lookup"><span data-stu-id="a3574-112">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="a3574-113">Эти члены называются членами данных.</span><span class="sxs-lookup"><span data-stu-id="a3574-113">These members are called data members.</span></span> <span data-ttu-id="a3574-114">По умолчанию все открытые типы сериализуемы.</span><span class="sxs-lookup"><span data-stu-id="a3574-114">By default, all public types are serializable.</span></span> <span data-ttu-id="a3574-115">Дополнительные сведения см. в разделе [сериализуемые типы](serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="a3574-115">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a3574-116">Можно применить атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> к закрытым полям, в результате чего данные будут предоставлены другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="a3574-116">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="a3574-117">Убедитесь, что член не содержит конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="a3574-117">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3574-118">Пример</span><span class="sxs-lookup"><span data-stu-id="a3574-118">Example</span></span>  
 <span data-ttu-id="a3574-119">В следующем примере показано создание контракта данных для типа `Person` путем применения атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> к классу и его членам.</span><span class="sxs-lookup"><span data-stu-id="a3574-119">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a3574-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a3574-120">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="a3574-121">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="a3574-121">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="a3574-122">Учебник по начало работы</span><span class="sxs-lookup"><span data-stu-id="a3574-122">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
- [<span data-ttu-id="a3574-123">Начало работы</span><span class="sxs-lookup"><span data-stu-id="a3574-123">Getting Started</span></span>](../samples/getting-started-sample.md)

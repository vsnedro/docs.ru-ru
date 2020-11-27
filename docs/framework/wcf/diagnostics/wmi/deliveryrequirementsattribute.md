---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: a70a4ba40b569acc7893b21d796194224dc4ee78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274053"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="bd9df-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="bd9df-102">DeliveryRequirementsAttribute</span></span>

<span data-ttu-id="bd9df-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="bd9df-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd9df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd9df-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bd9df-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bd9df-105">Methods</span></span>  

 <span data-ttu-id="bd9df-106">Класс DeliveryRequirementsAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="bd9df-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bd9df-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="bd9df-107">Properties</span></span>  

 <span data-ttu-id="bd9df-108">Класс DeliveryRequirementsAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="bd9df-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="bd9df-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="bd9df-109">QueuedDeliveryRequirements</span></span>  

 <span data-ttu-id="bd9df-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="bd9df-110">Data type: string</span></span>  
  
 <span data-ttu-id="bd9df-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bd9df-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bd9df-112">Указывает, поддерживает ли привязка для службы контракты.</span><span class="sxs-lookup"><span data-stu-id="bd9df-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="bd9df-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="bd9df-113">RequireOrderedDelivery</span></span>  

 <span data-ttu-id="bd9df-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="bd9df-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="bd9df-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bd9df-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bd9df-116">Указывает, поддерживает ли привязка упорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="bd9df-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="bd9df-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="bd9df-117">TargetContract</span></span>  

 <span data-ttu-id="bd9df-118">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="bd9df-118">Data type: string</span></span>  
  
 <span data-ttu-id="bd9df-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="bd9df-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bd9df-120">Контракт, к которому оно применимо.</span><span class="sxs-lookup"><span data-stu-id="bd9df-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd9df-121">Требования</span><span class="sxs-lookup"><span data-stu-id="bd9df-121">Requirements</span></span>  
  
|<span data-ttu-id="bd9df-122">MOF</span><span class="sxs-lookup"><span data-stu-id="bd9df-122">MOF</span></span>|<span data-ttu-id="bd9df-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bd9df-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bd9df-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="bd9df-124">Namespace</span></span>|<span data-ttu-id="bd9df-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="bd9df-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd9df-126">См. также</span><span class="sxs-lookup"><span data-stu-id="bd9df-126">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>

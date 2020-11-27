---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 867219130fc853f3ba2c1c2f807b1651f6480f13
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273975"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="7a955-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="7a955-102">ServiceTimeoutsBehavior</span></span>

<span data-ttu-id="7a955-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="7a955-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a955-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a955-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7a955-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7a955-105">Methods</span></span>  

 <span data-ttu-id="7a955-106">Класс ServiceTimeoutsBehavior не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="7a955-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7a955-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="7a955-107">Properties</span></span>  

 <span data-ttu-id="7a955-108">Класс ServiceTimeoutsBehavior имеет следующее свойство.</span><span class="sxs-lookup"><span data-stu-id="7a955-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="7a955-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="7a955-109">TransactionTimeout</span></span>  

 <span data-ttu-id="7a955-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="7a955-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="7a955-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7a955-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a955-112">Период времени, в течение которого транзакция должна быть завершена.</span><span class="sxs-lookup"><span data-stu-id="7a955-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a955-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7a955-113">Requirements</span></span>  
  
|<span data-ttu-id="7a955-114">MOF</span><span class="sxs-lookup"><span data-stu-id="7a955-114">MOF</span></span>|<span data-ttu-id="7a955-115">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7a955-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7a955-116">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="7a955-116">Namespace</span></span>|<span data-ttu-id="7a955-117">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="7a955-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a955-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7a955-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

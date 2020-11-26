---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: 6ea121e7901d877d4f0d8f9f5bfd259c2f93696d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239825"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="7fd47-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="7fd47-102">1008 - WorkflowApplicationUnloaded</span></span>

## <a name="properties"></a><span data-ttu-id="7fd47-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="7fd47-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7fd47-104">ID</span><span class="sxs-lookup"><span data-stu-id="7fd47-104">ID</span></span>|<span data-ttu-id="7fd47-105">1008</span><span class="sxs-lookup"><span data-stu-id="7fd47-105">1008</span></span>|  
|<span data-ttu-id="7fd47-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="7fd47-106">Keywords</span></span>|<span data-ttu-id="7fd47-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7fd47-107">WFRuntime</span></span>|  
|<span data-ttu-id="7fd47-108">Level</span><span class="sxs-lookup"><span data-stu-id="7fd47-108">Level</span></span>|<span data-ttu-id="7fd47-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="7fd47-109">Information</span></span>|  
|<span data-ttu-id="7fd47-110">Канал</span><span class="sxs-lookup"><span data-stu-id="7fd47-110">Channel</span></span>|<span data-ttu-id="7fd47-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7fd47-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7fd47-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7fd47-112">Description</span></span>  

 <span data-ttu-id="7fd47-113">Указывает, что приложение рабочего процесса выгружено.</span><span class="sxs-lookup"><span data-stu-id="7fd47-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7fd47-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="7fd47-114">Message</span></span>  

 <span data-ttu-id="7fd47-115">Элемент WorkflowInstance с идентификатором «%1» выгружен из памяти.</span><span class="sxs-lookup"><span data-stu-id="7fd47-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7fd47-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="7fd47-116">Details</span></span>  
  
|<span data-ttu-id="7fd47-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="7fd47-117">Data Item Name</span></span>|<span data-ttu-id="7fd47-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="7fd47-118">Data Item Type</span></span>|<span data-ttu-id="7fd47-119">Описание</span><span class="sxs-lookup"><span data-stu-id="7fd47-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7fd47-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="7fd47-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="7fd47-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7fd47-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="7fd47-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="7fd47-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7fd47-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7fd47-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: be97991be9b61908a23486da0ef255ebfbdc5485
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239956"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="069bd-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="069bd-102">1001 - WorkflowApplicationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="069bd-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="069bd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="069bd-104">ID</span><span class="sxs-lookup"><span data-stu-id="069bd-104">ID</span></span>|<span data-ttu-id="069bd-105">1001</span><span class="sxs-lookup"><span data-stu-id="069bd-105">1001</span></span>|  
|<span data-ttu-id="069bd-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="069bd-106">Keywords</span></span>|<span data-ttu-id="069bd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="069bd-107">WFRuntime</span></span>|  
|<span data-ttu-id="069bd-108">Level</span><span class="sxs-lookup"><span data-stu-id="069bd-108">Level</span></span>|<span data-ttu-id="069bd-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="069bd-109">Information</span></span>|  
|<span data-ttu-id="069bd-110">Канал</span><span class="sxs-lookup"><span data-stu-id="069bd-110">Channel</span></span>|<span data-ttu-id="069bd-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="069bd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="069bd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="069bd-112">Description</span></span>  

 <span data-ttu-id="069bd-113">Указывает, что приложение рабочего процесса завершено в состоянии Closed.</span><span class="sxs-lookup"><span data-stu-id="069bd-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="069bd-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="069bd-114">Message</span></span>  

 <span data-ttu-id="069bd-115">Элемент WorkflowInstance с идентификатором «%1» завершил работу в состоянии Closed.</span><span class="sxs-lookup"><span data-stu-id="069bd-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="069bd-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="069bd-116">Details</span></span>  
  
|<span data-ttu-id="069bd-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="069bd-117">Data Item Name</span></span>|<span data-ttu-id="069bd-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="069bd-118">Data Item Type</span></span>|<span data-ttu-id="069bd-119">Описание</span><span class="sxs-lookup"><span data-stu-id="069bd-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="069bd-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="069bd-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="069bd-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="069bd-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="069bd-122">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="069bd-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="069bd-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="069bd-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

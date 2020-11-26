---
title: 1104 - WorkflowActivityResume
ms.date: 03/30/2017
ms.assetid: 7fe95d1e-34bd-43ca-b92e-587d2d248fff
ms.openlocfilehash: 2a9c40e2c403d43dc980af116e4b6e98b3b2090b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243564"
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="5bd6f-102">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="5bd6f-102">1104 - WorkflowActivityResume</span></span>

## <a name="properties"></a><span data-ttu-id="5bd6f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="5bd6f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5bd6f-104">ID</span><span class="sxs-lookup"><span data-stu-id="5bd6f-104">ID</span></span>|<span data-ttu-id="5bd6f-105">1104</span><span class="sxs-lookup"><span data-stu-id="5bd6f-105">1104</span></span>|  
|<span data-ttu-id="5bd6f-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="5bd6f-106">Keywords</span></span>|<span data-ttu-id="5bd6f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5bd6f-107">WFRuntime</span></span>|  
|<span data-ttu-id="5bd6f-108">Level</span><span class="sxs-lookup"><span data-stu-id="5bd6f-108">Level</span></span>|<span data-ttu-id="5bd6f-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="5bd6f-109">Information</span></span>|  
|<span data-ttu-id="5bd6f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="5bd6f-110">Channel</span></span>|<span data-ttu-id="5bd6f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5bd6f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5bd6f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5bd6f-112">Description</span></span>  

 <span data-ttu-id="5bd6f-113">Указывает, что действие рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="5bd6f-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5bd6f-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5bd6f-114">Message</span></span>  

 <span data-ttu-id="5bd6f-115">Элемент WorkflowInstance с идентификатором «%1», действие E2E</span><span class="sxs-lookup"><span data-stu-id="5bd6f-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="5bd6f-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="5bd6f-116">Details</span></span>  
  
|<span data-ttu-id="5bd6f-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="5bd6f-117">Data Item Name</span></span>|<span data-ttu-id="5bd6f-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="5bd6f-118">Data Item Type</span></span>|<span data-ttu-id="5bd6f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5bd6f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5bd6f-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="5bd6f-120">WorkflowInstanceId</span></span>|<span data-ttu-id="5bd6f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5bd6f-121">xs:string</span></span>|<span data-ttu-id="5bd6f-122">Идентификатор экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="5bd6f-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="5bd6f-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="5bd6f-123">AppDomain</span></span>|<span data-ttu-id="5bd6f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5bd6f-124">xs:string</span></span>|<span data-ttu-id="5bd6f-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5bd6f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

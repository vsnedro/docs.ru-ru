---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: e7c92dcc9ce472c50af6f0aa26c59f55d62fbb9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239943"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="bbcc0-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="bbcc0-102">1002 - WorkflowApplicationTerminated</span></span>

## <a name="properties"></a><span data-ttu-id="bbcc0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="bbcc0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bbcc0-104">ID</span><span class="sxs-lookup"><span data-stu-id="bbcc0-104">ID</span></span>|<span data-ttu-id="bbcc0-105">1002</span><span class="sxs-lookup"><span data-stu-id="bbcc0-105">1002</span></span>|  
|<span data-ttu-id="bbcc0-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="bbcc0-106">Keywords</span></span>|<span data-ttu-id="bbcc0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bbcc0-107">WFRuntime</span></span>|  
|<span data-ttu-id="bbcc0-108">Level</span><span class="sxs-lookup"><span data-stu-id="bbcc0-108">Level</span></span>|<span data-ttu-id="bbcc0-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="bbcc0-109">Information</span></span>|  
|<span data-ttu-id="bbcc0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="bbcc0-110">Channel</span></span>|<span data-ttu-id="bbcc0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bbcc0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bbcc0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bbcc0-112">Description</span></span>  

 <span data-ttu-id="bbcc0-113">Указывает, что приложение рабочего процесса было остановлено в состоянии Faulted с исключением.</span><span class="sxs-lookup"><span data-stu-id="bbcc0-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bbcc0-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="bbcc0-114">Message</span></span>  

 <span data-ttu-id="bbcc0-115">WorkflowApplication с идентификатором «%1» остановлено.</span><span class="sxs-lookup"><span data-stu-id="bbcc0-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="bbcc0-116">Был прерван в состоянии сбоя с исключением.</span><span class="sxs-lookup"><span data-stu-id="bbcc0-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bbcc0-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="bbcc0-117">Details</span></span>  
  
|<span data-ttu-id="bbcc0-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="bbcc0-118">Data Item Name</span></span>|<span data-ttu-id="bbcc0-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="bbcc0-119">Data Item Type</span></span>|<span data-ttu-id="bbcc0-120">Описание</span><span class="sxs-lookup"><span data-stu-id="bbcc0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bbcc0-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="bbcc0-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="bbcc0-122">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="bbcc0-122">The workflow application id</span></span>|  
|<span data-ttu-id="bbcc0-123">Исключение</span><span class="sxs-lookup"><span data-stu-id="bbcc0-123">Exception</span></span>|`xs:string`|<span data-ttu-id="bbcc0-124">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="bbcc0-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="bbcc0-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="bbcc0-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bbcc0-126">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bbcc0-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

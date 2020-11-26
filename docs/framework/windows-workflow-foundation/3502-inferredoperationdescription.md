---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 05278067e3f86612ee4aafbe7d5eb66dc934cb85
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242114"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="590c3-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="590c3-102">3502 - InferredOperationDescription</span></span>

## <a name="properties"></a><span data-ttu-id="590c3-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="590c3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="590c3-104">ID</span><span class="sxs-lookup"><span data-stu-id="590c3-104">ID</span></span>|<span data-ttu-id="590c3-105">3502</span><span class="sxs-lookup"><span data-stu-id="590c3-105">3502</span></span>|  
|<span data-ttu-id="590c3-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="590c3-106">Keywords</span></span>|<span data-ttu-id="590c3-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="590c3-107">WFServices</span></span>|  
|<span data-ttu-id="590c3-108">Level</span><span class="sxs-lookup"><span data-stu-id="590c3-108">Level</span></span>|<span data-ttu-id="590c3-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="590c3-109">Information</span></span>|  
|<span data-ttu-id="590c3-110">Канал</span><span class="sxs-lookup"><span data-stu-id="590c3-110">Channel</span></span>|<span data-ttu-id="590c3-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="590c3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="590c3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="590c3-112">Description</span></span>  

 <span data-ttu-id="590c3-113">Указывает, что описание операции OperationDescription выведено из WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="590c3-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="590c3-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="590c3-114">Message</span></span>  

 <span data-ttu-id="590c3-115">Описание OperationDescription с параметром Name=«%1» в контракте «%2» было выведено из WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="590c3-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="590c3-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="590c3-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="590c3-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="590c3-117">Details</span></span>  
  
|<span data-ttu-id="590c3-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="590c3-118">Data Item Name</span></span>|<span data-ttu-id="590c3-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="590c3-119">Data Item Type</span></span>|<span data-ttu-id="590c3-120">Описание</span><span class="sxs-lookup"><span data-stu-id="590c3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="590c3-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="590c3-121">OperationName</span></span>|<span data-ttu-id="590c3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="590c3-122">xs:string</span></span>|<span data-ttu-id="590c3-123">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="590c3-123">The name of the operation.</span></span>|  
|<span data-ttu-id="590c3-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="590c3-124">ContractName</span></span>|<span data-ttu-id="590c3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="590c3-125">xs:string</span></span>|<span data-ttu-id="590c3-126">Имя контракта.</span><span class="sxs-lookup"><span data-stu-id="590c3-126">The name of the contract.</span></span>|  
|<span data-ttu-id="590c3-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="590c3-127">IsOneWay</span></span>|<span data-ttu-id="590c3-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="590c3-128">xs:string</span></span>|<span data-ttu-id="590c3-129">Логическое значение True или False, указывающее, является ли контракт односторонним.</span><span class="sxs-lookup"><span data-stu-id="590c3-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="590c3-130">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="590c3-130">AppDomain</span></span>|<span data-ttu-id="590c3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="590c3-131">xs:string</span></span>|<span data-ttu-id="590c3-132">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="590c3-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

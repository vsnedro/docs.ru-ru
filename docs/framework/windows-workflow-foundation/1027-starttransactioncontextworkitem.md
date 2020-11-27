---
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: cb5671ce7a30a7096104ba0ca6c4f36bed6b93f9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275236"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="f0208-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="f0208-102">1027 - StartTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="f0208-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f0208-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0208-104">ID</span><span class="sxs-lookup"><span data-stu-id="f0208-104">ID</span></span>|<span data-ttu-id="f0208-105">1027</span><span class="sxs-lookup"><span data-stu-id="f0208-105">1027</span></span>|  
|<span data-ttu-id="f0208-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="f0208-106">Keywords</span></span>|<span data-ttu-id="f0208-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f0208-107">WFRuntime</span></span>|  
|<span data-ttu-id="f0208-108">Level</span><span class="sxs-lookup"><span data-stu-id="f0208-108">Level</span></span>|<span data-ttu-id="f0208-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="f0208-109">Verbose</span></span>|  
|<span data-ttu-id="f0208-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f0208-110">Channel</span></span>|<span data-ttu-id="f0208-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f0208-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f0208-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f0208-112">Description</span></span>  

 <span data-ttu-id="f0208-113">Указывает, что начинается выполнение TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="f0208-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f0208-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f0208-114">Message</span></span>  

 <span data-ttu-id="f0208-115">Начато выполнение TransactionContextWorkItem для родительского действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="f0208-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f0208-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="f0208-116">Details</span></span>  
  
|<span data-ttu-id="f0208-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f0208-117">Data Item Name</span></span>|<span data-ttu-id="f0208-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f0208-118">Data Item Type</span></span>|<span data-ttu-id="f0208-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f0208-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f0208-120">Действие</span><span class="sxs-lookup"><span data-stu-id="f0208-120">Activity</span></span>|<span data-ttu-id="f0208-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0208-121">xs:string</span></span>|<span data-ttu-id="f0208-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="f0208-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f0208-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f0208-123">DisplayName</span></span>|<span data-ttu-id="f0208-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0208-124">xs:string</span></span>|<span data-ttu-id="f0208-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="f0208-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f0208-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f0208-126">InstanceId</span></span>|<span data-ttu-id="f0208-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0208-127">xs:string</span></span>|<span data-ttu-id="f0208-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="f0208-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f0208-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="f0208-129">AppDomain</span></span>|<span data-ttu-id="f0208-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0208-130">xs:string</span></span>|<span data-ttu-id="f0208-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f0208-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

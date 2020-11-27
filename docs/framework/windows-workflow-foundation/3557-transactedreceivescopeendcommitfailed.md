---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 4a4979047481687ef0d5c9d5891dec8f2826beed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263663"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="85b6b-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="85b6b-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>

## <a name="properties"></a><span data-ttu-id="85b6b-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="85b6b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85b6b-104">ID</span><span class="sxs-lookup"><span data-stu-id="85b6b-104">ID</span></span>|<span data-ttu-id="85b6b-105">3557</span><span class="sxs-lookup"><span data-stu-id="85b6b-105">3557</span></span>|  
|<span data-ttu-id="85b6b-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="85b6b-106">Keywords</span></span>|<span data-ttu-id="85b6b-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="85b6b-107">WFServices</span></span>|  
|<span data-ttu-id="85b6b-108">Level</span><span class="sxs-lookup"><span data-stu-id="85b6b-108">Level</span></span>|<span data-ttu-id="85b6b-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="85b6b-109">Information</span></span>|  
|<span data-ttu-id="85b6b-110">Канал</span><span class="sxs-lookup"><span data-stu-id="85b6b-110">Channel</span></span>|<span data-ttu-id="85b6b-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="85b6b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="85b6b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="85b6b-112">Description</span></span>  

 <span data-ttu-id="85b6b-113">Указывает, что вызов к EndCommit в CommittableTransaction привел к созданию исключения TransactionException.</span><span class="sxs-lookup"><span data-stu-id="85b6b-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="85b6b-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="85b6b-114">Message</span></span>  

 <span data-ttu-id="85b6b-115">Вызов EndCommit для CommittableTransaction с id = «%1» привел к созданию исключения TransactionException со следующим сообщением: «%2».</span><span class="sxs-lookup"><span data-stu-id="85b6b-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="85b6b-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="85b6b-116">Details</span></span>  
  
|<span data-ttu-id="85b6b-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="85b6b-117">Data Item Name</span></span>|<span data-ttu-id="85b6b-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="85b6b-118">Data Item Type</span></span>|<span data-ttu-id="85b6b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="85b6b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="85b6b-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="85b6b-120">TransactionId</span></span>|<span data-ttu-id="85b6b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="85b6b-121">xs:string</span></span>|<span data-ttu-id="85b6b-122">Идентификатор CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="85b6b-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="85b6b-123">Исключение</span><span class="sxs-lookup"><span data-stu-id="85b6b-123">Exception</span></span>|<span data-ttu-id="85b6b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="85b6b-124">xs:string</span></span>|<span data-ttu-id="85b6b-125">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="85b6b-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="85b6b-126">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="85b6b-126">AppDomain</span></span>|<span data-ttu-id="85b6b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="85b6b-127">xs:string</span></span>|<span data-ttu-id="85b6b-128">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="85b6b-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

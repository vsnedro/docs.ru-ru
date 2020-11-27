---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: 088754cb15c2e55faa1d43a1da1c79ddcddd69f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280420"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="a788f-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="a788f-102">4208 - RetryingSqlCommandDueToSqlError</span></span>

## <a name="properties"></a><span data-ttu-id="a788f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a788f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a788f-104">ID</span><span class="sxs-lookup"><span data-stu-id="a788f-104">ID</span></span>|<span data-ttu-id="a788f-105">4208</span><span class="sxs-lookup"><span data-stu-id="a788f-105">4208</span></span>|  
|<span data-ttu-id="a788f-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="a788f-106">Keywords</span></span>|<span data-ttu-id="a788f-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="a788f-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="a788f-108">Level</span><span class="sxs-lookup"><span data-stu-id="a788f-108">Level</span></span>|<span data-ttu-id="a788f-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="a788f-109">Information</span></span>|  
|<span data-ttu-id="a788f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a788f-110">Channel</span></span>|<span data-ttu-id="a788f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a788f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a788f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a788f-112">Description</span></span>  

 <span data-ttu-id="a788f-113">Указывает, что поставщик SQL повторяет команду SQL из-за ошибки SQL.</span><span class="sxs-lookup"><span data-stu-id="a788f-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a788f-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a788f-114">Message</span></span>  

 <span data-ttu-id="a788f-115">Выполняется повтор команды SQL из-за ошибки SQL с номером %1.</span><span class="sxs-lookup"><span data-stu-id="a788f-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a788f-116">Сведения</span><span class="sxs-lookup"><span data-stu-id="a788f-116">Details</span></span>  
  
|<span data-ttu-id="a788f-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a788f-117">Data Item Name</span></span>|<span data-ttu-id="a788f-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a788f-118">Data Item Type</span></span>|<span data-ttu-id="a788f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a788f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a788f-120">Номер ошибки</span><span class="sxs-lookup"><span data-stu-id="a788f-120">ErrorNumber</span></span>|<span data-ttu-id="a788f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a788f-121">xs:string</span></span>|<span data-ttu-id="a788f-122">Номер ошибки SQL.</span><span class="sxs-lookup"><span data-stu-id="a788f-122">The SQL error number.</span></span>|  
|<span data-ttu-id="a788f-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="a788f-123">AppDomain</span></span>|<span data-ttu-id="a788f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a788f-124">xs:string</span></span>|<span data-ttu-id="a788f-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a788f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

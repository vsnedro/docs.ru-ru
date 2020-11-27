---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 23262427c3da730eaf930a8b483c7c4d4ec3a3a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289845"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="270a7-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="270a7-102">3508 - TrackingProfileNotFound</span></span>

## <a name="properties"></a><span data-ttu-id="270a7-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="270a7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="270a7-104">ID</span><span class="sxs-lookup"><span data-stu-id="270a7-104">ID</span></span>|<span data-ttu-id="270a7-105">3508</span><span class="sxs-lookup"><span data-stu-id="270a7-105">3508</span></span>|  
|<span data-ttu-id="270a7-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="270a7-106">Keywords</span></span>|<span data-ttu-id="270a7-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="270a7-107">WFServices</span></span>|  
|<span data-ttu-id="270a7-108">Level</span><span class="sxs-lookup"><span data-stu-id="270a7-108">Level</span></span>|<span data-ttu-id="270a7-109">Подробный</span><span class="sxs-lookup"><span data-stu-id="270a7-109">Verbose</span></span>|  
|<span data-ttu-id="270a7-110">Канал</span><span class="sxs-lookup"><span data-stu-id="270a7-110">Channel</span></span>|<span data-ttu-id="270a7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="270a7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="270a7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="270a7-112">Description</span></span>  

 <span data-ttu-id="270a7-113">Указывает, что либо профиль TrackingProfile не найден в файле конфигурации, либо обнаружено несоответствие ActivityDefinitionId профилю.</span><span class="sxs-lookup"><span data-stu-id="270a7-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="270a7-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="270a7-114">Message</span></span>  

 <span data-ttu-id="270a7-115">Не найден TrackingProfile «%1» для ActivityDefinitionId «%2».</span><span class="sxs-lookup"><span data-stu-id="270a7-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="270a7-116">Профиль TrackingProfile не найден в файле конфигурации, или обнаружено несоответствие ActivityDefinitionId.</span><span class="sxs-lookup"><span data-stu-id="270a7-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="270a7-117">Сведения</span><span class="sxs-lookup"><span data-stu-id="270a7-117">Details</span></span>  
  
|<span data-ttu-id="270a7-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="270a7-118">Data Item Name</span></span>|<span data-ttu-id="270a7-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="270a7-119">Data Item Type</span></span>|<span data-ttu-id="270a7-120">Описание</span><span class="sxs-lookup"><span data-stu-id="270a7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="270a7-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="270a7-121">TrackingProfile</span></span>|<span data-ttu-id="270a7-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="270a7-122">xs:string</span></span>|<span data-ttu-id="270a7-123">Имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="270a7-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="270a7-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="270a7-124">ActivityDefinitionId</span></span>|<span data-ttu-id="270a7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="270a7-125">xs:string</span></span>|<span data-ttu-id="270a7-126">Идентификатор определения действия.</span><span class="sxs-lookup"><span data-stu-id="270a7-126">The activity definition id.</span></span>|  
|<span data-ttu-id="270a7-127">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="270a7-127">AppDomain</span></span>|<span data-ttu-id="270a7-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="270a7-128">xs:string</span></span>|<span data-ttu-id="270a7-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="270a7-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

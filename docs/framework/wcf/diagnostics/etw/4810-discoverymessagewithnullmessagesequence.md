---
title: 4810 - DiscoveryMessageWithNullMessageSequence
ms.date: 03/30/2017
ms.assetid: aa70573e-8a76-486a-9616-ccca8c7008b6
ms.openlocfilehash: 183fb9b611855839a2fe5234f7ffce0962a775d8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267430"
---
# <a name="4810---discoverymessagewithnullmessagesequence"></a><span data-ttu-id="2235b-102">4810 - DiscoveryMessageWithNullMessageSequence</span><span class="sxs-lookup"><span data-stu-id="2235b-102">4810 - DiscoveryMessageWithNullMessageSequence</span></span>

## <a name="properties"></a><span data-ttu-id="2235b-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2235b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2235b-104">ID</span><span class="sxs-lookup"><span data-stu-id="2235b-104">ID</span></span>|<span data-ttu-id="2235b-105">4810</span><span class="sxs-lookup"><span data-stu-id="2235b-105">4810</span></span>|  
|<span data-ttu-id="2235b-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="2235b-106">Keywords</span></span>|<span data-ttu-id="2235b-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="2235b-107">Discovery</span></span>|  
|<span data-ttu-id="2235b-108">Level</span><span class="sxs-lookup"><span data-stu-id="2235b-108">Level</span></span>|<span data-ttu-id="2235b-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="2235b-109">Warning</span></span>|  
|<span data-ttu-id="2235b-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2235b-110">Channel</span></span>|<span data-ttu-id="2235b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2235b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2235b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2235b-112">Description</span></span>  

 <span data-ttu-id="2235b-113">Это событие создается при отбрасывании клиентом DiscoveryClient сообщения запроса обнаружения из-за отсутствия в нем свойства DiscoveryMessageSequence.</span><span class="sxs-lookup"><span data-stu-id="2235b-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because it did not have the DiscoveryMessageSequence property.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2235b-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2235b-114">Message</span></span>  

 <span data-ttu-id="2235b-115">Сообщение %1 с messageId="%2" удалено клиентом DiscoveryClient, поскольку в нем отсутствует свойство DiscoveryMessageSequence.</span><span class="sxs-lookup"><span data-stu-id="2235b-115">A %1 message with messageId='%2' was dropped by the DiscoveryClient because it did not have the DiscoveryMessageSequence property.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2235b-116">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2235b-116">Details</span></span>

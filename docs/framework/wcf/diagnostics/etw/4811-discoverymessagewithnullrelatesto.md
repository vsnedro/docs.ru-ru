---
title: 4811 - DiscoveryMessageWithNullRelatesTo
ms.date: 03/30/2017
ms.assetid: dab901e8-a2b3-41c1-a76b-bcd8b3c7c29a
ms.openlocfilehash: 2f2eeee50ed6925ab1f3762dbdd898c375756b7e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267432"
---
# <a name="4811---discoverymessagewithnullrelatesto"></a><span data-ttu-id="2b8bb-102">4811 - DiscoveryMessageWithNullRelatesTo</span><span class="sxs-lookup"><span data-stu-id="2b8bb-102">4811 - DiscoveryMessageWithNullRelatesTo</span></span>

## <a name="properties"></a><span data-ttu-id="2b8bb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2b8bb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b8bb-104">ID</span><span class="sxs-lookup"><span data-stu-id="2b8bb-104">ID</span></span>|<span data-ttu-id="2b8bb-105">4811</span><span class="sxs-lookup"><span data-stu-id="2b8bb-105">4811</span></span>|  
|<span data-ttu-id="2b8bb-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="2b8bb-106">Keywords</span></span>|<span data-ttu-id="2b8bb-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="2b8bb-107">Discovery</span></span>|  
|<span data-ttu-id="2b8bb-108">Level</span><span class="sxs-lookup"><span data-stu-id="2b8bb-108">Level</span></span>|<span data-ttu-id="2b8bb-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="2b8bb-109">Warning</span></span>|  
|<span data-ttu-id="2b8bb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2b8bb-110">Channel</span></span>|<span data-ttu-id="2b8bb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2b8bb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2b8bb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2b8bb-112">Description</span></span>  

 <span data-ttu-id="2b8bb-113">Это событие создается при отбрасывании сообщения обнаружения объектом DiscoveryClient из-за отсутствия в заголовке сообщения обязательного свойства RelatesTo.</span><span class="sxs-lookup"><span data-stu-id="2b8bb-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because the message header did not contain the required RelatesTo property.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2b8bb-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2b8bb-114">Message</span></span>  

 <span data-ttu-id="2b8bb-115">Сообщение %1 с messageId="%2" удалено клиентом DiscoveryClient, поскольку заголовок сообщения не содержит обязательного свойства RelatesTo.</span><span class="sxs-lookup"><span data-stu-id="2b8bb-115">A %1 message with messageId='%2' was dropped by the DiscoveryClient because the message header did not contain the required RelatesTo property.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2b8bb-116">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2b8bb-116">Details</span></span>

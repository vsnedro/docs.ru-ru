---
title: 4812 - DiscoveryMessageWithNullReplyTo
ms.date: 03/30/2017
ms.assetid: a40e6b7e-c2a6-4186-b1d6-c9560f24a959
ms.openlocfilehash: f933f8668ccb21c9b509db6dc2b56726ba6c78bf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285997"
---
# <a name="4812---discoverymessagewithnullreplyto"></a><span data-ttu-id="7a520-102">4812 - DiscoveryMessageWithNullReplyTo</span><span class="sxs-lookup"><span data-stu-id="7a520-102">4812 - DiscoveryMessageWithNullReplyTo</span></span>

## <a name="properties"></a><span data-ttu-id="7a520-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="7a520-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7a520-104">ID</span><span class="sxs-lookup"><span data-stu-id="7a520-104">ID</span></span>|<span data-ttu-id="7a520-105">4812</span><span class="sxs-lookup"><span data-stu-id="7a520-105">4812</span></span>|  
|<span data-ttu-id="7a520-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="7a520-106">Keywords</span></span>|<span data-ttu-id="7a520-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="7a520-107">Discovery</span></span>|  
|<span data-ttu-id="7a520-108">Level</span><span class="sxs-lookup"><span data-stu-id="7a520-108">Level</span></span>|<span data-ttu-id="7a520-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="7a520-109">Warning</span></span>|  
|<span data-ttu-id="7a520-110">Канал</span><span class="sxs-lookup"><span data-stu-id="7a520-110">Channel</span></span>|<span data-ttu-id="7a520-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7a520-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7a520-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7a520-112">Description</span></span>  

 <span data-ttu-id="7a520-113">Это событие создается при удалении клиентом DiscoveryClient сообщения запроса обнаружения из-за отсутствия в нем адреса ReplyTo.</span><span class="sxs-lookup"><span data-stu-id="7a520-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because it did not have a ReplyTo address.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7a520-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="7a520-114">Message</span></span>  

 <span data-ttu-id="7a520-115">Сообщение запроса обнаружения с messageId="%1" удалено, поскольку отсутствует адрес ReplyTo.</span><span class="sxs-lookup"><span data-stu-id="7a520-115">A discovery request message with messageId='%1' was dropped because it did not have a ReplyTo address.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7a520-116">Подробнее</span><span class="sxs-lookup"><span data-stu-id="7a520-116">Details</span></span>

---
title: Одноранговая сеть
ms.date: 03/30/2017
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
ms.openlocfilehash: 1729b7defd6a9145a1cff150b51c2117e22e3af0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554297"
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="909d3-102">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="909d3-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="909d3-103">Одноранговый канал — это многокомпонентная (P2P) технология связи в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="909d3-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="909d3-104">Она предоставляет надежный и масштабируемый одноранговый канал связи на основе обмена сообщениями для разработчиков приложений.</span><span class="sxs-lookup"><span data-stu-id="909d3-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="909d3-105">Одним из типичных примеров многопользовательского приложения, в котором могут использоваться преимущества однорангового канала, является приложение для совместной работы, такое как разговор, в котором группа людей общается друг с другом по одноранговой сети без использования серверов.</span><span class="sxs-lookup"><span data-stu-id="909d3-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="909d3-106">Одноранговый канал поддерживает одноранговую совместную работу, распространение содержимого, балансировку нагрузки и распределенную обработку сценариев потребителя и предприятия.</span><span class="sxs-lookup"><span data-stu-id="909d3-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="909d3-107">Одноранговый канал включен по умолчанию в Windows Vista, как и в случае с WCF.</span><span class="sxs-lookup"><span data-stu-id="909d3-107">Peer Channel is enabled by default on Windows Vista, as is all of WCF.</span></span> <span data-ttu-id="909d3-108">Для того чтобы получить доступ к классам однорангового канала, необходимо добавить в проект ссылки на System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="909d3-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="909d3-109">В следующих разделах содержится информация об одноранговых сетях и использовании классов одноранговых каналов для создания сетевых приложений с поддержкой одноранговых объектов.</span><span class="sxs-lookup"><span data-stu-id="909d3-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="909d3-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="909d3-110">In This Section</span></span>  
 <span data-ttu-id="909d3-111">[Сценарии одноранговых каналов](peer-channel-scenarios.md). описывает сценарии разработки, поддерживаемые интерфейсами API однорангового канала, такими как обмен сообщениями публикации и подписки, совместная работа, распределенная обработка и игры.</span><span class="sxs-lookup"><span data-stu-id="909d3-111">[Peer Channel Scenarios](peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="909d3-112">[Основные понятия одноранговых каналов](peer-channel-concepts.md): описывает одноранговые сети, одноранговые узлы, Безопасность одноранговых каналов и одноранговые разрешения.</span><span class="sxs-lookup"><span data-stu-id="909d3-112">[Peer Channel Concepts](peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="909d3-113">[Создание приложения однорангового канала](building-a-peer-channel-application.md): предоставляет рекомендации по разработке приложений одноранговых каналов.</span><span class="sxs-lookup"><span data-stu-id="909d3-113">[Building a Peer Channel Application](building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="909d3-114">Примеры кода одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="909d3-114">Peer Channel Code Examples</span></span>  
 <span data-ttu-id="909d3-115">[Пользовательский распознаватель для одноранговых каналов](/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="909d3-115">[Peer Channel Custom Peer Resolver](/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span></span>  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="909d3-116">Блог команды разработчиков одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="909d3-116">Peer Channel Team blog</span></span>  
 [<span data-ttu-id="909d3-117">Блог группы одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="909d3-117">Peer Channel Team Blog</span></span>](/archive/blogs/peerchan/)

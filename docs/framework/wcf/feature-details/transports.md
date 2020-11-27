---
title: Транспорты в Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 8623b788b848867f25836a657b07349dd50c2780
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251689"
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="e394f-102">Транспорты в Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e394f-102">Transports in Windows Communication Foundation</span></span>

<span data-ttu-id="e394f-103">Транспортный уровень является самым нижним уровнем стека каналов.</span><span class="sxs-lookup"><span data-stu-id="e394f-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="e394f-104">Основными транспортами, используемыми в Windows Communication Foundation (WCF), являются HTTP, HTTPS, TCP и именованные каналы.</span><span class="sxs-lookup"><span data-stu-id="e394f-104">The main transports used in Windows Communication Foundation (WCF) are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="e394f-105">В подразделах данного раздела рассматриваются выбор типа транспорта среди названных выше типов, настройка транспорта и задание свойств настройки.</span><span class="sxs-lookup"><span data-stu-id="e394f-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="e394f-106">В состав WCF входят дополнительные транспорты.</span><span class="sxs-lookup"><span data-stu-id="e394f-106">WCF includes additional transports.</span></span> <span data-ttu-id="e394f-107">Дополнительные сведения о службе очередей сообщений (MSMQ) см. в статье [очереди и надежные сеансы](queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="e394f-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="e394f-108">Дополнительные сведения о одноранговом транспорте см. в разделе одноранговая [сеть](peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="e394f-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e394f-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="e394f-109">In This Section</span></span>  

 [<span data-ttu-id="e394f-110">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="e394f-110">Choosing a Transport</span></span>](choosing-a-transport.md)  
 <span data-ttu-id="e394f-111">Описываются три основных типа транспорта и рассматриваются вопросы выбора транспорта.</span><span class="sxs-lookup"><span data-stu-id="e394f-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="e394f-112">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="e394f-112">Choosing a Message Encoder</span></span>](choosing-a-message-encoder.md)  
 <span data-ttu-id="e394f-113">Описываются факторы, которые необходимо принять во внимание при выборе элемента привязки для кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="e394f-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="e394f-114">Потоковая передача сообщений</span><span class="sxs-lookup"><span data-stu-id="e394f-114">Streaming Message Transfer</span></span>](streaming-message-transfer.md)  
 <span data-ttu-id="e394f-115">Описывается настройка транспортного уровня для выполнения потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="e394f-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="e394f-116">Настройка HTTP и HTTPS</span><span class="sxs-lookup"><span data-stu-id="e394f-116">Configuring HTTP and HTTPS</span></span>](configuring-http-and-https.md)  
 <span data-ttu-id="e394f-117">Описывается настройка элементов привязки транспорта HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e394f-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="e394f-118">Практическое руководство. Как заменить URL-резервирование WCF на ограниченное резервирование</span><span class="sxs-lookup"><span data-stu-id="e394f-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="e394f-119">Описывает, как использовать ограниченные резервирования ВКФУРЛ.</span><span class="sxs-lookup"><span data-stu-id="e394f-119">Describes how to use WCFURL restricted reservations.</span></span>  
  
 [<span data-ttu-id="e394f-120">Квоты транспорта</span><span class="sxs-lookup"><span data-stu-id="e394f-120">Transport Quotas</span></span>](transport-quotas.md)  
 <span data-ttu-id="e394f-121">Рассматриваются вопросы задания квот, доступных на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="e394f-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="e394f-122">Работа со средствами NAT и брандмауэрами</span><span class="sxs-lookup"><span data-stu-id="e394f-122">Working with NATs and Firewalls</span></span>](working-with-nats-and-firewalls.md)  
 <span data-ttu-id="e394f-123">Описывается настройка транспортного уровня при отправке или получении сообщений за брандмауэром или при использовании преобразования сетевых адресов (NAT).</span><span class="sxs-lookup"><span data-stu-id="e394f-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="e394f-124">Совместное использование портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="e394f-124">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)  
 <span data-ttu-id="e394f-125">Описывает, как использовать компонент совместного использования портов net. TCP в WCF.</span><span class="sxs-lookup"><span data-stu-id="e394f-125">Describes how to use the Net.TCP Port Sharing component of WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e394f-126">Справочник</span><span class="sxs-lookup"><span data-stu-id="e394f-126">Reference</span></span>  

 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="e394f-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e394f-127">Related Sections</span></span>  

 [<span data-ttu-id="e394f-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="e394f-128">Bindings</span></span>](bindings.md)  
  
 [<span data-ttu-id="e394f-129">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="e394f-129">Extending Bindings</span></span>](../extending/extending-bindings.md)

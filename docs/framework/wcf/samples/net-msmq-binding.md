---
title: Привязка MSMQ на платформе .NET
ms.date: 03/30/2017
ms.assetid: fe4bb696-f57c-4cb3-9b7e-9d95fe6b8323
ms.openlocfilehash: 22b82e9335f3bf5861000a62374ab9e8dccce8cf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259984"
---
# <a name="net-msmq-binding"></a><span data-ttu-id="2e4fc-102">Привязка MSMQ на платформе .NET</span><span class="sxs-lookup"><span data-stu-id="2e4fc-102">Net MSMQ Binding</span></span>

<span data-ttu-id="2e4fc-103">Этот раздел содержит образцы, которые демонстрируют использование привязки атрибутов MSMQ элемента конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-103">This section contains samples that demonstrate using MSMQ binding attributes of an endpoint element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2e4fc-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2e4fc-104">In This Section</span></span>  

 [<span data-ttu-id="2e4fc-105">Привязка MSMQ с поддержкой транзакций</span><span class="sxs-lookup"><span data-stu-id="2e4fc-105">Transacted MSMQ Binding</span></span>](transacted-msmq-binding.md)  
 <span data-ttu-id="2e4fc-106">Показывает, как осуществлять транзакционное взаимодействие с использованием очередей с помощью очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="2e4fc-106">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ).</span></span>  
  
 [<span data-ttu-id="2e4fc-107">Неустойчивое взаимодействие с использованием очереди</span><span class="sxs-lookup"><span data-stu-id="2e4fc-107">Volatile Queued Communication</span></span>](volatile-queued-communication.md)  
 <span data-ttu-id="2e4fc-108">Демонстрирует неустойчивое взаимодействие с использованием очередей через MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-108">Demonstrates how to perform volatile queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="2e4fc-109">Очереди недоставленных сообщений</span><span class="sxs-lookup"><span data-stu-id="2e4fc-109">Dead Letter Queues</span></span>](dead-letter-queues.md)  
 <span data-ttu-id="2e4fc-110">Демонстрирует обработку недоставленных сообщений.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-110">Demonstrates how to handle and process messages that have failed delivery.</span></span>  
  
 [<span data-ttu-id="2e4fc-111">Обработка подозрительных сообщений в MSMQ 4.0</span><span class="sxs-lookup"><span data-stu-id="2e4fc-111">Poison Message Handling in MSMQ 4.0</span></span>](poison-message-handling-in-msmq-4-0.md)  
 <span data-ttu-id="2e4fc-112">Демонстрирует обработку подозрительных сообщений в службе с использованием MSMQ 4.0.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-112">Demonstrates how to perform poison message handling in a service using MSMQ 4.0.</span></span>  
  
 [<span data-ttu-id="2e4fc-113">Сеансы и очереди</span><span class="sxs-lookup"><span data-stu-id="2e4fc-113">Sessions and Queues</span></span>](sessions-and-queues.md)  
 <span data-ttu-id="2e4fc-114">Показывает, как с помощью транспорта очереди сообщений (MSMQ) отправить и принять набор взаимосвязанных сообщений при взаимодействии с использованием очередей.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-114">Demonstrates how to send and receive a set of related messages in queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="2e4fc-115">Двусторонний обмен данными</span><span class="sxs-lookup"><span data-stu-id="2e4fc-115">Two-Way Communication</span></span>](two-way-communication.md)  
 <span data-ttu-id="2e4fc-116">Демонстрирует транзакционное двустороннее взаимодействие с использованием очередей через MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-116">Demonstrates how to perform transacted two-way queued communication over MSMQ.</span></span>
  
 [<span data-ttu-id="2e4fc-117">SRMP</span><span class="sxs-lookup"><span data-stu-id="2e4fc-117">SRMP</span></span>](srmp.md)  
 <span data-ttu-id="2e4fc-118">Показывает, как осуществлять транзакционное взаимодействие по HTTP с помощью очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="2e4fc-118">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 [<span data-ttu-id="2e4fc-119">Безопасность сообщений при использовании очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="2e4fc-119">Message Security over Message Queuing</span></span>](message-security-over-message-queuing.md)  
 <span data-ttu-id="2e4fc-120">Демонстрирует реализацию приложения, использующего протокол WS-Security и проверку подлинности с использованием сертификата X.509v3 для клиента и требующего проверки подлинности сервера с использованием сертификата X.509v3 сервера через MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-120">Demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span>

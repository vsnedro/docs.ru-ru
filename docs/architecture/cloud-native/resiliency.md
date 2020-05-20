---
title: Устойчивость, ориентированная на облако
description: Создание архитектуры облачных приложений .NET для Azure | Устойчивость машинного кода в облаке
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: f3aa89e3ae21b13a31f65013b59636b3f931553c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613776"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="aee42-103">Устойчивость, ориентированная на облако</span><span class="sxs-lookup"><span data-stu-id="aee42-103">Cloud-native resiliency</span></span>

<span data-ttu-id="aee42-104">Устойчивость — это способность системы реагировать на сбои и продолжать работать.</span><span class="sxs-lookup"><span data-stu-id="aee42-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="aee42-105">Не следует избегать сбоев, но принимать ошибки и создавать собственные облачные службы для реагирования на них.</span><span class="sxs-lookup"><span data-stu-id="aee42-105">It's not about avoiding failure, but accepting failure and constructing your cloud-native services to respond to it.</span></span> <span data-ttu-id="aee42-106">Необходимо как можно быстрее вернуться к полностью работоспособному состоянию.</span><span class="sxs-lookup"><span data-stu-id="aee42-106">You want to return to a fully functioning state quickly as possible.</span></span>

<span data-ttu-id="aee42-107">В отличие от традиционных монолитных приложений, где все работает вместе в одном процессе, облачные системы используют распределенную архитектуру, как показано на рисунке 6-1:</span><span class="sxs-lookup"><span data-stu-id="aee42-107">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace a distributed architecture as shown in Figure 6-1:</span></span>

![Распределенное облако — собственная среда](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="aee42-109">**Рис. 6-1.**</span><span class="sxs-lookup"><span data-stu-id="aee42-109">**Figure 6-1.**</span></span> <span data-ttu-id="aee42-110">Распределенное облако — собственная среда</span><span class="sxs-lookup"><span data-stu-id="aee42-110">Distributed cloud-native environment</span></span>

<span data-ttu-id="aee42-111">На предыдущем рисунке каждая микрослужба и облачная [Служба резервного копирования](https://12factor.net/backing-services) выполняются в отдельном процессе в инфраструктуре сервера, взаимодействующем через сетевые вызовы.</span><span class="sxs-lookup"><span data-stu-id="aee42-111">In the previous figure, each microservice and cloud-based [backing service](https://12factor.net/backing-services) execute in a separate process, across server infrastructure, communicating via network-based calls.</span></span>

<span data-ttu-id="aee42-112">При работе в этой среде служба должна быть чувствительна к различным проблемам:</span><span class="sxs-lookup"><span data-stu-id="aee42-112">Operating in this environment, a service must be sensitive to many different challenges:</span></span>

- <span data-ttu-id="aee42-113">Непредвиденная задержка сети — время, когда запрос на обслуживание перемещаются получателю и обратно.</span><span class="sxs-lookup"><span data-stu-id="aee42-113">Unexpected network latency - the time for a service request to travel to the receiver and back.</span></span>

- <span data-ttu-id="aee42-114">[Временные сбои](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) — кратковременные ошибки подключения к сети.</span><span class="sxs-lookup"><span data-stu-id="aee42-114">[Transient faults](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) - short-lived network connectivity errors.</span></span>

- <span data-ttu-id="aee42-115">Блокирование длительно выполняющейся синхронной операции.</span><span class="sxs-lookup"><span data-stu-id="aee42-115">Blockage by a long-running synchronous operation.</span></span>

- <span data-ttu-id="aee42-116">Ведущий процесс, который завершился сбоем, перезапускается или перемещается.</span><span class="sxs-lookup"><span data-stu-id="aee42-116">A host process that has crashed and is being restarted or moved.</span></span>

- <span data-ttu-id="aee42-117">Перегруженная микрослужба, которая не может ответить на короткое время.</span><span class="sxs-lookup"><span data-stu-id="aee42-117">An overloaded microservice that can't respond for a short time.</span></span>

- <span data-ttu-id="aee42-118">Выполняющаяся операция Orchestrator, например последовательное обновление или перемещение службы с одного узла на другой.</span><span class="sxs-lookup"><span data-stu-id="aee42-118">An in-flight orchestrator operation such as a rolling upgrade or moving a service from one node to another.</span></span>

- <span data-ttu-id="aee42-119">Сбои оборудования.</span><span class="sxs-lookup"><span data-stu-id="aee42-119">Hardware failures.</span></span>

<span data-ttu-id="aee42-120">Облачные платформы могут обнаруживать и устранять многие из этих проблем инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="aee42-120">Cloud platforms can detect and mitigate many of these infrastructure issues.</span></span> <span data-ttu-id="aee42-121">Она может перезапускаться, масштабироваться и даже распространять службу на другой узел.</span><span class="sxs-lookup"><span data-stu-id="aee42-121">It may restart, scale out, and even redistribute your service to a different node.</span></span>  <span data-ttu-id="aee42-122">Тем не менее, чтобы воспользоваться всеми преимуществами этой встроенной защиты, необходимо разрабатывать службы для реагирования на нее и развиваться в этой динамической среде.</span><span class="sxs-lookup"><span data-stu-id="aee42-122">However, to take full advantage of this built-in protection, you must design your services to react to it and thrive in this dynamic environment.</span></span>

<span data-ttu-id="aee42-123">В следующих разделах мы рассмотрим защитные методы, которые служба и управляемые облачные ресурсы могут использовать для минимизации простоев и сбоев.</span><span class="sxs-lookup"><span data-stu-id="aee42-123">In the following sections, we'll explore defensive techniques that your service and managed cloud resources can leverage to minimize downtime and disruption.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="aee42-124">[Назад](elastic-search-in-azure.md)
>[Вперед](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="aee42-124">[Previous](elastic-search-in-azure.md)
[Next](application-resiliency-patterns.md)</span></span>

---
title: Устойчивое взаимодействие
description: Создание архитектуры облачных приложений .NET для Azure | Устойчивое взаимодействие
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 18b26223634efc5c05f680d0cbb7c8cbc2490a59
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166044"
---
# <a name="resilient-communications"></a><span data-ttu-id="8541a-103">Устойчивое взаимодействие</span><span class="sxs-lookup"><span data-stu-id="8541a-103">Resilient communications</span></span>

<span data-ttu-id="8541a-104">В рамках этой книги мы включили архитектурный подход на основе микрослужб.</span><span class="sxs-lookup"><span data-stu-id="8541a-104">Throughout this book, we've embraced a microservice-based architectural approach.</span></span> <span data-ttu-id="8541a-105">Хотя такая архитектура обеспечивает важные преимущества, она предоставляет множество проблем:</span><span class="sxs-lookup"><span data-stu-id="8541a-105">While such an architecture provides important benefits, it presents many challenges:</span></span>

- <span data-ttu-id="8541a-106">*Необработанное сетевое взаимодействие.*</span><span class="sxs-lookup"><span data-stu-id="8541a-106">*Out-of-process network communication.*</span></span> <span data-ttu-id="8541a-107">Каждая микрослужба взаимодействует по сетевому протоколу, который представляет перегрузку сети, задержку и временные сбои.</span><span class="sxs-lookup"><span data-stu-id="8541a-107">Each microservice communicates over a network protocol that introduces network congestion, latency, and transient faults.</span></span>

- <span data-ttu-id="8541a-108">*Обнаружение службы.*</span><span class="sxs-lookup"><span data-stu-id="8541a-108">*Service discovery.*</span></span> <span data-ttu-id="8541a-109">Как микрослужбы обнаруживают и взаимодействуют друг с другом при работе в кластере компьютеров с собственными IP-адресами и портами?</span><span class="sxs-lookup"><span data-stu-id="8541a-109">How do microservices discover and communicate with each other when running across a cluster of machines with their own IP addresses and ports?</span></span>

- <span data-ttu-id="8541a-110">*Устойчивость.*</span><span class="sxs-lookup"><span data-stu-id="8541a-110">*Resiliency.*</span></span> <span data-ttu-id="8541a-111">Как управлять кратковременными сбоями и поддерживать стабильность системы?</span><span class="sxs-lookup"><span data-stu-id="8541a-111">How do you manage short-lived failures and keep the system stable?</span></span>

- <span data-ttu-id="8541a-112">*Балансировка нагрузки.*</span><span class="sxs-lookup"><span data-stu-id="8541a-112">*Load balancing.*</span></span> <span data-ttu-id="8541a-113">Как входящий трафик распределяется по нескольким экземплярам микрослужбы?</span><span class="sxs-lookup"><span data-stu-id="8541a-113">How does inbound traffic get distributed across multiple instances of a microservice?</span></span>

- <span data-ttu-id="8541a-114">*Безопасность.*</span><span class="sxs-lookup"><span data-stu-id="8541a-114">*Security.*</span></span> <span data-ttu-id="8541a-115">Как применяются такие проблемы безопасности, как шифрование на транспортном уровне и управление сертификатами?</span><span class="sxs-lookup"><span data-stu-id="8541a-115">How are security concerns such as transport-level encryption and certificate management enforced?</span></span>

- <span data-ttu-id="8541a-116">*Распределенный мониторинг.*</span><span class="sxs-lookup"><span data-stu-id="8541a-116">*Distributed Monitoring.*</span></span> <span data-ttu-id="8541a-117">Как вы устанавливаете и отслеживаете трассировку и мониторинг для одного запроса в нескольких микрослужбах?</span><span class="sxs-lookup"><span data-stu-id="8541a-117">- How do you correlate and capture traceability and monitoring for a single request across multiple consuming microservices?</span></span>

<span data-ttu-id="8541a-118">Эти проблемы можно решить с помощью различных библиотек и платформ, но реализация может быть дорогостоящей, сложной и трудоемкой.</span><span class="sxs-lookup"><span data-stu-id="8541a-118">You can address these concerns with different libraries and frameworks, but the implementation can be expensive, complex, and time-consuming.</span></span> <span data-ttu-id="8541a-119">Кроме того, в итоге связаны проблемы с инфраструктурой, связанные с бизнес-логикой.</span><span class="sxs-lookup"><span data-stu-id="8541a-119">You also end up with infrastructure concerns coupled to business logic.</span></span>

## <a name="service-mesh"></a><span data-ttu-id="8541a-120">Сеть службы</span><span class="sxs-lookup"><span data-stu-id="8541a-120">Service mesh</span></span>

<span data-ttu-id="8541a-121">Лучший подход — это развивающаяся технология, предназначенная для работы с сетями *служб*.</span><span class="sxs-lookup"><span data-stu-id="8541a-121">A better approach is an evolving technology entitled *Service Mesh*.</span></span> <span data-ttu-id="8541a-122">[Сетка служб](https://www.nginx.com/blog/what-is-a-service-mesh/) — это настраиваемый уровень инфраструктуры со встроенными возможностями для управления взаимодействием служб и другими упомянутыми выше проблемами.</span><span class="sxs-lookup"><span data-stu-id="8541a-122">A [service mesh](https://www.nginx.com/blog/what-is-a-service-mesh/) is a configurable infrastructure layer with built-in capabilities to handle service communication and the other challenges mentioned above.</span></span> <span data-ttu-id="8541a-123">Она разделяет эти проблемы, перемещая их в прокси-сервер службы.</span><span class="sxs-lookup"><span data-stu-id="8541a-123">It decouples these concerns by moving them into a service proxy.</span></span> <span data-ttu-id="8541a-124">Прокси-сервер развертывается в отдельный процесс (называемый [расширения](/azure/architecture/patterns/sidecar)) для обеспечения изоляции от бизнес-кода.</span><span class="sxs-lookup"><span data-stu-id="8541a-124">The proxy is deployed into a separate process (called a [sidecar](/azure/architecture/patterns/sidecar)) to provide isolation from business code.</span></span> <span data-ttu-id="8541a-125">Однако расширения связывается с этой службой. она создается с ней и разделяет жизненный цикл.</span><span class="sxs-lookup"><span data-stu-id="8541a-125">However, the sidecar is linked to the service - it's created with it and shares its lifecycle.</span></span> <span data-ttu-id="8541a-126">Этот сценарий показан на рис. 6-7.</span><span class="sxs-lookup"><span data-stu-id="8541a-126">Figure 6-7 shows this scenario.</span></span>

![Сеть службы с побочным автомобилем](./media/service-mesh-with-side-car.png)

<span data-ttu-id="8541a-128">**Рис. 6-7**.</span><span class="sxs-lookup"><span data-stu-id="8541a-128">**Figure 6-7**.</span></span> <span data-ttu-id="8541a-129">Сеть службы с побочным автомобилем</span><span class="sxs-lookup"><span data-stu-id="8541a-129">Service mesh with a side car</span></span>

<span data-ttu-id="8541a-130">На предыдущем рисунке обратите внимание, как прокси-сервер перехватывает и управляет связью между микрослужбами и кластером.</span><span class="sxs-lookup"><span data-stu-id="8541a-130">In the previous figure, note how the proxy intercepts and manages communication among the microservices and the cluster.</span></span>

<span data-ttu-id="8541a-131">Сетка служб логически разделяется на два разнородных компонента: [плоскость данных](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) и [плоскость управления](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc).</span><span class="sxs-lookup"><span data-stu-id="8541a-131">A service mesh is logically split into two disparate components: A [data plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) and [control plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc).</span></span> <span data-ttu-id="8541a-132">На рис. 6-8 показаны эти компоненты и их обязанности.</span><span class="sxs-lookup"><span data-stu-id="8541a-132">Figure 6-8 shows these components and their responsibilities.</span></span>

![Управление сеткой услуг и плоскость данных](./media/istio-control-and-data-plane.png)

<span data-ttu-id="8541a-134">**Рис. 6-8.**</span><span class="sxs-lookup"><span data-stu-id="8541a-134">**Figure 6-8.**</span></span> <span data-ttu-id="8541a-135">Управление сеткой услуг и плоскость данных</span><span class="sxs-lookup"><span data-stu-id="8541a-135">Service mesh control and data plane</span></span>

<span data-ttu-id="8541a-136">После настройки сеть службы сильно функционирует.</span><span class="sxs-lookup"><span data-stu-id="8541a-136">Once configured, a service mesh is highly functional.</span></span> <span data-ttu-id="8541a-137">Он может получить соответствующий пул экземпляров из конечной точки обнаружения службы.</span><span class="sxs-lookup"><span data-stu-id="8541a-137">It can retrieve a corresponding pool of instances from a service discovery endpoint.</span></span> <span data-ttu-id="8541a-138">Затем сетка может отправить запрос к определенному экземпляру, записывая тип задержки и ответа результата.</span><span class="sxs-lookup"><span data-stu-id="8541a-138">The mesh can then send a request to a specific instance, recording the latency and response type of the result.</span></span> <span data-ttu-id="8541a-139">Сетка может выбрать экземпляр, который, скорее всего, будет возвращать быстрый ответ на основе многих факторов, включая наблюдаемую задержку для последних запросов.</span><span class="sxs-lookup"><span data-stu-id="8541a-139">A mesh can choose the instance most likely to return a fast response based on many factors, including its observed latency for recent requests.</span></span>

<span data-ttu-id="8541a-140">Если экземпляр не отвечает или завершается неудачно, сеть попытается повторить запрос на другом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="8541a-140">If an instance is unresponsive or fails, the mesh will retry the request on another instance.</span></span> <span data-ttu-id="8541a-141">Если он возвращает ошибки, сеть удаляет экземпляр из пула балансировки нагрузки и переводит его после восстановлении.</span><span class="sxs-lookup"><span data-stu-id="8541a-141">If it returns errors, a mesh will evict the instance from the load-balancing pool and restate it after it heals.</span></span> <span data-ttu-id="8541a-142">Если время ожидания запроса истекло, произойдет сбой сетки, а затем повторите запрос.</span><span class="sxs-lookup"><span data-stu-id="8541a-142">If a request times out, a mesh can fail and then retry the request.</span></span> <span data-ttu-id="8541a-143">Сетка захватывает и выдает метрики и распределенную трассировку в централизованную систему метрик.</span><span class="sxs-lookup"><span data-stu-id="8541a-143">A mesh captures and emits metrics and distributed tracing to a centralized metrics system.</span></span>

## <a name="istio-and-envoy"></a><span data-ttu-id="8541a-144">Istio и делегат</span><span class="sxs-lookup"><span data-stu-id="8541a-144">Istio and Envoy</span></span>

<span data-ttu-id="8541a-145">Хотя в настоящее время существует несколько вариантов сетки служб, [Istio](https://istio.io/docs/concepts/what-is-istio/) является самым популярным в момент написания этой статьи.</span><span class="sxs-lookup"><span data-stu-id="8541a-145">While a few service mesh options currently exist, [Istio](https://istio.io/docs/concepts/what-is-istio/) is the most popular at the time of this writing.</span></span> <span data-ttu-id="8541a-146">Istio — это совместное предприятие от IBM, Google и Лифт.</span><span class="sxs-lookup"><span data-stu-id="8541a-146">Istio is a joint venture from IBM, Google, and Lyft.</span></span> <span data-ttu-id="8541a-147">Это предложение с открытым кодом, которое можно интегрировать в новое или существующее распределенное приложение.</span><span class="sxs-lookup"><span data-stu-id="8541a-147">It's an open-source offering that can be integrated into a new or existing distributed application.</span></span> <span data-ttu-id="8541a-148">Эта технология обеспечивает единообразное и полное решение для защиты и подключения микрослужб, а также для их мониторинга.</span><span class="sxs-lookup"><span data-stu-id="8541a-148">The technology provides a consistent and complete solution to secure, connect, and monitor microservices.</span></span> <span data-ttu-id="8541a-149">Она обладает следующими возможностями:</span><span class="sxs-lookup"><span data-stu-id="8541a-149">Its features include:</span></span>

- <span data-ttu-id="8541a-150">Защита обмена данными между службами в кластере с помощью надежной проверки подлинности и авторизации на основе удостоверений.</span><span class="sxs-lookup"><span data-stu-id="8541a-150">Secure service-to-service communication in a cluster with strong identity-based authentication and authorization.</span></span>
- <span data-ttu-id="8541a-151">Автоматическая балансировка нагрузки для трафика HTTP, [gRPC](https://grpc.io/), WEBSOCKET и TCP.</span><span class="sxs-lookup"><span data-stu-id="8541a-151">Automatic load balancing for HTTP, [gRPC](https://grpc.io/), WebSocket, and TCP traffic.</span></span>
- <span data-ttu-id="8541a-152">Детальное управление поведением трафика с богатыми правилами маршрутизации, повторными попытками, отработкой отказа и внедрением ошибок.</span><span class="sxs-lookup"><span data-stu-id="8541a-152">Fine-grained control of traffic behavior with rich routing rules, retries, failovers, and fault injection.</span></span>
- <span data-ttu-id="8541a-153">Подключаемый уровень политики и API конфигурации, поддерживающий элементы управления доступом, ограничения скорости и квоты.</span><span class="sxs-lookup"><span data-stu-id="8541a-153">A pluggable policy layer and configuration API supporting access controls, rate limits, and quotas.</span></span>
- <span data-ttu-id="8541a-154">Автоматические метрики, журналы и трассировки для всего трафика в кластере, включая входящие и исходящие данные кластера.</span><span class="sxs-lookup"><span data-stu-id="8541a-154">Automatic metrics, logs, and traces for all traffic within a cluster, including cluster ingress and egress.</span></span>

<span data-ttu-id="8541a-155">Ключевым компонентом для реализации Istio является служба прокси-сервера с [представителем прокси](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy).</span><span class="sxs-lookup"><span data-stu-id="8541a-155">A key component for an Istio implementation is a proxy service entitled the [Envoy proxy](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy).</span></span> <span data-ttu-id="8541a-156">Она выполняется параллельно с каждой службой и предоставляет независимую от платформы основу для следующих функций:</span><span class="sxs-lookup"><span data-stu-id="8541a-156">It runs alongside each service and provides a platform-agnostic foundation for the following features:</span></span>

- <span data-ttu-id="8541a-157">Динамическое обнаружение служб.</span><span class="sxs-lookup"><span data-stu-id="8541a-157">Dynamic service discovery.</span></span>
- <span data-ttu-id="8541a-158">Балансировка нагрузки.</span><span class="sxs-lookup"><span data-stu-id="8541a-158">Load balancing.</span></span>
- <span data-ttu-id="8541a-159">Завершение TLS.</span><span class="sxs-lookup"><span data-stu-id="8541a-159">TLS termination.</span></span>
- <span data-ttu-id="8541a-160">Прокси-серверы HTTP и gRPC.</span><span class="sxs-lookup"><span data-stu-id="8541a-160">HTTP and gRPC proxies.</span></span>
- <span data-ttu-id="8541a-161">Устойчивость выключателя.</span><span class="sxs-lookup"><span data-stu-id="8541a-161">Circuit breaker resiliency.</span></span>
- <span data-ttu-id="8541a-162">Проверки работоспособности.</span><span class="sxs-lookup"><span data-stu-id="8541a-162">Health checks.</span></span>
- <span data-ttu-id="8541a-163">Последовательные обновления с развертываниями [ранний](https://martinfowler.com/bliki/CanaryRelease.html) .</span><span class="sxs-lookup"><span data-stu-id="8541a-163">Rolling updates with [canary](https://martinfowler.com/bliki/CanaryRelease.html) deployments.</span></span>

<span data-ttu-id="8541a-164">Как уже говорилось, представитель развертывается как расширения для каждой микрослужбы в кластере.</span><span class="sxs-lookup"><span data-stu-id="8541a-164">As previously discussed, Envoy is deployed as a sidecar to each microservice in the cluster.</span></span>

## <a name="integration-with-azure-kubernetes-services"></a><span data-ttu-id="8541a-165">Интеграция с Azure Kubernetes Services</span><span class="sxs-lookup"><span data-stu-id="8541a-165">Integration with Azure Kubernetes Services</span></span>

<span data-ttu-id="8541a-166">Облако Azure использует Istio и обеспечивает прямую поддержку в Azure Kubernetes Services.</span><span class="sxs-lookup"><span data-stu-id="8541a-166">The Azure cloud embraces Istio and provides direct support for it within Azure Kubernetes Services.</span></span> <span data-ttu-id="8541a-167">Следующие ссылки помогут вам приступить к работе:</span><span class="sxs-lookup"><span data-stu-id="8541a-167">The following links can help you get started:</span></span>

- [<span data-ttu-id="8541a-168">Установка Istio в AKS</span><span class="sxs-lookup"><span data-stu-id="8541a-168">Installing Istio in AKS</span></span>](/azure/aks/istio-install)
- [<span data-ttu-id="8541a-169">Использование AKS и Istio</span><span class="sxs-lookup"><span data-stu-id="8541a-169">Using AKS and Istio</span></span>](/azure/aks/istio-scenario-routing)

### <a name="references"></a><span data-ttu-id="8541a-170">Ссылки</span><span class="sxs-lookup"><span data-stu-id="8541a-170">References</span></span>

- [<span data-ttu-id="8541a-171">Polly</span><span class="sxs-lookup"><span data-stu-id="8541a-171">Polly</span></span>](http://www.thepollyproject.org/)

- [<span data-ttu-id="8541a-172">Шаблон повторов</span><span class="sxs-lookup"><span data-stu-id="8541a-172">Retry pattern</span></span>](/azure/architecture/patterns/retry)

- [<span data-ttu-id="8541a-173">Шаблон автоматического выключения</span><span class="sxs-lookup"><span data-stu-id="8541a-173">Circuit Breaker pattern</span></span>](/azure/architecture/patterns/circuit-breaker)

- [<span data-ttu-id="8541a-174">Обеспечение устойчивости в техническом документе Azure</span><span class="sxs-lookup"><span data-stu-id="8541a-174">Resilience in Azure whitepaper</span></span>](https://azure.microsoft.com/mediahandler/files/resourcefiles/resilience-in-azure-whitepaper/Resilience%20in%20Azure.pdf)

- [<span data-ttu-id="8541a-175">задержка в сети</span><span class="sxs-lookup"><span data-stu-id="8541a-175">network latency</span></span>](https://www.techopedia.com/definition/8553/network-latency)

- [<span data-ttu-id="8541a-176">Избыточность</span><span class="sxs-lookup"><span data-stu-id="8541a-176">Redundancy</span></span>](/azure/architecture/guide/design-principles/redundancy)

- [<span data-ttu-id="8541a-177">Георепликация</span><span class="sxs-lookup"><span data-stu-id="8541a-177">geo-replication</span></span>](/azure/sql-database/sql-database-active-geo-replication)

- [<span data-ttu-id="8541a-178">Диспетчер трафика Azure</span><span class="sxs-lookup"><span data-stu-id="8541a-178">Azure Traffic Manager</span></span>](/azure/traffic-manager/traffic-manager-overview)

- [<span data-ttu-id="8541a-179">Руководство по автоматическому масштабированию</span><span class="sxs-lookup"><span data-stu-id="8541a-179">Autoscaling guidance</span></span>](/azure/architecture/best-practices/auto-scaling)

- [<span data-ttu-id="8541a-180">Istio</span><span class="sxs-lookup"><span data-stu-id="8541a-180">Istio</span></span>](https://istio.io/docs/concepts/what-is-istio/)

- [<span data-ttu-id="8541a-181">Прокси-сервер делегата</span><span class="sxs-lookup"><span data-stu-id="8541a-181">Envoy proxy</span></span>](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)

>[!div class="step-by-step"]
><span data-ttu-id="8541a-182">[Назад](infrastructure-resiliency-azure.md)
>[Вперед](monitoring-health.md)</span><span class="sxs-lookup"><span data-stu-id="8541a-182">[Previous](infrastructure-resiliency-azure.md)
[Next](monitoring-health.md)</span></span>

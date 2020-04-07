---
title: Кандидатские приложения для родного облака
description: Узнайте, какие типы приложений могут использовать облачный подход
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 8e58f5bd3aa0a4503ea73ab454e42e863eb0bb5d
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805611"
---
# <a name="candidate-apps-for-cloud-native"></a><span data-ttu-id="7f110-103">Кандидатские приложения для родного облака</span><span class="sxs-lookup"><span data-stu-id="7f110-103">Candidate apps for cloud native</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="7f110-104">Посмотрите на приложения в вашем портфолио.</span><span class="sxs-lookup"><span data-stu-id="7f110-104">Look at the apps in your portfolio.</span></span> <span data-ttu-id="7f110-105">Сколько из них имеют право на архитектуру, наносивую тучное?</span><span class="sxs-lookup"><span data-stu-id="7f110-105">How many of them qualify for a cloud-native architecture?</span></span> <span data-ttu-id="7f110-106">Все они?</span><span class="sxs-lookup"><span data-stu-id="7f110-106">All of them?</span></span> <span data-ttu-id="7f110-107">Может быть, некоторые?</span><span class="sxs-lookup"><span data-stu-id="7f110-107">Perhaps some?</span></span>

<span data-ttu-id="7f110-108">Применяя анализ затрат/выгод, есть хороший шанс, что большинство из них не будет поддерживать здоровенный ценник, необходимый для того, чтобы быть родным облаком.</span><span class="sxs-lookup"><span data-stu-id="7f110-108">Applying a cost/benefit analysis, there's a good chance that most wouldn't support the hefty price tag required to be cloud native.</span></span> <span data-ttu-id="7f110-109">Стоимость того, чтобы быть родным облаком, намного превысит бизнес-ценность приложения.</span><span class="sxs-lookup"><span data-stu-id="7f110-109">The cost of being cloud native would far exceed the business value of the application.</span></span>

<span data-ttu-id="7f110-110">Какой тип приложения может быть кандидатом для родного облака?</span><span class="sxs-lookup"><span data-stu-id="7f110-110">What type of application might be a candidate for cloud native?</span></span>

- <span data-ttu-id="7f110-111">Большая стратегическая корпоративная корпоративная система, которая должна постоянно развивать бизнес-возможности/функции</span><span class="sxs-lookup"><span data-stu-id="7f110-111">A large, strategic enterprise system that needs to constantly evolve business capabilities/features</span></span>

- <span data-ttu-id="7f110-112">Приложение, требующее высокой скорости выпуска - с высокой уверенностью</span><span class="sxs-lookup"><span data-stu-id="7f110-112">An application that requires a high release velocity - with high confidence</span></span>

- <span data-ttu-id="7f110-113">Система, с которой отдельные функции должны выпустить *без* полной передислокации всей системы</span><span class="sxs-lookup"><span data-stu-id="7f110-113">A system with where individual features must release *without* a full redeployment of the entire system</span></span>

- <span data-ttu-id="7f110-114">Приложение, разработанное командами, имеющих опыт работы в различных технологических стеках</span><span class="sxs-lookup"><span data-stu-id="7f110-114">An application developed by teams with expertise in different technology stacks</span></span>

- <span data-ttu-id="7f110-115">Приложение с компонентами, которые должны масштабироваться независимо</span><span class="sxs-lookup"><span data-stu-id="7f110-115">An application with components that must scale independently</span></span>

<span data-ttu-id="7f110-116">Тогда Есть устаревшие системы.</span><span class="sxs-lookup"><span data-stu-id="7f110-116">Then there are legacy systems.</span></span> <span data-ttu-id="7f110-117">Хотя мы все хотели бы создавать новые приложения, мы часто отвечаем за модернизацию устаревших рабочих нагрузок, которые имеют решающее значение для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7f110-117">While we'd all like to build new applications, we're often responsible for modernizing legacy workloads that are critical to the business.</span></span> <span data-ttu-id="7f110-118">Со временем устаревшее приложение может быть разложено на микрослужбы, контейнеризировано и, в конечном счете, «перемочено» в архитектуру, наносившуюся в облако.</span><span class="sxs-lookup"><span data-stu-id="7f110-118">Over time, a legacy application could be decomposed into microservices, containerized, and ultimately "replatformed" into a cloud-native architecture.</span></span>

### <a name="modernizing-legacy-apps"></a><span data-ttu-id="7f110-119">Модернизация устаревших приложений</span><span class="sxs-lookup"><span data-stu-id="7f110-119">Modernizing legacy apps</span></span>

<span data-ttu-id="7f110-120">Бесплатная электронная книга Майкрософт [Модернизируйте существующие приложения .NET с облачными технологиями Azure и Windows Containers,](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) содержит рекомендации для переноса рабочих нагрузок в облако.</span><span class="sxs-lookup"><span data-stu-id="7f110-120">The free Microsoft e-book [Modernize existing .NET applications with Azure cloud and Windows Containers](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) provides guidance for migrating on-premises workloads into cloud.</span></span> <span data-ttu-id="7f110-121">На рисунке 1-10 показано, что не существует единой универсальной стратегии модернизации устаревших приложений.</span><span class="sxs-lookup"><span data-stu-id="7f110-121">Figure 1-10 shows that there isn't a single, one-size-fits-all strategy for modernizing legacy applications.</span></span>

![Стратегии миграции устаревших рабочих нагрузок](./media/strategies-for-migrating-legacy-workloads.png)

<span data-ttu-id="7f110-123">**Рисунок 1-10**.</span><span class="sxs-lookup"><span data-stu-id="7f110-123">**Figure 1-10**.</span></span> <span data-ttu-id="7f110-124">Стратегии миграции устаревших рабочих нагрузок</span><span class="sxs-lookup"><span data-stu-id="7f110-124">Strategies for migrating legacy workloads</span></span>

<span data-ttu-id="7f110-125">Монолитные приложения, которые не критичны, в значительной степени выигрывают от быстрой миграции лифта и переноса[(Cloud Infrastructure-Ready).](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)</span><span class="sxs-lookup"><span data-stu-id="7f110-125">Monolithic apps that are non-critical largely benefit from a quick lift-and-shift ([Cloud Infrastructure-Ready](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)) migration.</span></span> <span data-ttu-id="7f110-126">Здесь рабочая нагрузка на непредрасположенности в облачном VM без изменений.</span><span class="sxs-lookup"><span data-stu-id="7f110-126">Here, the on-premises workload is rehosted to a cloud-based VM, without changes.</span></span> <span data-ttu-id="7f110-127">Этот подход использует [модель IaaS (Инфраструктура как услуга).](https://azure.microsoft.com/overview/what-is-iaas/)</span><span class="sxs-lookup"><span data-stu-id="7f110-127">This approach uses the [IaaS (Infrastructure as a Service) model](https://azure.microsoft.com/overview/what-is-iaas/).</span></span> <span data-ttu-id="7f110-128">Azure включает в себя несколько инструментов, таких как [Azure Migrate,](https://azure.microsoft.com/services/azure-migrate/) [Восстановление сайта Azure](https://azure.microsoft.com/services/site-recovery/)и [служба миграции баз данных Azure,](https://azure.microsoft.com/campaigns/database-migration/) чтобы упростить такой шаг.</span><span class="sxs-lookup"><span data-stu-id="7f110-128">Azure includes several tools such as [Azure Migrate](https://azure.microsoft.com/services/azure-migrate/), [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/), and [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) to make such a move easier.</span></span> <span data-ttu-id="7f110-129">Хотя эта стратегия может принести некоторую экономию средств, такие приложения, как правило, не были проектированы для разблокировки и использования преимуществ облачных вычислений.</span><span class="sxs-lookup"><span data-stu-id="7f110-129">While this strategy can yield some cost savings, such applications typically weren't architected to unlock and leverage the benefits of cloud computing.</span></span>

<span data-ttu-id="7f110-130">Монолитные приложения, которые имеют решающее значение для бизнеса, часто получают выгоду от расширенной миграции лифтов и*сдвигов (Cloud Optimized).*</span><span class="sxs-lookup"><span data-stu-id="7f110-130">Monolithic apps that are critical to the business oftentimes benefit from an enhanced lift-and-shift (*Cloud Optimized*) migration.</span></span> <span data-ttu-id="7f110-131">Этот подход включает оптимизацию развертывания, которая позволяет ключевым облачным службам без изменения базовой архитектуры приложения.</span><span class="sxs-lookup"><span data-stu-id="7f110-131">This approach includes deployment optimizations that enable key cloud services - without changing the core architecture of the application.</span></span> <span data-ttu-id="7f110-132">Например, можно [контейнеризировать](https://docs.microsoft.com/virtualization/windowscontainers/about/) приложение и развернуть его в контейнерный оркестратор, например [службу Azure Kubernetes,](https://azure.microsoft.com/services/kubernetes-service/)обсуждаемую позднее в этой книге.</span><span class="sxs-lookup"><span data-stu-id="7f110-132">For example, you might [containerize](https://docs.microsoft.com/virtualization/windowscontainers/about/) the application and deploy it to a container orchestrator, like [Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/), discussed later in this book.</span></span> <span data-ttu-id="7f110-133">Попав в облако, приложение может использовать другие облачные службы, такие как базы данных, очереди сообщений, мониторинг и распределенное кэширование.</span><span class="sxs-lookup"><span data-stu-id="7f110-133">Once in the cloud, the application could consume other cloud services such as databases, message queues, monitoring, and distributed caching.</span></span>

<span data-ttu-id="7f110-134">Наконец, монолитные приложения, выполняющие стратегические корпоративные функции, могут извлечь выгоду из подхода *Cloud-Native,* предметом этой книги.</span><span class="sxs-lookup"><span data-stu-id="7f110-134">Finally, monolithic apps that perform strategic enterprise functions might best benefit from a *Cloud-Native* approach, the subject of this book.</span></span> <span data-ttu-id="7f110-135">Такой подход обеспечивает гибкость и скорость.</span><span class="sxs-lookup"><span data-stu-id="7f110-135">This approach provides agility and velocity.</span></span> <span data-ttu-id="7f110-136">Но, это происходит за счет реплатформирования, переоценивания и переписывания кода.</span><span class="sxs-lookup"><span data-stu-id="7f110-136">But, it comes at a cost of replatforming, rearchitecting, and rewriting code.</span></span>

<span data-ttu-id="7f110-137">Если вы и ваша команда считаете, что подход, связанный с облачным образованием, является целесообразным, вам необходимо обосновать решение с вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="7f110-137">If you and your team believe a cloud-native approach is appropriate, it behooves you to rationalize the decision with your organization.</span></span> <span data-ttu-id="7f110-138">Что именно решает бизнес-проблема, которую решит облачный подход?</span><span class="sxs-lookup"><span data-stu-id="7f110-138">What exactly is the business problem that a cloud-native approach will solve?</span></span> <span data-ttu-id="7f110-139">Как она будет соответствовать потребностям бизнеса?</span><span class="sxs-lookup"><span data-stu-id="7f110-139">How would it align with business needs?</span></span>

- <span data-ttu-id="7f110-140">Быстрые выпуски функций с повышенной уверенностью?</span><span class="sxs-lookup"><span data-stu-id="7f110-140">Rapid releases of features with increased confidence?</span></span>

- <span data-ttu-id="7f110-141">Мелкозернистые масштабируемости - более эффективное использование ресурсов?</span><span class="sxs-lookup"><span data-stu-id="7f110-141">Fine-grained scalability - more efficient usage of resources?</span></span>

- <span data-ttu-id="7f110-142">Улучшенная устойчивость системы?</span><span class="sxs-lookup"><span data-stu-id="7f110-142">Improved system resiliency?</span></span>

- <span data-ttu-id="7f110-143">Улучшенная производительность системы?</span><span class="sxs-lookup"><span data-stu-id="7f110-143">Improved system performance?</span></span>

- <span data-ttu-id="7f110-144">Больше видимости в операциях?</span><span class="sxs-lookup"><span data-stu-id="7f110-144">More visibility into operations?</span></span>

- <span data-ttu-id="7f110-145">Смешайте платформы разработки и хранилища данных, чтобы прийти к лучшему инструменту для работы?</span><span class="sxs-lookup"><span data-stu-id="7f110-145">Blend development platforms and data stores to arrive at the best tool for the job?</span></span>

- <span data-ttu-id="7f110-146">Будущие инвестиции приложения?</span><span class="sxs-lookup"><span data-stu-id="7f110-146">Future-proof application investment?</span></span>

<span data-ttu-id="7f110-147">Правильная стратегия миграции зависит от организационных приоритетов и систем, на которые вы ориентируетесь.</span><span class="sxs-lookup"><span data-stu-id="7f110-147">The right migration strategy depends on organizational priorities and the systems you're targeting.</span></span> <span data-ttu-id="7f110-148">Для многих может быть более экономически эффективным облачная оптимизация монолитного приложения или добавление услуг с грубым зерном в приложение N-Tier.</span><span class="sxs-lookup"><span data-stu-id="7f110-148">For many, it may be more cost effective to cloud-optimize a monolithic application or add coarse-grained services to an N-Tier app.</span></span> <span data-ttu-id="7f110-149">В этих случаях вы все еще можете в полной мере использовать возможности облака PaaS, подобные тем, которые предлагает Служба приложений Azure.</span><span class="sxs-lookup"><span data-stu-id="7f110-149">In these cases, you can still make full use of cloud PaaS capabilities like the ones offered by Azure App Service.</span></span>

## <a name="summary"></a><span data-ttu-id="7f110-150">Сводка</span><span class="sxs-lookup"><span data-stu-id="7f110-150">Summary</span></span>

<span data-ttu-id="7f110-151">В этой главе мы представили облачные вычисления.</span><span class="sxs-lookup"><span data-stu-id="7f110-151">In this chapter, we introduced cloud-native computing.</span></span> <span data-ttu-id="7f110-152">Мы предоставили определение наряду с ключевыми возможностями, которые управляют облачным приложением.</span><span class="sxs-lookup"><span data-stu-id="7f110-152">We provided a definition along with the key capabilities that drive a cloud-native application.</span></span> <span data-ttu-id="7f110-153">Мы рассмотрели типы приложений, которые могут оправдать эти инвестиции и усилия.</span><span class="sxs-lookup"><span data-stu-id="7f110-153">We looked at the types of applications that might justify this investment and effort.</span></span>

<span data-ttu-id="7f110-154">С введением позади, мы теперь погрузимся в гораздо более подробный взгляд на облако родной.</span><span class="sxs-lookup"><span data-stu-id="7f110-154">With the introduction behind, we now dive into a much more detailed look at cloud native.</span></span>

### <a name="references"></a><span data-ttu-id="7f110-155">Ссылки</span><span class="sxs-lookup"><span data-stu-id="7f110-155">References</span></span>

- [<span data-ttu-id="7f110-156">Облачный фонд индейских вычислений</span><span class="sxs-lookup"><span data-stu-id="7f110-156">Cloud Native Computing Foundation</span></span>](https://www.cncf.io/)

- [<span data-ttu-id="7f110-157">Microservices .NET: Архитектура для контейнерных приложений .NET</span><span class="sxs-lookup"><span data-stu-id="7f110-157">.NET Microservices: Architecture for Containerized .NET applications</span></span>](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [<span data-ttu-id="7f110-158">Модернизация существующих приложений .NET с помощью облачных и Windows-контейнеров</span><span class="sxs-lookup"><span data-stu-id="7f110-158">Modernize existing .NET applications with Azure cloud and Windows Containers</span></span>](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [<span data-ttu-id="7f110-159">Облачные узоры коренных народов Корнелия Дэвис</span><span class="sxs-lookup"><span data-stu-id="7f110-159">Cloud Native Patterns by Cornelia Davis</span></span>](https://www.manning.com/books/cloud-native-patterns)

- [<span data-ttu-id="7f110-160">Помимо приложения "Двенадцать факторов"</span><span class="sxs-lookup"><span data-stu-id="7f110-160">Beyond the Twelve-Factor Application</span></span>](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [<span data-ttu-id="7f110-161">Что такое инфраструктура как код</span><span class="sxs-lookup"><span data-stu-id="7f110-161">What is Infrastructure as Code</span></span>](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [<span data-ttu-id="7f110-162">Микроразвертывание Uber Engineering: ежедневное развертывание с уверенностью</span><span class="sxs-lookup"><span data-stu-id="7f110-162">Uber Engineering's Micro Deploy: Deploying Daily with Confidence</span></span>](https://eng.uber.com/micro-deploy/)

- [<span data-ttu-id="7f110-163">Как Netflix развертывает код</span><span class="sxs-lookup"><span data-stu-id="7f110-163">How Netflix Deploys Code</span></span>](https://www.infoq.com/news/2013/06/netflix/)

- [<span data-ttu-id="7f110-164">Контроль перегрузки для масштабирования микросервисов WeChat</span><span class="sxs-lookup"><span data-stu-id="7f110-164">Overload Control for Scaling WeChat Microservices</span></span>](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
><span data-ttu-id="7f110-165">[Назад](definition.md)
>[Вперед](introduce-eshoponcontainers-reference-app.md)</span><span class="sxs-lookup"><span data-stu-id="7f110-165">[Previous](definition.md)
[Next](introduce-eshoponcontainers-reference-app.md)</span></span>

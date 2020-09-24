---
title: Elasticsearch в собственных приложениях в облаке
description: Узнайте о добавлении возможностей эластичного поиска в собственные облачные приложения.
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: fa46f3387eecb3fccd63fdea10c11e92923ae862
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155384"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="f046b-103">Elasticsearch в собственном облачном приложении</span><span class="sxs-lookup"><span data-stu-id="f046b-103">Elasticsearch in a cloud-native app</span></span>

<span data-ttu-id="f046b-104">Elasticsearch — это распределенная система поиска и аналитики, которая обеспечивает сложные возможности поиска по различным типам данных.</span><span class="sxs-lookup"><span data-stu-id="f046b-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="f046b-105">Это открытый исходный код и широко распространенный.</span><span class="sxs-lookup"><span data-stu-id="f046b-105">It's open source and widely popular.</span></span> <span data-ttu-id="f046b-106">Рассмотрим, как следующие компании интегрируют Elasticsearch в свои приложения:</span><span class="sxs-lookup"><span data-stu-id="f046b-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="f046b-107">[Википедии](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) для полнотекстового и добавочного поиска (Поиск по мере ввода).</span><span class="sxs-lookup"><span data-stu-id="f046b-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="f046b-108">[GitHub](https://www.elastic.co/customers/github) для индексирования и предоставления более 8 000 000 репозиториев кода.</span><span class="sxs-lookup"><span data-stu-id="f046b-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="f046b-109">[DOCKER](https://www.elastic.co/customers/docker) , чтобы сделать его библиотекой контейнеров обнаруживаемой.</span><span class="sxs-lookup"><span data-stu-id="f046b-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="f046b-110">Elasticsearch построен на базе механизма полнотекстового поиска [Apache Lucene](https://lucene.apache.org/core/) .</span><span class="sxs-lookup"><span data-stu-id="f046b-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="f046b-111">Lucene обеспечивает высокую производительность индексирования документов и запросов.</span><span class="sxs-lookup"><span data-stu-id="f046b-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="f046b-112">Он индексирует данные с инверсной схемой индексирования, вместо того чтобы сопоставлять страницы с ключевыми словами, она сопоставляет ключевые слова со страницами так же, как Глоссарий в конце книги.</span><span class="sxs-lookup"><span data-stu-id="f046b-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="f046b-113">Lucene обладает мощными возможностями синтаксиса запросов и может запрашивать данные с помощью следующих средств:</span><span class="sxs-lookup"><span data-stu-id="f046b-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="f046b-114">Term (полное слово)</span><span class="sxs-lookup"><span data-stu-id="f046b-114">Term (a full word)</span></span>
- <span data-ttu-id="f046b-115">Префикс (начинается с слова)</span><span class="sxs-lookup"><span data-stu-id="f046b-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="f046b-116">Подстановочный знак (с помощью \* фильтров "" или "?")</span><span class="sxs-lookup"><span data-stu-id="f046b-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="f046b-117">Фраза (последовательность текста в документе)</span><span class="sxs-lookup"><span data-stu-id="f046b-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="f046b-118">Логическое значение (сложные поиски, объединяющие запросы)</span><span class="sxs-lookup"><span data-stu-id="f046b-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="f046b-119">Хотя Lucene предоставляет низкоуровневые коммуникации для поиска, Elasticsearch предоставляет сервер, расположенный на основе Lucene.</span><span class="sxs-lookup"><span data-stu-id="f046b-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="f046b-120">Elasticsearch добавляет функции более высокого уровня для упрощения работы с Lucene, включая API RESTFUL для доступа к функциям индексирования и поиска Lucene.</span><span class="sxs-lookup"><span data-stu-id="f046b-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene's indexing and searching functionality.</span></span> <span data-ttu-id="f046b-121">Она также предоставляет распределенную инфраструктуру с широкими возможностями масштабирования, отказоустойчивости и высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="f046b-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="f046b-122">Для более крупных облачных приложений с комплексными требованиями поиска Elasticsearch доступен в качестве управляемой службы в Azure.</span><span class="sxs-lookup"><span data-stu-id="f046b-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="f046b-123">Microsoft Azure Marketplace содержит предварительно настроенные шаблоны, которые разработчики могут использовать для развертывания кластера Elasticsearch в Azure.</span><span class="sxs-lookup"><span data-stu-id="f046b-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="f046b-124">С Microsoft Azure Marketplace разработчики могут использовать предварительно настроенные шаблоны, созданные для быстрого развертывания кластера Elasticsearch в Azure.</span><span class="sxs-lookup"><span data-stu-id="f046b-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="f046b-125">С помощью предложения, управляемого Azure, можно развернуть до 50 узлов данных, 20 координирующих узлов и трех выделенных главных узлов.</span><span class="sxs-lookup"><span data-stu-id="f046b-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="f046b-126">Сводка</span><span class="sxs-lookup"><span data-stu-id="f046b-126">Summary</span></span>

<span data-ttu-id="f046b-127">В этой главе представлен подробный обзор данных в собственных облачных системах.</span><span class="sxs-lookup"><span data-stu-id="f046b-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="f046b-128">Мы начали с того, чтобы сравнить объем хранилища данных в монолитных приложениях с шаблонами хранения данных в собственных системах в облаке.</span><span class="sxs-lookup"><span data-stu-id="f046b-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="f046b-129">Мы рассматривали шаблоны данных, реализованные в собственных системах, включая запросы между службами, распределенные транзакции и шаблоны для работы с большими объемами систем.</span><span class="sxs-lookup"><span data-stu-id="f046b-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="f046b-130">Мы относимся к данным SQL с NoSQL.</span><span class="sxs-lookup"><span data-stu-id="f046b-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="f046b-131">Мы рассматривали возможности хранения данных, доступные в Azure, которые включают в себя как ориентированный на Майкрософт, так и вариант с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="f046b-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="f046b-132">Наконец, мы обсуждали кэширование и Elasticsearch в облачном приложении.</span><span class="sxs-lookup"><span data-stu-id="f046b-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="f046b-133">Ссылки</span><span class="sxs-lookup"><span data-stu-id="f046b-133">References</span></span>

- [<span data-ttu-id="f046b-134">Шаблон CQRS</span><span class="sxs-lookup"><span data-stu-id="f046b-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="f046b-135">Шаблон источников событий</span><span class="sxs-lookup"><span data-stu-id="f046b-135">Event Sourcing pattern</span></span>](/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="f046b-136">Почему не существует отказоустойчивых секций РСУБД в Теоремае CAP и почему она доступна?</span><span class="sxs-lookup"><span data-stu-id="f046b-136">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="f046b-137">Материализованное представление</span><span class="sxs-lookup"><span data-stu-id="f046b-137">Materialized View</span></span>](/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="f046b-138">Все, что действительно необходимо знать о базах данных с открытым исходным кодом</span><span class="sxs-lookup"><span data-stu-id="f046b-138">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="f046b-139">Шаблон компенсирующих транзакций</span><span class="sxs-lookup"><span data-stu-id="f046b-139">Compensating Transaction pattern</span></span>](/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="f046b-140">Шаблон Saga</span><span class="sxs-lookup"><span data-stu-id="f046b-140">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="f046b-141">Шаблоны Saga | Реализация бизнес-транзакций с помощью микрослужб</span><span class="sxs-lookup"><span data-stu-id="f046b-141">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="f046b-142">Шаблон компенсирующих транзакций</span><span class="sxs-lookup"><span data-stu-id="f046b-142">Compensating Transaction pattern</span></span>](/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="f046b-143">Знакомство с 9-шариком: Cosmos DB уровней согласованности</span><span class="sxs-lookup"><span data-stu-id="f046b-143">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="f046b-144">Изучение различных типов баз данных NoSQL, часть II</span><span class="sxs-lookup"><span data-stu-id="f046b-144">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="f046b-145">Для баз данных RDBMS, NoSQL и Невскл. Собеседование с Джон Райан</span><span class="sxs-lookup"><span data-stu-id="f046b-145">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="f046b-146">Сравнение SQL VS NoSQL и Невскл. полное сравнение</span><span class="sxs-lookup"><span data-stu-id="f046b-146">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="f046b-147">ТИРЕ: четыре свойства баз данных Kubernetes — Native</span><span class="sxs-lookup"><span data-stu-id="f046b-147">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="f046b-148">коккроачдб</span><span class="sxs-lookup"><span data-stu-id="f046b-148">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="f046b-149">тидб</span><span class="sxs-lookup"><span data-stu-id="f046b-149">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="f046b-150">югабитедб</span><span class="sxs-lookup"><span data-stu-id="f046b-150">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="f046b-151">витесс</span><span class="sxs-lookup"><span data-stu-id="f046b-151">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="f046b-152">Elasticsearch: The Definitive Guide (Elasticsearch: полное руководство)</span><span class="sxs-lookup"><span data-stu-id="f046b-152">Elasticsearch: The Definitive Guide</span></span>](https://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="f046b-153">Введение в Apache Lucene</span><span class="sxs-lookup"><span data-stu-id="f046b-153">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="f046b-154">[Назад](azure-caching.md)
>[Вперед](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="f046b-154">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->

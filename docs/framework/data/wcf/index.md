---
title: Службы WCF Data Services 4.5
description: Сведения о WCF Data Services, компоненте .NET Framework, который поддерживает службы для предоставления и использования данных с помощью семантики RESTFUL.
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: ca6b196e8c910f97ead6d1df5b6c0dd6c49c68a4
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247756"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="ca750-103">Службы WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="ca750-103">WCF Data Services 4.5</span></span>

<span data-ttu-id="ca750-104">WCF Data Services (прежнее название — "службы данных ADO.NET") — это компонент .NET Framework, который позволяет создавать службы, использующие Open Data Protocol (OData) для предоставления и использования данных в Интернете или интрасети с помощью семантики [передачи состояния представления (остальное)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span><span class="sxs-lookup"><span data-stu-id="ca750-104">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the Open Data Protocol (OData) to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm).</span></span> <span data-ttu-id="ca750-105">OData предоставляет доступ к данным в виде ресурсов, которые адресуются по URI.</span><span class="sxs-lookup"><span data-stu-id="ca750-105">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="ca750-106">Доступ и изменение данных производится с помощью таких стандартных команд HTTP, как GET, PUT, POST и DELETE.</span><span class="sxs-lookup"><span data-stu-id="ca750-106">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="ca750-107">OData использует соглашения об отношениях отношений сущностей [EDM](../adonet/entity-data-model.md) для предоставления ресурсов в виде наборов сущностей, связанных ассоциациями.</span><span class="sxs-lookup"><span data-stu-id="ca750-107">OData uses the entity-relationship conventions of the [Entity Data Model](../adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="ca750-108">WCF Data Services использует протокол OData для адресации и обновления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ca750-108">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="ca750-109">Таким образом, доступ к этим службам можно получить с любого клиента, поддерживающего OData.</span><span class="sxs-lookup"><span data-stu-id="ca750-109">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="ca750-110">OData позволяет запрашивать и записывать данные в ресурсы с помощью хорошо известных форматов передачи: Atom, набора стандартов для обмена и обновления данных в формате XML, а также нотация объектов JavaScript (JSON), основанный на тексте формат обмена данными, широко применяемый в приложениях AJAX.</span><span class="sxs-lookup"><span data-stu-id="ca750-110">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX applications.</span></span>

<span data-ttu-id="ca750-111">WCF Data Services может предоставлять данные, происходящие из различных источников, в качестве каналов OData.</span><span class="sxs-lookup"><span data-stu-id="ca750-111">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="ca750-112">Средства Visual Studio облегчают создание службы на основе OData с помощью модели данных ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ca750-112">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="ca750-113">Можно также создавать веб-каналы OData на основе классов среды CLR и даже данных с поздним связыванием или нетипизированными данными.</span><span class="sxs-lookup"><span data-stu-id="ca750-113">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="ca750-114">WCF Data Services также включает набор клиентских библиотек, один для общих .NET Framework клиентских приложений и другой специально для приложений на основе Silverlight.</span><span class="sxs-lookup"><span data-stu-id="ca750-114">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="ca750-115">Эти клиентские библиотеки предоставляют возможности объектно ориентированного программирования для доступа к каналу OData из таких платформ, как .NET Framework и Silverlight.</span><span class="sxs-lookup"><span data-stu-id="ca750-115">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="ca750-116">Подготовка к изучению темы</span><span class="sxs-lookup"><span data-stu-id="ca750-116">Where Should I Start?</span></span>

<span data-ttu-id="ca750-117">В зависимости от ваших интересов рекомендуется приступить к работе с WCF Data Services в одном из следующих разделов.</span><span class="sxs-lookup"><span data-stu-id="ca750-117">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="ca750-118">Необходимо перейти непосредственно к…</span><span class="sxs-lookup"><span data-stu-id="ca750-118">I want to jump right in...</span></span>

- [<span data-ttu-id="ca750-119">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="ca750-119">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="ca750-120">Начало работы</span><span class="sxs-lookup"><span data-stu-id="ca750-120">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="ca750-121">Просто покажите мне код...</span><span class="sxs-lookup"><span data-stu-id="ca750-121">Just show me some code...</span></span>

- [<span data-ttu-id="ca750-122">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="ca750-122">Quickstart</span></span>](quickstart-wcf-data-services.md)

- [<span data-ttu-id="ca750-123">Практическое руководство. Выполнение запросов к службе данных</span><span class="sxs-lookup"><span data-stu-id="ca750-123">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

- [<span data-ttu-id="ca750-124">Практическое руководство. Привязка данных к элементам Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="ca750-124">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="ca750-125">Я хочу узнать больше о OData...</span><span class="sxs-lookup"><span data-stu-id="ca750-125">I want to know more about OData...</span></span>

- [<span data-ttu-id="ca750-126">Технический документ. Введение в OData</span><span class="sxs-lookup"><span data-stu-id="ca750-126">White paper: Introducing OData</span></span>](https://download.microsoft.com/download/E/5/A/E5A59052-EE48-4D64-897B-5F7C608165B8/IntroducingOData.pdf)
- [<span data-ttu-id="ca750-127">Веб-сайт Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="ca750-127">Open Data Protocol website</span></span>](https://www.odata.org/)
- [<span data-ttu-id="ca750-128">OData SDK</span><span class="sxs-lookup"><span data-stu-id="ca750-128">OData: SDK</span></span>](https://www.odata.org/ecosystem/)

<span data-ttu-id="ca750-129">Я хочу просмотреть полный пример...</span><span class="sxs-lookup"><span data-stu-id="ca750-129">I want to see end-to-end samples...</span></span>

- <span data-ttu-id="ca750-130">[Краткое руководство по WCF Data Services](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span><span class="sxs-lookup"><span data-stu-id="ca750-130">[WCF Data Services Quickstart](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))</span></span>
- [<span data-ttu-id="ca750-131">Пакет SDK OData — пример кода</span><span class="sxs-lookup"><span data-stu-id="ca750-131">OData SDK - Sample Code</span></span>](https://www.odata.org/ecosystem/#sdk)

<span data-ttu-id="ca750-132">Как происходит интеграция со средствами Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ca750-132">How does it integrate with Visual Studio?</span></span>

- [<span data-ttu-id="ca750-133">Создание библиотеки клиентов службы данных</span><span class="sxs-lookup"><span data-stu-id="ca750-133">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)

- [<span data-ttu-id="ca750-134">Создание службы данных</span><span class="sxs-lookup"><span data-stu-id="ca750-134">Creating the Data Service</span></span>](creating-the-data-service.md)

- [<span data-ttu-id="ca750-135">Поставщик Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ca750-135">Entity Framework Provider</span></span>](entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="ca750-136">Что можно сделать?</span><span class="sxs-lookup"><span data-stu-id="ca750-136">What can I do with it?</span></span>

- [<span data-ttu-id="ca750-137">Обзор</span><span class="sxs-lookup"><span data-stu-id="ca750-137">Overview</span></span>](wcf-data-services-overview.md)

- [<span data-ttu-id="ca750-138">Сценарии приложений</span><span class="sxs-lookup"><span data-stu-id="ca750-138">Application Scenarios</span></span>](application-scenarios-wcf-data-services.md)

<span data-ttu-id="ca750-139">Я хочу использовать LINQ...</span><span class="sxs-lookup"><span data-stu-id="ca750-139">I want to use LINQ...</span></span>

- [<span data-ttu-id="ca750-140">Выполнение запросов к службе данных</span><span class="sxs-lookup"><span data-stu-id="ca750-140">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)

- [<span data-ttu-id="ca750-141">Рекомендации по LINQ</span><span class="sxs-lookup"><span data-stu-id="ca750-141">LINQ Considerations</span></span>](linq-considerations-wcf-data-services.md)

- [<span data-ttu-id="ca750-142">Практическое руководство. Выполнение запросов к службе данных</span><span class="sxs-lookup"><span data-stu-id="ca750-142">How to: Execute Data Service Queries</span></span>](how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="ca750-143">Мне по-прежнему нужны дополнительные сведения...</span><span class="sxs-lookup"><span data-stu-id="ca750-143">I still need some more information...</span></span>

- [<span data-ttu-id="ca750-144">Блог группы служб WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="ca750-144">WCF Data Services Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/astoriateam/)

- [<span data-ttu-id="ca750-145">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="ca750-145">Resources</span></span>](wcf-data-services-resources.md)

## <a name="in-this-section"></a><span data-ttu-id="ca750-146">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ca750-146">In This Section</span></span>

[<span data-ttu-id="ca750-147">Обзор</span><span class="sxs-lookup"><span data-stu-id="ca750-147">Overview</span></span>](wcf-data-services-overview.md)

<span data-ttu-id="ca750-148">Содержит общие сведения о функциях и функциях, доступных в WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="ca750-148">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

<span data-ttu-id="ca750-149">[Новые возможности WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span><span class="sxs-lookup"><span data-stu-id="ca750-149">[What's New in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))</span></span>

<span data-ttu-id="ca750-150">Описание новых функциональных возможностей WCF Data Services и поддержки новых функций OData.</span><span class="sxs-lookup"><span data-stu-id="ca750-150">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

[<span data-ttu-id="ca750-151">Начало работы</span><span class="sxs-lookup"><span data-stu-id="ca750-151">Getting Started</span></span>](getting-started-with-wcf-data-services.md)

<span data-ttu-id="ca750-152">Описывает, как предоставлять и использовать каналы OData с помощью WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="ca750-152">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

[<span data-ttu-id="ca750-153">Определение служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="ca750-153">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)

<span data-ttu-id="ca750-154">Описывает создание и настройку службы данных, предоставляющей доступ к каналам OData.</span><span class="sxs-lookup"><span data-stu-id="ca750-154">Describes how to create and configure a data service that exposes OData feeds.</span></span>

[<span data-ttu-id="ca750-155">Библиотека клиентов служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="ca750-155">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)

<span data-ttu-id="ca750-156">Описывает использование клиентских библиотек для использования каналов OData из клиентского приложения .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca750-156">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca750-157">См. также</span><span class="sxs-lookup"><span data-stu-id="ca750-157">See also</span></span>

- [<span data-ttu-id="ca750-158">Передача состояния представления (REST)</span><span class="sxs-lookup"><span data-stu-id="ca750-158">Representational State Transfer (REST)</span></span>](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)

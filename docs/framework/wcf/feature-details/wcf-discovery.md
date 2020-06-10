---
title: Обнаружение WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 63c6589cb2ecff9f0a5e7c8bb61b454f6516c98c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600183"
---
# <a name="wcf-discovery"></a><span data-ttu-id="67608-102">Обнаружение WCF</span><span class="sxs-lookup"><span data-stu-id="67608-102">WCF Discovery</span></span>
<span data-ttu-id="67608-103">Windows Communication Foundation (WCF) предоставляет поддержку для обеспечения возможности обнаружения служб во время выполнения с помощью протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="67608-103">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="67608-104">Службы WCF могут объявлять о доступности в сети с помощью многоадресного сообщения или прокси-сервера обнаружения.</span><span class="sxs-lookup"><span data-stu-id="67608-104">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="67608-105">Клиентские приложения могут осуществлять поиск служб, отвечающих набору указанных критериев, в сети или на прокси-сервере обнаружения.</span><span class="sxs-lookup"><span data-stu-id="67608-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="67608-106">В подразделах этого раздела представлены общие сведения и описание модели программирования данной функции.</span><span class="sxs-lookup"><span data-stu-id="67608-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="67608-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="67608-107">In This Section</span></span>  
 [<span data-ttu-id="67608-108">Общие сведения об обнаружении WCF</span><span class="sxs-lookup"><span data-stu-id="67608-108">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)  
 <span data-ttu-id="67608-109">Содержит общие сведения о поддержке WS-Discovery, предоставляемой WCF.</span><span class="sxs-lookup"><span data-stu-id="67608-109">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="67608-110">Модель объектов обнаружения WCF</span><span class="sxs-lookup"><span data-stu-id="67608-110">WCF Discovery Object Model</span></span>](wcf-discovery-object-model.md)  
 <span data-ttu-id="67608-111">Содержит описание классов объектной модели и расширяемости поддержки WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="67608-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="67608-112">Практическое руководство. Как программно добавить возможность обнаружения к службе и клиенту WCF</span><span class="sxs-lookup"><span data-stu-id="67608-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="67608-113">Показывает, как сделать службу Windows Communication Foundation (WCF) обнаруживаемой.</span><span class="sxs-lookup"><span data-stu-id="67608-113">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="67608-114">Реализация прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="67608-114">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)  
 <span data-ttu-id="67608-115">Содержит описание шагов, необходимых для реализации прокси-сервера обнаружения, службы, доступной для обнаружения, которая регистрируется на прокси-сервере обнаружения, и клиента, использующего прокси-сервер обнаружения для поиска этой службы.</span><span class="sxs-lookup"><span data-stu-id="67608-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="67608-116">Управление версиями обнаружения</span><span class="sxs-lookup"><span data-stu-id="67608-116">Discovery Versioning</span></span>](discovery-versioning.md)  
 <span data-ttu-id="67608-117">Содержит общие сведения о реализации прототипа некоторых новых функций обнаружения.</span><span class="sxs-lookup"><span data-stu-id="67608-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="67608-118">Также приводятся общие сведения о выборе версии обнаружения.</span><span class="sxs-lookup"><span data-stu-id="67608-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="67608-119">Настройка обнаружения в файле конфигурации</span><span class="sxs-lookup"><span data-stu-id="67608-119">Configuring Discovery in a Configuration File</span></span>](configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="67608-120">Настройка обнаружения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="67608-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="67608-121">Использование клиентского канала обнаружения</span><span class="sxs-lookup"><span data-stu-id="67608-121">Using the Discovery Client Channel</span></span>](using-the-discovery-client-channel.md)  
 <span data-ttu-id="67608-122">Показывает, как использовать клиентский канал обнаружения при записи клиентского приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="67608-122">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>

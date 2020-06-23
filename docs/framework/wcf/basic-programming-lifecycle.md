---
title: Базовый жизненный цикл программирования
description: Сведения о задачах для создания приложения WCF. WCF позволяет приложениям взаимодействовать на одном компьютере, в сетях или на разных платформах приложений.
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: c672827fff780fd263f5355520bb6ccf02bb902e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245535"
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="634f3-104">Базовый жизненный цикл программирования</span><span class="sxs-lookup"><span data-stu-id="634f3-104">Basic Programming Lifecycle</span></span>
<span data-ttu-id="634f3-105">Windows Communication Foundation (WCF) позволяет приложениям взаимодействовать независимо от того, находятся ли они на одном компьютере, через Интернет или на разных платформах приложений.</span><span class="sxs-lookup"><span data-stu-id="634f3-105">Windows Communication Foundation (WCF) enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="634f3-106">В этом разделе описаны задачи, необходимые для создания приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="634f3-106">This topic outlines the tasks that are required to build a WCF application.</span></span> <span data-ttu-id="634f3-107">Рабочий пример приложения см. в [руководстве по начало работы](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="634f3-107">For a working sample application, see [Getting Started Tutorial](getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="634f3-108">Основные задачи</span><span class="sxs-lookup"><span data-stu-id="634f3-108">The Basic Tasks</span></span>  
 <span data-ttu-id="634f3-109">Необходимо выполнить следующие основные задачи в указанном порядке:</span><span class="sxs-lookup"><span data-stu-id="634f3-109">The basic tasks to perform are, in order:</span></span>  
  
1. <span data-ttu-id="634f3-110">Определите контракт службы.</span><span class="sxs-lookup"><span data-stu-id="634f3-110">Define the service contract.</span></span> <span data-ttu-id="634f3-111">В контракте службы указывается ее сигнатура, отправляемые и получаемые ей данные и прочие данные, требуемые контрактом.</span><span class="sxs-lookup"><span data-stu-id="634f3-111">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> <span data-ttu-id="634f3-112">Дополнительные сведения см. в разделе [проектирование контрактов служб](designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="634f3-112">For more information, see [Designing Service Contracts](designing-service-contracts.md).</span></span>  
  
2. <span data-ttu-id="634f3-113">Реализуйте контракт.</span><span class="sxs-lookup"><span data-stu-id="634f3-113">Implement the contract.</span></span> <span data-ttu-id="634f3-114">Для реализации контракта службы создайте класс, который реализует этот контракт, и укажите пользовательские режимы работы, которые должна иметь среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="634f3-114">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> <span data-ttu-id="634f3-115">Дополнительные сведения см. в разделе [реализация контрактов служб](implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="634f3-115">For more information, see [Implementing Service Contracts](implementing-service-contracts.md).</span></span>  
  
3. <span data-ttu-id="634f3-116">Настройте службу, указав конечные точки и определив прочие сведения о режимах работы.</span><span class="sxs-lookup"><span data-stu-id="634f3-116">Configure the service by specifying endpoints and other behavior information.</span></span> <span data-ttu-id="634f3-117">Дополнительные сведения см. в разделе [Настройка служб](configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="634f3-117">For more information, see [Configuring Services](configuring-services.md).</span></span>  
  
4. <span data-ttu-id="634f3-118">Разместите службу.</span><span class="sxs-lookup"><span data-stu-id="634f3-118">Host the service.</span></span> <span data-ttu-id="634f3-119">Дополнительные сведения см. в разделе [службы хостинга](hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="634f3-119">For more information, see [Hosting Services](hosting-services.md).</span></span>  
  
5. <span data-ttu-id="634f3-120">Создайте клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="634f3-120">Build a client application.</span></span> <span data-ttu-id="634f3-121">Дополнительные сведения см. в разделе [Создание клиентов](building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="634f3-121">For more information, see [Building Clients](building-clients.md).</span></span>  
  
 <span data-ttu-id="634f3-122">Несмотря на то что подразделы этого раздела приведены именно в таком порядке, некоторые сценарии не начинаются с самого начала.</span><span class="sxs-lookup"><span data-stu-id="634f3-122">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="634f3-123">Например, если требуется создать клиент для существующей службы, следует начать с шага 5.</span><span class="sxs-lookup"><span data-stu-id="634f3-123">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="634f3-124">При создании службы, которая будет использоваться другими службами, можно пропустить шаг 5.</span><span class="sxs-lookup"><span data-stu-id="634f3-124">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="634f3-125">После ознакомления с разработкой контрактов служб вы также можете ознакомиться с [введением в расширяемость](introduction-to-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="634f3-125">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](introduction-to-extensibility.md).</span></span> <span data-ttu-id="634f3-126">Если у вас возникли проблемы со службой, ознакомьтесь с [кратким руководством по устранению неполадок WCF](wcf-troubleshooting-quickstart.md) , чтобы узнать, не возникли ли другие проблемы.</span><span class="sxs-lookup"><span data-stu-id="634f3-126">If you have problems with your service, check [WCF Troubleshooting Quickstart](wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="634f3-127">См. также</span><span class="sxs-lookup"><span data-stu-id="634f3-127">See also</span></span>

- [<span data-ttu-id="634f3-128">Реализация контрактов служб</span><span class="sxs-lookup"><span data-stu-id="634f3-128">Implementing Service Contracts</span></span>](implementing-service-contracts.md)

---
title: Перехватчики (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: 64c5c82f33daf677e58d49655897c392f1f7b7f9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204402"
---
# <a name="interceptors-wcf-data-services"></a><span data-ttu-id="44464-102">Перехватчики (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="44464-102">Interceptors (WCF Data Services)</span></span>

<span data-ttu-id="44464-103">WCF Data Services позволяет приложению перехватывать сообщения запроса, чтобы можно было добавить в операцию пользовательскую логику.</span><span class="sxs-lookup"><span data-stu-id="44464-103">WCF Data Services enables an application to intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="44464-104">Эта логика может применяться для проверки данных во входящих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="44464-104">You can use this custom logic to validate data in incoming messages.</span></span> <span data-ttu-id="44464-105">Можно также дальнейшим образом ограничить область запроса, например вставить специализированные правила проверки подлинности на основе отдельных запросов.</span><span class="sxs-lookup"><span data-stu-id="44464-105">You can also use it to further restrict the scope of a query request, such as to insert a custom authorization policy on a per request basis.</span></span>  
  
 <span data-ttu-id="44464-106">Перехват выполняется методами службы данных со специальными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="44464-106">Interception is performed by specially attributed methods in the data service.</span></span> <span data-ttu-id="44464-107">Эти методы вызываются WCF Data Services в соответствующей точке обработки сообщения.</span><span class="sxs-lookup"><span data-stu-id="44464-107">These methods are called by WCF Data Services at the appropriate point in message processing.</span></span> <span data-ttu-id="44464-108">Перехватчики определяются индивидуально для наборов сущностей. Методы перехватчика, в отличие от операций службы, не принимают параметры из запроса.</span><span class="sxs-lookup"><span data-stu-id="44464-108">Interceptors are defined on a per-entity set basis, and interceptor methods cannot accept parameters from the request like service operations can.</span></span> <span data-ttu-id="44464-109">Методы перехвата запросов, которые вызываются при обработке запросов HTTP GET, должны возвращать лямбда-выражение, определяющее, должен ли экземпляр набора сущностей перехватчика возвращаться в результатах запроса.</span><span class="sxs-lookup"><span data-stu-id="44464-109">Query interceptor methods, which are called when processing an HTTP GET request, must return a lambda expression that determines whether an instance of the interceptor's entity set should be returned by the query results.</span></span> <span data-ttu-id="44464-110">Это выражение используется службой данных для дальнейшего уточнения запрошенного действия.</span><span class="sxs-lookup"><span data-stu-id="44464-110">This expression is used by the data service to further refine the requested operation.</span></span> <span data-ttu-id="44464-111">В следующем примере рассмотрено определение перехватчика запроса.</span><span class="sxs-lookup"><span data-stu-id="44464-111">The following is an example definition of a query interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 <span data-ttu-id="44464-112">Дополнительные сведения см. [в разделе как перехватывать сообщения службы данных](how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="44464-112">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="44464-113">Перехватчики изменений, которые вызываются при обработке операций, не связанных с запросами, должны возвращать значение `void` (`Nothing` в коде Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="44464-113">Change interceptors, which are called when processing non-query operations, must return `void` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="44464-114">Методы перехватчика изменений должны принимать следующие два параметра.</span><span class="sxs-lookup"><span data-stu-id="44464-114">Change interceptor methods must accept the following two parameters:</span></span>  
  
1. <span data-ttu-id="44464-115">Параметр типа, совместимого с типом сущностей в наборе сущностей.</span><span class="sxs-lookup"><span data-stu-id="44464-115">A parameter of a type that is compatible with the entity type of the entity set.</span></span> <span data-ttu-id="44464-116">При вызове службой данных перехватчика изменений значение этого параметра будет отражать сведения о сущности, отправленные в запросе.</span><span class="sxs-lookup"><span data-stu-id="44464-116">When the data service invokes the change interceptor, the value of this parameter will reflect the entity information that is sent by the request.</span></span>  
  
2. <span data-ttu-id="44464-117">Параметр типа <xref:System.Data.Services.UpdateOperations>.</span><span class="sxs-lookup"><span data-stu-id="44464-117">A parameter of type <xref:System.Data.Services.UpdateOperations>.</span></span> <span data-ttu-id="44464-118">При вызове службой данных перехватчика изменений значение этого параметра будет отражать операцию, которую пытается выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="44464-118">When the data service invokes the change interceptor, the value of this parameter will reflect the operation that the request is trying to perform.</span></span>  
  
 <span data-ttu-id="44464-119">В следующем примере рассмотрено определение перехватчика изменений.</span><span class="sxs-lookup"><span data-stu-id="44464-119">The following is an example definition of a change interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 <span data-ttu-id="44464-120">Дополнительные сведения см. [в разделе как перехватывать сообщения службы данных](how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="44464-120">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="44464-121">Для перехватчиков поддерживаются следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="44464-121">The following attributes are supported for interception.</span></span>  
  
 <span data-ttu-id="44464-122">**[Куеринтерцептор (** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="44464-122">**[QueryInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="44464-123">Методы с атрибутом <xref:System.Data.Services.QueryInterceptorAttribute> вызываются при получении запроса HTTP GET к целевому ресурсу набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="44464-123">Methods with the <xref:System.Data.Services.QueryInterceptorAttribute> attribute applied are called when an HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="44464-124">Эти методы всегда должны возвращать лямбда-выражение в форме `Expression<Func<T,bool>>`.</span><span class="sxs-lookup"><span data-stu-id="44464-124">These methods must always return a lambda expression in the form of `Expression<Func<T,bool>>`.</span></span>  
  
 <span data-ttu-id="44464-125">**[Чанжеинтерцептор (** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="44464-125">**[ChangeInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="44464-126">Методы с атрибутом <xref:System.Data.Services.ChangeInterceptorAttribute> вызываются при получении запроса HTTP, отличного от HTTP GET, к целевому ресурсу набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="44464-126">Methods with the <xref:System.Data.Services.ChangeInterceptorAttribute> attribute applied are called when an HTTP request other than HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="44464-127">Эти методы должны всегда возвращать значение `void` (`Nothing` в коде Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="44464-127">These methods must always return `void` (`Nothing` in Visual Basic).</span></span>  
  
 <span data-ttu-id="44464-128">Дополнительные сведения см. [в разделе как перехватывать сообщения службы данных](how-to-intercept-data-service-messages-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="44464-128">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44464-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="44464-129">See also</span></span>

- [<span data-ttu-id="44464-130">Операции служб</span><span class="sxs-lookup"><span data-stu-id="44464-130">Service Operations</span></span>](service-operations-wcf-data-services.md)

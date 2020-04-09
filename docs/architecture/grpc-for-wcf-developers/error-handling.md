---
title: Обработка ошибок - gRPC для разработчиков WCF
description: Темы, относящиеся к обработке ошибок в gRPC. Включает таблицу наиболее часто используемых кодов статуса.
ms.date: 09/02/2019
ms.openlocfilehash: 64a2355a8bd608c074f9bc420312b23aba0c1fb2
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988951"
---
# <a name="error-handling"></a><span data-ttu-id="e323f-104">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="e323f-104">Error handling</span></span>

<span data-ttu-id="e323f-105">Фонд связи Windows (WCF) использует <xref:System.ServiceModel.FaultException%601> и [FaultContract](xref:System.ServiceModel.FaultContractAttribute) для предоставления подробной информации об ошибках, включая поддержку стандарта неисправности SOAP.</span><span class="sxs-lookup"><span data-stu-id="e323f-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="e323f-106">К сожалению, в текущей версии gRPC отсутствует сложность, найденная с WCF, и только имеет ограниченную встроенную обработку ошибок на основе простых кодов статуса и метаданных.</span><span class="sxs-lookup"><span data-stu-id="e323f-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="e323f-107">Следующая таблица представляет собой краткое руководство по наиболее часто используемым кодов статуса:</span><span class="sxs-lookup"><span data-stu-id="e323f-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="e323f-108">Код состояния</span><span class="sxs-lookup"><span data-stu-id="e323f-108">Status code</span></span> | <span data-ttu-id="e323f-109">Проблема</span><span class="sxs-lookup"><span data-stu-id="e323f-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="e323f-110">Метод не написан.</span><span class="sxs-lookup"><span data-stu-id="e323f-110">Method hasn't been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="e323f-111">Проблема со всем обслуживанием.</span><span class="sxs-lookup"><span data-stu-id="e323f-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="e323f-112">Недействительный ответ.</span><span class="sxs-lookup"><span data-stu-id="e323f-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="e323f-113">Проблема с кодированием/расшифровкой.</span><span class="sxs-lookup"><span data-stu-id="e323f-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="e323f-114">Ошибка проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e323f-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="e323f-115">Ошибка авторизации.</span><span class="sxs-lookup"><span data-stu-id="e323f-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="e323f-116">Звонок был отменен, как правило, абонентом.</span><span class="sxs-lookup"><span data-stu-id="e323f-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="e323f-117">Повышение ошибок в ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="e323f-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="e323f-118">Служба ASP.NET Core gRPC может отправить ответ `RpcException`на ошибку, бросив , который может быть пойман клиентом, как если бы он был в том же процессе.</span><span class="sxs-lookup"><span data-stu-id="e323f-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="e323f-119">Необходимо `RpcException` включить код статуса и описание, и может по желанию включать метаданные и более длинное сообщение исключения.</span><span class="sxs-lookup"><span data-stu-id="e323f-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="e323f-120">Метаданные могут использоваться для отправки вспомогательных данных, подобно тому, как `FaultContract` объекты могут нести дополнительные данные для ошибок WCF.</span><span class="sxs-lookup"><span data-stu-id="e323f-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var user = context.GetHttpContext().User;
    if (!ValidateUser(user))
    {
        var metadata = new Metadata
        {
            { "User", user.Identity.Name }
        };
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Permission denied"), metadata);
    }
}
```

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="e323f-121">Поймать ошибки в gRPC клиентов</span><span class="sxs-lookup"><span data-stu-id="e323f-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="e323f-122">Так же, как <xref:System.ServiceModel.FaultException%601> клиенты WCF могут ловить `RpcException` ошибки, клиент gRPC может поймать для обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="e323f-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="e323f-123">Поскольку `RpcException` не является общим типом, вы не можете поймать различные типы ошибок в разных блоках.</span><span class="sxs-lookup"><span data-stu-id="e323f-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="e323f-124">Но можно использовать функцию *фильтров исключений* C's для декларирования отдельных `catch` блоков для различных кодов статусов, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e323f-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

```csharp
try
{
    var portfolio = await client.GetPortfolioAsync(new GetPortfolioRequest { Id = id });
}
catch (RpcException ex) when (ex.StatusCode == StatusCode.PermissionDenied)
{
    var userEntry = ex.Trailers.FirstOrDefault(e => e.Key == "User");
    Console.WriteLine($"User '{userEntry.Value}' does not have permission to view this portfolio.");
}
catch (RpcException)
{
    // Handle any other error type ...
}
```

> [!IMPORTANT]
> <span data-ttu-id="e323f-125">При предоставлении дополнительных метаданных об ошибках обязательно задокументируйте соответствующие ключи и значения `.proto` в документации API или в комментариях в файле.</span><span class="sxs-lookup"><span data-stu-id="e323f-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="e323f-126">gRPC богаче модель ошибки</span><span class="sxs-lookup"><span data-stu-id="e323f-126">gRPC richer error model</span></span>

<span data-ttu-id="e323f-127">Google разработала [более богатую модель ошибок,](https://cloud.google.com/apis/design/errors#error_model) которая больше похожа на [WCF в FaultContract](xref:System.ServiceModel.FaultContractAttribute), но эта модель не поддерживается в C » еще.</span><span class="sxs-lookup"><span data-stu-id="e323f-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="e323f-128">В настоящее время он доступен только для Go, Java, Python и C..</span><span class="sxs-lookup"><span data-stu-id="e323f-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e323f-129">[Назад](metadata.md)
>[Вперед](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="e323f-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>

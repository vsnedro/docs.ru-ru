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
# <a name="error-handling"></a>Обработка ошибок

Фонд связи Windows (WCF) использует <xref:System.ServiceModel.FaultException%601> и [FaultContract](xref:System.ServiceModel.FaultContractAttribute) для предоставления подробной информации об ошибках, включая поддержку стандарта неисправности SOAP.

К сожалению, в текущей версии gRPC отсутствует сложность, найденная с WCF, и только имеет ограниченную встроенную обработку ошибок на основе простых кодов статуса и метаданных. Следующая таблица представляет собой краткое руководство по наиболее часто используемым кодов статуса:

| Код состояния | Проблема |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | Метод не написан. |
| `GRPC_STATUS_UNAVAILABLE` | Проблема со всем обслуживанием. |
| `GRPC_STATUS_UNKNOWN` | Недействительный ответ. |
| `GRPC_STATUS_INTERNAL` | Проблема с кодированием/расшифровкой. |
| `GRPC_STATUS_UNAUTHENTICATED` | Ошибка проверки подлинности. |
| `GRPC_STATUS_PERMISSION_DENIED` | Ошибка авторизации. |
| `GRPC_STATUS_CANCELLED` | Звонок был отменен, как правило, абонентом. |

## <a name="raise-errors-in-aspnet-core-grpc"></a>Повышение ошибок в ASP.NET Core gRPC

Служба ASP.NET Core gRPC может отправить ответ `RpcException`на ошибку, бросив , который может быть пойман клиентом, как если бы он был в том же процессе. Необходимо `RpcException` включить код статуса и описание, и может по желанию включать метаданные и более длинное сообщение исключения. Метаданные могут использоваться для отправки вспомогательных данных, подобно тому, как `FaultContract` объекты могут нести дополнительные данные для ошибок WCF.

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

## <a name="catch-errors-in-grpc-clients"></a>Поймать ошибки в gRPC клиентов

Так же, как <xref:System.ServiceModel.FaultException%601> клиенты WCF могут ловить `RpcException` ошибки, клиент gRPC может поймать для обработки ошибок. Поскольку `RpcException` не является общим типом, вы не можете поймать различные типы ошибок в разных блоках. Но можно использовать функцию *фильтров исключений* C's для декларирования отдельных `catch` блоков для различных кодов статусов, как показано в следующем примере:

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
> При предоставлении дополнительных метаданных об ошибках обязательно задокументируйте соответствующие ключи и значения `.proto` в документации API или в комментариях в файле.

## <a name="grpc-richer-error-model"></a>gRPC богаче модель ошибки

Google разработала [более богатую модель ошибок,](https://cloud.google.com/apis/design/errors#error_model) которая больше похожа на [WCF в FaultContract](xref:System.ServiceModel.FaultContractAttribute), но эта модель не поддерживается в C » еще. В настоящее время он доступен только для Go, Java, Python и C..

>[!div class="step-by-step"]
>[Назад](metadata.md)
>[Вперед](ws-protocols.md)

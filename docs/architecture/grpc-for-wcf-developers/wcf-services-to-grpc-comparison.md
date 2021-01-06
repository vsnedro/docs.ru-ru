---
title: Сравнение WCF с gRPC-gRPC для разработчиков WCF
description: Сравнение платформ WCF и gRPC для создания распределенных приложений.
ms.date: 12/15/2020
ms.openlocfilehash: 7dd41c3d6f248bb1ef5eacb323b1443c7bc575a7
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938498"
---
# <a name="comparing-wcf-to-grpc"></a>Сравнение WCF и gRPC

В предыдущей главе вы узнаете о protobuf и том, как gRPC обрабатывает сообщения. Прежде чем выполнять подробное преобразование из Windows Communication Foundation (WCF) в gRPC, важно понять, как функции, доступные в WCF, обрабатываются в gRPC и какие обходные пути можно использовать при отсутствии эквивалента gRPC. В частности, в этой главе рассматриваются следующие темы:

- Операции и методы
- Привязки и транспорты
- Типы RPC
- Метаданные
- Обработка ошибок
- WS- \* Protocols

## <a name="grpc-example"></a>Пример gRPC

При создании нового проекта ASP.NET Core 5,0 gRPC из Visual Studio 2019 или командной строки для вас создается gRPC эквивалент "Hello World". Он состоит из `greeter.proto` файла, который определяет службу и ее сообщения, а также `GreeterService.cs` файл с реализацией службы.

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message that contains the user's name.
message HelloRequest {
  string name = 1;
}

// The response message that contains the greetings.
message HelloReply {
  string message = 1;
}
```

```csharp
using System.Threading.Tasks;
using Grpc.Core;
using Microsoft.Extensions.Logging;

namespace HelloGrpc
{
    public class GreeterService : Greeter.GreeterBase
    {
        private readonly ILogger<GreeterService> _logger;
        public GreeterService(ILogger<GreeterService> logger)
        {
            _logger = logger;
        }

        public override Task<HelloReply> SayHello(HelloRequest request, ServerCallContext context)
        {
            return Task.FromResult(new HelloReply
            {
                Message = "Hello " + request.Name
            });
        }
    }
}
```

В этой главе мы рассмотрим этот пример кода при объяснении различных концепций и функций gRPC.

>[!div class="step-by-step"]
>[Назад](protobuf-maps.md)
>[Вперед](wcf-endpoints-grpc-methods.md)

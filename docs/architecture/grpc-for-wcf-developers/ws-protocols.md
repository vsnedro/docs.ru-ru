---
title: Протоколы WS-* — gRPC для разработчиков WCF
description: Ознакомьтесь с протоколами WS-*, поддерживаемыми WCF, и альтернативами, доступными в gRPC
author: markrendle
ms.date: 12/15/2020
ms.openlocfilehash: d6fffdd5153c799c78ad949a3b16fa72e9612e43
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938485"
---
# <a name="ws--protocols"></a>WS- \* Protocols

Одним из реальных преимуществ работы с Windows Communication Foundation (WCF) было поддержка множества существующих протоколов _WS- \*_ Standard. В этом разделе кратко рассматривается, как gRPC управляет одними и теми же WS- \* Protocols, и обсуждаются возможности, доступные при отсутствии альтернативы.

## <a name="metadata-exchange-ws-policy-ws-discovery-and-so-on"></a>Обмен метаданными: WS-Policy, WS-Discovery и т. д.

Службы SOAP предоставляют документы схемы языка описания веб-служб (WSDL) со сведениями, такими как форматы данных, операции или варианты обмена данными. Эту схему можно использовать для создания клиентского кода.

gRPC лучше всего подходит, когда серверы и клиенты создаются из одних и тех же `.proto` файлов, но дополнительное расширение серверного отражения предоставляет способ предоставления динамической информации с работающего сервера. Дополнительные сведения см. в разделе пакет NuGet [GRPC. Reflection](https://nuget.org/packages/Grpc.Reflection) и статья о [серверном отражении GRPC C#](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md) .

Протокол WS-Discovery используется для нахождение служб в локальной сети. службы gRPC находятся в DNS или реестре службы, например Consul или ZooKeeper.

## <a name="security-ws-security-ws-federation-xml-encryption-and-so-on"></a>Безопасность: WS-Security, WS-Federation, шифрование XML и т. д.

Сведения о безопасности, проверке подлинности и авторизации более подробно описаны в [главе 6](security.md). Но стоит отметить, что, в отличие от WCF, gRPC не поддерживает шифрование WS-Security, WS-Federation или XML. Несмотря на это, gRPC обеспечивает отличную безопасность. Весь сетевой трафик gRPC автоматически шифруется при использовании HTTP/2 через TLS. Сертификаты X509 можно использовать для взаимной проверки подлинности клиента или сервера.

## <a name="ws-reliablemessaging"></a>WS-ReliableMessaging

gRPC не предоставляет эквивалент WS-ReliableMessaging. Семантика повторных попыток должна обрабатываться в коде, возможно, с такой библиотекой, как [Polly](https://github.com/App-vNext/Polly). При работе в Kubernetes или аналогичных средах оркестрации [сети служб](service-mesh.md) также могут помочь обеспечить надежный обмен сообщениями между службами.

## <a name="ws-transaction-ws-coordination"></a>WS-Transaction, WS-Coordination

Реализация распределенных транзакций в WCF использует Microsoft координатор распределенных транзакций (MSDTC). Он работает с диспетчерами ресурсов, которые специально поддерживают такие службы, как SQL Server, MSMQ или файловые системы Windows. В современных микрослужбах нет эквивалента, часть из-за широкого спектра используемых технологий. Обсуждение транзакций см. [в приложении а](appendix.md).

>[!div class="step-by-step"]
>[Назад](error-handling.md)
>[Вперед](migrate-wcf-to-grpc.md)

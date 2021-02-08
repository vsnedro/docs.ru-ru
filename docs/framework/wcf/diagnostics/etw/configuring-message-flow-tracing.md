---
description: 'Дополнительные сведения: Настройка трассировки потока сообщений'
title: Настройка отслеживания потока сообщений
ms.date: 03/30/2017
ms.assetid: 15571ca2-bee2-47fb-ba10-fcbc09152ad0
ms.openlocfilehash: c91362ca0d0a8fd83f69c6988d2ad2786b08b339
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798853"
---
# <a name="configuring-message-flow-tracing"></a>Настройка отслеживания потока сообщений

Если включена трассировка активности Windows Communication Foundation (WCF), идентификаторы действий должны назначаться логическим действиям во всем стеке WCF. Платформа [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] включает более высокопроизводительную версию этой функции, которая поддерживает работу со средством трассировкой событий для Windows, называемой трассировкой потока сообщений. При ее включении полные идентификаторы действий извлекаются (или назначаются при их отсутствии) и распространяются для всех событий трассировки, которые создаются после того, как канал декодировал сообщение. Клиенты могут использовать эту функцию для воссоздания потоков сообщений с журналами трассировки от различных служб после декодирования.  
  
 Трассировку можно включить после обнаружения проблемы в работе приложения, а затем отключить после разрешения проблемы.  
  
## <a name="enabling-tracing"></a>Включение трассировки  

 Чтобы включить трассировку потока сообщений, установите элемент конфигурации .NET Framework 4 `messageFlowTracing` в значение `true`, как показано в следующем примере.  
  
```xml  
<system.servicemodel>  
  <diagnostics>  
    <endToEndTracing propagateActivity="true" messageFlowTracing="true" />  
  </diagnostics>  
</system.servicemodel>  
```  
  
> [!NOTE]
> Поскольку элемент конфигурации `endToEndTracing` находится в файле Web.config, его нельзя динамично изменять таким же образом, как и трассировку событий Windows. Чтобы изменение параметра `endToEndTracing` вступило в силу, необходимо выполнить очистку приложения.  
  
 Действия связываются путем обмена идентификаторами действия. Эти идентификаторы являются идентификаторами GUID и формируются классом System.Diagnostics.CorrelationManager. При изменении идентификатора System.Diagnostics.Trace.CorrelationManager.ActivityID не забудьте вернуть идентификатору исходное значение, передавая управление обратно в код WCF.  Кроме того, если используется асинхронная программная модель WCF, не забывайте передавать идентификатор System.Diagnostics.Trace.CorrelationManager.ActivityID между потоками.  
  
## <a name="message-flow-tracing-and-rest-services"></a>Трассировка потока сообщений и службы REST  

 Трассировка потока сообщений позволяет выполнять сквозную трассировку запроса.  В службах на основе SOAP идентификатор действия отправляется в заголовке сообщения SOAP. Запросы REST не содержат этот заголовок, поэтому взамен используется заголовок события HTTP. В следующем фрагменте кода показано, как можно программно получить значение идентификатора действия:  
  
```csharp
Object output = null;
if (OperationContext.Current.IncomingMessageProperties.TryGetValue(HttpRequestMessageProperty.Name, out output))
{
   HttpRequestMessageProperty httpHeaders = output as HttpRequestMessageProperty;
   // Retrieve the Activity Id from the HTTP header    string e2eId = httpHeaders.Headers["E2EActivity"];
   // ...
}
```

 Можно программно добавить заголовок с помощью следующего кода:  
  
```csharp  
HttpContent content = new StreamContent(contentStream);  
Guid correlation = Guid.NewGuid();  
content.Headers.Add("E2EActivity", Convert.ToBase64String(correlation.ToByteArray()));  
```

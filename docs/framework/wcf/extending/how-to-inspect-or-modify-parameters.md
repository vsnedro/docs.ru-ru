---
title: Практическое руководство. Проверка или изменение параметров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
ms.openlocfilehash: e8b2674d8efc0ef3ac2f1dd6ab0df559195c274c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249037"
---
# <a name="how-to-inspect-or-modify-parameters"></a><span data-ttu-id="8c619-102">Практическое руководство. Проверка или изменение параметров</span><span class="sxs-lookup"><span data-stu-id="8c619-102">How to: Inspect or Modify Parameters</span></span>

<span data-ttu-id="8c619-103">Вы можете проверить или изменить входящие или исходящие сообщения для одной операции в клиентском объекте Windows Communication Foundation (WCF) или WCF, реализовав <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> интерфейс и вставив его в клиентскую среду или службу среды выполнения службы.</span><span class="sxs-lookup"><span data-stu-id="8c619-103">You can inspect or modify the incoming or outgoing messages for a single operation on a Windows Communication Foundation (WCF) client object or a WCF service by implementing the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface and inserting it into the client or service runtime.</span></span> <span data-ttu-id="8c619-104">Как правило, для добавления инспекторов параметров для отдельной операции используется поведение операции; другие поведения могут использоваться для обеспечения быстрого доступа к среде выполнения в более широкой области действия.</span><span class="sxs-lookup"><span data-stu-id="8c619-104">Typically an operation behavior is used to add parameter inspectors for a single operation; other behaviors can be used to provide easy access to the runtime at a greater scope.</span></span> <span data-ttu-id="8c619-105">Дополнительные сведения см. в разделе [расширение клиентов](extending-clients.md) и [Расширение диспетчеров](extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="8c619-105">For more information, see [Extending Clients](extending-clients.md) and [Extending Dispatchers](extending-dispatchers.md).</span></span>  
  
### <a name="inspecting-or-modifying-parameters"></a><span data-ttu-id="8c619-106">Проверка или изменение параметров</span><span class="sxs-lookup"><span data-stu-id="8c619-106">Inspecting or Modifying Parameters</span></span>  
  
1. <span data-ttu-id="8c619-107">Реализовать интерфейс <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c619-107">Implement the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="8c619-108">Реализуйте поведение <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (в зависимости от того, какая требуется область действия), чтобы добавить инспектор параметров в свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c619-108">Implement a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (depending upon the required scope) to add your parameter inspector to either the <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> or <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> properties.</span></span>  
  
3. <span data-ttu-id="8c619-109">Вставьте поведение до вызова метода <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> в производство каналов <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c619-109">Insert your behavior prior to calling <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8c619-110">Дополнительные сведения см. [в разделе Настройка и расширение среды выполнения с помощью поведений](configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="8c619-110">For details, see [Configuring and Extending the Runtime with Behaviors](configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c619-111">Пример</span><span class="sxs-lookup"><span data-stu-id="8c619-111">Example</span></span>  

 <span data-ttu-id="8c619-112">В следующих примерах кода показаны, по порядку:</span><span class="sxs-lookup"><span data-stu-id="8c619-112">The following code examples show, in order:</span></span>  
  
- <span data-ttu-id="8c619-113">реализация инспектора параметров;</span><span class="sxs-lookup"><span data-stu-id="8c619-113">A parameter inspector implementation.</span></span>  
  
- <span data-ttu-id="8c619-114">реализация поведения, вставляющего инспектор параметров с помощью <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> и <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>;</span><span class="sxs-lookup"><span data-stu-id="8c619-114">The behavior implementation that inserts the parameter inspector using a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, and an <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="8c619-115">файл конфигурации, который загружает и запускает поведение конечной точки в клиентском приложении для вставки инспектора параметров в клиент.</span><span class="sxs-lookup"><span data-stu-id="8c619-115">A configuration file that loads and runs the endpoint behavior in a client application to insert the parameter inspector on the client.</span></span>  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8c619-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8c619-116">See also</span></span>

- [<span data-ttu-id="8c619-117">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="8c619-117">Configuring and Extending the Runtime with Behaviors</span></span>](configuring-and-extending-the-runtime-with-behaviors.md)

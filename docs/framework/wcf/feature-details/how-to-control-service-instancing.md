---
title: Практическое руководство. Управление созданием экземпляров служб
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: 8a73dd90d268c61e0df974861753119e205a870f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599078"
---
# <a name="how-to-control-service-instancing"></a><span data-ttu-id="dfff4-102">Практическое руководство. Управление созданием экземпляров служб</span><span class="sxs-lookup"><span data-stu-id="dfff4-102">How to: Control Service Instancing</span></span>
<span data-ttu-id="dfff4-103">Установка режима экземпляра службы позволяет определить, когда будет создаваться объект <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (и связанный с ним определяемый пользователем объект службы).</span><span class="sxs-lookup"><span data-stu-id="dfff4-103">Setting the instance mode of a service enables you to specify when a <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (and its associated user-defined service object) is created.</span></span> <span data-ttu-id="dfff4-104">Возможные режимы см. в перечислении <xref:System.ServiceModel.InstanceContextMode>.</span><span class="sxs-lookup"><span data-stu-id="dfff4-104">See the <xref:System.ServiceModel.InstanceContextMode> enumeration for the possible modes.</span></span> <span data-ttu-id="dfff4-105">Дополнительные сведения о поведении см. [в разделе Настройка и расширение среды выполнения с помощью поведений](../extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="dfff4-105">For more information about behaviors, see [Configuring and Extending the Runtime with Behaviors](../extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span> <span data-ttu-id="dfff4-106">Рабочие примеры см. в разделе [варианты поведения](../samples/behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="dfff4-106">For working examples, see [Behaviors](../samples/behaviors.md).</span></span>  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a><span data-ttu-id="dfff4-107">Управление временем существования экземпляра службы с помощью кода</span><span class="sxs-lookup"><span data-stu-id="dfff4-107">To control the service instance lifetime using code</span></span>  
  
1. <span data-ttu-id="dfff4-108">Примените атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> к классу службы.</span><span class="sxs-lookup"><span data-stu-id="dfff4-108">Apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> to the service class.</span></span>  
  
2. <span data-ttu-id="dfff4-109">Присвойте свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> одно из следующих значений: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession> или <xref:System.ServiceModel.InstanceContextMode.Single>.</span><span class="sxs-lookup"><span data-stu-id="dfff4-109">Set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property to one of the following values: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, or <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span>  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="dfff4-110">Пример</span><span class="sxs-lookup"><span data-stu-id="dfff4-110">Example</span></span>  
 <span data-ttu-id="dfff4-111">В следующем примере кода свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> атрибута <xref:System.ServiceModel.ServiceBehaviorAttribute> присваивается значение <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span><span class="sxs-lookup"><span data-stu-id="dfff4-111">The following code example sets the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property of the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span></span>  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="dfff4-112">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="dfff4-112">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>
- <xref:System.ServiceModel.InstanceContextMode>
- [<span data-ttu-id="dfff4-113">Служба: примеры поведения</span><span class="sxs-lookup"><span data-stu-id="dfff4-113">Service: Behaviors Samples</span></span>](../samples/behaviors.md)

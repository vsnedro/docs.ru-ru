---
description: Дополнительные сведения о том, как управлять созданием экземпляров службы.
title: Практическое руководство. Управление созданием экземпляров служб
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: 014d7fb4b054a1b52c1fea671cd099267fba468c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779924"
---
# <a name="how-to-control-service-instancing"></a>Практическое руководство. Управление созданием экземпляров служб

Установка режима экземпляра службы позволяет определить, когда будет создаваться объект <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (и связанный с ним определяемый пользователем объект службы). Возможные режимы см. в перечислении <xref:System.ServiceModel.InstanceContextMode>. Дополнительные сведения о поведении см. [в разделе Настройка и расширение среды выполнения с помощью поведений](../extending/configuring-and-extending-the-runtime-with-behaviors.md). Рабочие примеры см. в разделе [варианты поведения](../samples/behaviors.md).  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a>Управление временем существования экземпляра службы с помощью кода  
  
1. Примените атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> к классу службы.  
  
2. Присвойте свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> одно из следующих значений: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession> или <xref:System.ServiceModel.InstanceContextMode.Single>.  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a>Пример  

 В следующем примере кода свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> атрибута <xref:System.ServiceModel.ServiceBehaviorAttribute> присваивается значение <xref:System.ServiceModel.InstanceContextMode.PerCall>.  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>
- <xref:System.ServiceModel.InstanceContextMode>
- [Служба: примеры поведения](../samples/behaviors.md)

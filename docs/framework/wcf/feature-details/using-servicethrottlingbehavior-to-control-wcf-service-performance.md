---
description: 'Дополнительные сведения: использование Сервицесроттлингбехавиор для управления производительностью службы WCF'
title: Использование ServiceThrottlingBehavior для управления производительностью службы WCF
ms.date: 03/30/2017
helpviewer_keywords:
- behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
ms.openlocfilehash: 4a53c89c6b17402b7dd32120d049426052e4f9e0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704424"
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a>Использование ServiceThrottlingBehavior для управления производительностью службы WCF

Класс <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> представляет свойства, которые можно использовать для ограничения количества экземпляров или сеансов, создаваемых на уровне приложения. Используя такое поведение, можно точно настроить производительность приложения Windows Communication Foundation (WCF).  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>Управление экземплярами службы и одновременными вызовами  

 С помощью свойства <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> задайте максимальное количество одновременно обрабатываемых сообщений в классе <xref:System.ServiceModel.ServiceHost>, а с помощью свойства <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> задайте максимальное количество объектов <xref:System.ServiceModel.InstanceContext> в службе.  
  
 Поскольку определение параметров для этих свойств обычно происходит после реального опыта работы приложения с загрузкой, параметры <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> свойств обычно задаются в файле конфигурации приложения с помощью [\<serviceThrottling>](../../configure-apps/file-schema/wcf/servicethrottling.md) элемента.  
  
 В следующем примере кода показано использование класса <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> из файла конфигурации приложения, который, в качестве упрощенного примера, задает для свойств <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> и <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> значение 1. Фактические условия определяют оптимальные параметры для каждого конкретного приложения.  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 Точное поведение времени выполнения зависит от значений свойств <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> и <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>, которые управляют количеством сообщений, которые могут обрабатываться в операции одновременно, и временем существования службы <xref:System.ServiceModel.InstanceContext> относительно сеансов входящих каналов, соответственно.  
  
 Дополнительные сведения см. в разделах <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> и <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>

---
description: Дополнительные сведения см. в статье сравнение транзакций в COM+ и ServiceModel.
title: Сравнение транзакций в COM+ и ServiceModel
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 9b4e8e0940297e887ec9a3085ebe521afe4d000d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743425"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Сравнение транзакций в COM+ и ServiceModel

В этом разделе обсуждается имитация поведения транзакционной службы COM+ с помощью атрибутов Windows Communication Foundation (WCF), <xref:System.ServiceModel> предоставляемых пространством имен.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Эмуляция COM+ с помощью атрибутов ServiceModel  

 В следующей таблице сравнивается <xref:System.EnterpriseServices.TransactionOption> перечисление, используемое для создания `EnterpriseServices` транзакции, и то, как они сопоставляются с атрибутами WCF, <xref:System.ServiceModel> предоставляемыми пространством имен.  
  
|Атрибут COM+|Атрибуты WCF|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|Параметру <xref:System.ServiceModel.TransactionFlowAttribute> задается значение <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `true`.<br /><br /> Атрибут `TransactionFlow` в элементе привязки имеет значение `false`.|  
|Обязательно|Параметру <xref:System.ServiceModel.TransactionFlowAttribute> задается значение <xref:System.ServiceModel.TransactionFlowOption.Allowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `true`.<br /><br /> Атрибут `TransactionFlow` в элементе привязки имеет значение `true`.|  
|Поддерживается|Прямого эквивалента не существует. В общем случае необходимо принимать поведение, заданное для `Required`.|  
|NotSupported|Параметр <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> равен `false`.<br /><br /> Атрибут `TransactionFlow` в элементе привязки имеет значение `false`.|  
|Выключено|Прямого эквивалента не существует. В общем случае необходимо принимать поведение, заданное для `NotSupported`.|

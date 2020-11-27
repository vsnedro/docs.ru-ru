---
title: Исключения при обработке транзакций
ms.date: 03/30/2017
ms.assetid: 1d27ed51-7eda-477f-9eca-94fa129f3e07
ms.openlocfilehash: dcdf825699368617335f2d59a05f8826884a8e9e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285685"
---
# <a name="transaction-exceptions"></a>Исключения при обработке транзакций

В этом разделе перечислены все исключения, создаваемые транзакцией Windows Communication Foundation (WCF).  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Строка ресурса|  
|-------------------|---------------------|  
|SFxCannotHaveDifferentTransactionProtocolsInOneBinding|Сведения политики, импортируемые из метаданных, задают различные значения TransactionProtocol для различных операций. Поддерживается только одно значение TransactionProtocol для каждой конечной точки.|  
|SFxTransactionAutoCompleteFalseAndInstanceContextMode|TransactionAutoComplete не может иметь значение false, если InstanceContextMode службы имеет значение PerSession. Обнаружена ошибка в реализации заданных контракта и операции.|  
|SFxTransactionInvalidSetTransactionComplete|Метод OperationContext.SetTransactionComplete может вызываться в операции, только если TransactionAutoComplete имеет значение false, а TransactionScopeRequired имеет значение true. Это недопустимый сценарий, и текущая транзакция была завершена.|  
|TransactionFlowRequiredIssuedTokens|Для передачи транзакций требуется поддержка потока выданных маркеров.|  
|TrustDriverVersionDoesNotSupportIssuedTokens|Настроенная версия Trust не поддерживает выданные маркеры. Используйте WSTrustFeb2005 или более позднюю версию.|

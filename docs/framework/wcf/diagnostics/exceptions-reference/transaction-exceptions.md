---
description: 'Дополнительные сведения: исключения транзакций'
title: Исключения при обработке транзакций
ms.date: 03/30/2017
ms.assetid: 1d27ed51-7eda-477f-9eca-94fa129f3e07
ms.openlocfilehash: edea932ca12fcd05994c979555e7eb9c0d00e969
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686067"
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

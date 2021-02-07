---
description: 'Дополнительные сведения: исключения, транзакции и компенсация'
title: Исключения, транзакции и компенсация
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: 3188b0238b1909847c289bb56274671ff4b307b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720193"
---
# <a name="exceptions-transactions-and-compensation"></a>Исключения, транзакции и компенсация

[!INCLUDE[wf1](../../../includes/wf1-md.md)] предоставляет несколько различных механизмов обработки состояний ошибок времени выполнения в рабочих процессах. Рабочие процессы могут использовать сочетание обработчиков исключений, транзакций, отмены и компенсации для обработки ошибочных состояний и верного возобновления работы.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Исключения](exceptions.md)  
 Показывается использование действия <xref:System.Activities.Statements.TryCatch> для обработки исключений в рабочем процессе.  
  
 [Транзакции](workflow-transactions.md)  
 Показывается использование действия <xref:System.Activities.Statements.TransactionScope> для использования транзакций в рабочем процессе.  
  
 [Компенсация](compensation.md)  
 Описывается компенсация в рабочих процессах и показывается использование действий компенсации, например <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> и <xref:System.Activities.Statements.Confirm>.  
  
 [Отмена](modeling-cancellation-behavior-in-workflows.md)  
 Описывает, как производить выполнение отмены в рабочих процессах с помощью встроенных и настраиваемых действий.  
  
 [Отладка рабочих процессов](debugging-workflows.md)  
 Содержит описание способов отладки рабочих процессов.

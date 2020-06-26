---
title: Создание транзакционного приложения
description: Написание транзакционного приложения в .NET. Используйте явную или неявную модель программирования с классом Transaction или классом TransactionScope соответственно.
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 0235bb507d974e0bd3a7046ea213d8b78d870d59
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415775"
---
# <a name="writing-a-transactional-application"></a>Создание транзакционного приложения
Пространство имен <xref:System.Transactions> предоставляет разработчикам транзакционных приложений две модели программирования для создания транзакций. Явную модель программирования можно использовать с помощью <xref:System.Transactions.Transaction> класса или неявной модели программирования, в которой транзакции автоматически управляются инфраструктурой с помощью <xref:System.Transactions.TransactionScope> класса. Для разработки рекомендуется использовать модель неявной транзакции. Дополнительные сведения об использовании области транзакций см. в разделе [Реализация неявной транзакции с помощью области транзакций](implementing-an-implicit-transaction-using-transaction-scope.md) .  
  
 Обе модели поддерживают фиксацию транзакции при достижении программой согласованного состояния. При успешной фиксации выполненные в ходе транзакции изменения становятся постоянными. Если фиксация завершается неудачей, транзакция прерывается. Если приложение не может успешно завершить транзакцию, оно пытается прервать ее выполнение и отменить произведенные в ходе транзакции изменения.  
  
## <a name="in-this-section"></a>В этом разделе  
  
### <a name="creating-a-transaction"></a>Создание транзакции  
 Пространство имен <xref:System.Transactions> предоставляет две модели для создания транзакций. Эти модели рассматриваются в следующих разделах.  
  
 [Реализация неявной транзакции с использованием области транзакции](implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Описывает, как пространство имен <xref:System.Transactions> поддерживает создание неявных транзакций с использованием класса <xref:System.Transactions.TransactionScope>.  
  
 [Реализация явной транзакции с помощью класса CommittableTransaction](implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Описывает, как пространство имен <xref:System.Transactions> поддерживает создание явных транзакций с использованием класса <xref:System.Transactions.CommittableTransaction>.  
  
### <a name="escalating-transaction-management"></a>Передача управления транзакцией на следующий уровень иерархии  
 Если транзакции необходим доступ к ресурсу в другом домене приложения или требуется зачислить другой диспетчер устойчивых ресурсов, управление транзакцией автоматически передается координатору MSDTC. Укрупнение транзакций рассматривается в разделе [эскалация управления транзакциями](transaction-management-escalation.md) .  
  
### <a name="concurrency"></a>Параллелизм  
 В разделе [Управление параллелизмом с помощью класса DependentTransaction](managing-concurrency-with-dependenttransaction.md) показано, как можно достичь параллелизма между асинхронными задачами с использованием <xref:System.Transactions.DependentTransaction> класса.  
  
### <a name="com-interop"></a>Взаимодействие с транзакциями COM+  
 В разделе [взаимодействие с корпоративными службами и транзакциями COM+](interoperability-with-enterprise-services-and-com-transactions.md) показано, как можно сделать распределенные транзакции взаимодействующими с транзакциями COM+.  
  
### <a name="diagnostics"></a>Диагностика  
 [Диагностические трассировки](diagnostic-traces.md) описывает, как можно использовать коды трассировки, созданные <xref:System.Transactions> инфраструктурой, для устранения неполадок в приложениях.  
  
### <a name="working-within-aspnet"></a>Работа в среде ASP.NET  
 В разделе [использование System. Transactions в ASP.NET](using-system-transactions-in-aspnet.md) описывается, как можно успешно использовать <xref:System.Transactions> внутри приложения ASP.NET.

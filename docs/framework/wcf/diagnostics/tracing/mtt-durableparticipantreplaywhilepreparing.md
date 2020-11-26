---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: bfa279887339f025e4cb7c9c455fd25098684073
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236615"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing

Служба протокола WS-AT получила ответное сообщение от постоянного участника, который не ответил на подготовительное сообщение. Поэтому транзакция была прервана.  
  
## <a name="description"></a>Описание  

 Трассируется, если ответное сообщение получается, пока постоянный участник находится в состоянии подготовки. Это недопустимое сообщение для данного состояния, поэтому транзакция прерывается.  
  
## <a name="troubleshooting"></a>Устранение неполадок

Получение этой ошибки может означать, что устойчивый участник (включая подчиненный Трансактионманажерс) был восстановлен после сбоя; Тем не менее, результат транзакции не известен и запрашивает свое состояние.  
  
## <a name="see-also"></a>См. также

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)

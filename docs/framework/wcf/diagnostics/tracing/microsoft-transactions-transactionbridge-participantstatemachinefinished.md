---
description: 'Дополнительные сведения о: Microsoft. Transactions. Трансактионбридже. ПартиЦипантстатемачинефинишед'
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: f49027b82957969779423d0895ff24a4a36d1f4f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759384"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a>Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished

Конечный автомат для перечисления участников перешел в конечное состояние.  
  
## <a name="description"></a>Описание  

 Трассируется, когда перечисление подчиненных участников завершило обработку 2pc. Результатом для перечисления может быть значение Committed или Aborted. Кроме того, это событие регистрируется, если на этапе подготовки любой из участников голосует за режим ReadOnly.  
  
## <a name="see-also"></a>См. также

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)

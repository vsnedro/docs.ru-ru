---
description: 'Дополнительные сведения о: Microsoft. Transactions. Трансактионбридже. Коммитмессажеретри'
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: 8f45463ac31c210acd8534df2c4e1ef2922f1c8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720609"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a>Microsoft.Transactions.TransactionBridge.CommitMessageRetry

Повторная попытка сообщения фиксации была отправлена участнику, который не отвечает.  
  
## <a name="description"></a>Описание  

 Трассируется, если локальному диспетчеру транзакций потребовалось заново отправить сообщение фиксации подчиненному участнику, так как за заданное время не был получен отклик.  
  
## <a name="troubleshooting"></a>Устранение неполадок  

 Рассмотрите потенциальные проблемы с сетью или продуктом, которые могут препятствовать своевременной доставке отклика.  Если таких сообщений много, это может указывать на проблемы инфраструктуры или чрезмерно большое время отклика. Обе проблемы значительно снижают пропускную способность транзакций в системе.  
  
## <a name="see-also"></a>См. также

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)

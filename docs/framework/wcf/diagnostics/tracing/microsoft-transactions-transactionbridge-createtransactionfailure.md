---
title: Microsoft.Transactions.TransactionBridge.CreateTransactionFailure
ms.date: 03/30/2017
ms.assetid: c3468e23-49a9-4a84-972d-a79a658851b3
ms.openlocfilehash: 09b93ce4b72416cfea9f8c9850fd1e50c77035b7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270227"
---
# <a name="microsofttransactionstransactionbridgecreatetransactionfailure"></a>Microsoft.Transactions.TransactionBridge.CreateTransactionFailure

Невозможно создать транзакцию.  
  
## <a name="description"></a>Описание  

 Данная трассировка создается, если MSDTC не может создать транзакцию. Это может быть вызвано недостаточным объемом ресурсов, отсутствием места в журнале или другими ошибками.  
  
## <a name="troubleshooting"></a>Устранение неполадок  

 Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.  
  
## <a name="see-also"></a>См. также

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)

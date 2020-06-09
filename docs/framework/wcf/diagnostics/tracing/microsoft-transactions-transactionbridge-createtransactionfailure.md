---
title: Microsoft.Transactions.TransactionBridge.CreateTransactionFailure
ms.date: 03/30/2017
ms.assetid: c3468e23-49a9-4a84-972d-a79a658851b3
ms.openlocfilehash: f35cc0c12f2ac42c2b26536186c21feef193ae5d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594404"
---
# <a name="microsofttransactionstransactionbridgecreatetransactionfailure"></a>Microsoft.Transactions.TransactionBridge.CreateTransactionFailure
Невозможно создать транзакцию.  
  
## <a name="description"></a>Описание  
 Данная трассировка создается, если MSDTC не может создать транзакцию. Это может быть вызвано недостаточным объемом ресурсов, отсутствием места в журнале или другими ошибками.  
  
## <a name="troubleshooting"></a>Диагностика  
 Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.  
  
## <a name="see-also"></a>Дополнительно

- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)

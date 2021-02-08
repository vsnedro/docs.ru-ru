---
description: 'Подробнее: распределенные транзакции Oracle'
title: Распределенные транзакции Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: d0c41920f18e0f56ebdf57e3cb82cf829a59c450
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786177"
---
# <a name="oracle-distributed-transactions"></a>Распределенные транзакции Oracle

Объект <xref:System.Data.OracleClient.OracleConnection> автоматически прикрепляется к существующей распределенной транзакции, если он определяет, что транзакция активна. Автоматическое прикрепление к транзакции происходит при открытии соединения или его получении из пула соединений. Автоматическое прикрепление к существующим транзакциям можно отменить, задав  
  
```csharp  
Enlist=false  
```  
  
 в качестве параметра строки соединения для <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="see-also"></a>См. также

- [Oracle и ADO.NET](oracle-and-adonet.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)

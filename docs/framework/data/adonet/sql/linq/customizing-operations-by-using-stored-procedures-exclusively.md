---
title: Настройка операций за счет исключительного использования хранимых процедур
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 78db5cf448a19056d7265ab84d97d055748c3faa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164328"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>Настройка операций за счет исключительного использования хранимых процедур

Распространенным сценарием является доступ к данным с использованием только хранимых процедур.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  

 Вы можете изменить пример, предоставленный в разделе [Настройка операций, используя хранимые процедуры](customizing-operations-by-using-stored-procedures.md) , заменив даже первый запрос (который вызывает динамическое выполнение SQL) вызовом метода, который создает оболочку для хранимой процедуры.  
  
 Предположим, что `CustomersByCity` является методом, как в следующем примере.  
  
### <a name="code"></a>Код  

 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 Следующий код выполняется без динамического SQL.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>См. также раздел

- [Ответственность разработчика при переопределении поведения по умолчанию](responsibilities-of-the-developer-in-overriding-default-behavior.md)

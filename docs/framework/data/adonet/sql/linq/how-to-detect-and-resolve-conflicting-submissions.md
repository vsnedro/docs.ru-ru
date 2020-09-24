---
title: Практическое руководство. Как обнаруживать и разрешать конфликты отправки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 96e96208d9bb28092701164e6cd5943ef81515a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147727"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a>Практическое руководство. Как обнаруживать и разрешать конфликты отправки

Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет целый ряд ресурсов для обнаружения и разрешения конфликтов, возникающих при внесении изменений в базу данных несколькими пользователями. Дополнительные сведения см. [в разделе руководство. Управление конфликтами изменений](how-to-manage-change-conflicts.md).  
  
## <a name="example"></a>Пример  

 В следующем примере показан `try` / `catch` блок, который перехватывает <xref:System.Data.Linq.ChangeConflictException> исключение. Сведения о сущностях и членах для каждого конфликта отображаются в окне «Консоль».  
  
> [!NOTE]
> Для поддержки извлечения этих сведений необходимо включить директиву `using System.Reflection` (`Imports System.Reflection` в Visual Basic). Для получения дополнительной информации см. <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Внесение и отправка изменений данных](making-and-submitting-data-changes.md)
- [Практическое руководство. Как управлять конфликтами изменений](how-to-manage-change-conflicts.md)

---
description: Дополнительные сведения о том, как обнаруживать и устранять конфликты.
title: Практическое руководство. Как обнаруживать и разрешать конфликты отправки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 7ccfc9aeba8a21c3f5e950569d7650af087416a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739044"
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

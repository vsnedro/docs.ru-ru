---
description: Дополнительные сведения см. в статье как получить сведения о конфликте элементов
title: Практическое руководство. Как получить сведения о конфликтах элементов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: 2a33aba1a113bdfd66bdc341bfc9ae59406f2c40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723404"
---
# <a name="how-to-retrieve-member-conflict-information"></a>Практическое руководство. Как получить сведения о конфликтах элементов

Класс <xref:System.Data.Linq.MemberChangeConflict> можно использовать для получения сведений об отдельных членах конфликта. В этом же контексте можно предусмотреть пользовательскую обработку конфликта для любого члена. Дополнительные сведения см. в разделе [Оптимистическая блокировка: обзор](optimistic-concurrency-overview.md).  
  
## <a name="example"></a>Пример  

 Следующий код выполняет итерацию объектов <xref:System.Data.Linq.ObjectChangeConflict>. Итерация выполняется для каждого объекта <xref:System.Data.Linq.MemberChangeConflict>.  
  
> [!NOTE]
> Для предоставления сведений <xref:System.Reflection> добавьте пространство имен <xref:System.Data.Linq.MemberChangeConflict.Member%2A>.  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Как управлять конфликтами изменений](how-to-manage-change-conflicts.md)

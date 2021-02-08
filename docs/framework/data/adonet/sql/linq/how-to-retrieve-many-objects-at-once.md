---
description: Дополнительные сведения см. в статье как получить много объектов одновременно
title: Практическое руководство. Как получить несколько объектов одновременно
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 2bc202e09c64f2a1956b8688be30cfd87fb655c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802012"
---
# <a name="how-to-retrieve-many-objects-at-once"></a>Практическое руководство. Как получить несколько объектов одновременно

Для извлечения нескольких объектов из одного запроса используется <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.  
  
## <a name="example"></a>Пример  

 В следующем коде для извлечения объекта <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> и `Customer` используется метод `Order`.  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a>См. также

- [Основные принципы запросов](query-concepts.md)

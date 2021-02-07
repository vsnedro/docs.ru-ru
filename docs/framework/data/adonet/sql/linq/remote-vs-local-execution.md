---
description: 'Дополнительные сведения: удаленное и локальное выполнение'
title: Удаленное и локальное выполнение
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
ms.openlocfilehash: ea4d85faedd4a299da292029e64d77132e1a65a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695213"
---
# <a name="remote-vs-local-execution"></a>Удаленное и локальное выполнение

Запросы можно выполнять либо удаленно (то есть ядро базы данных выполняет запрос в базе данных) или локально ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] выполняет запрос в локальном кэше).  
  
## <a name="remote-execution"></a>Удаленное выполнение  

 Обратите внимание на следующий запрос:  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 Если база данных содержит тысячи строк заказов, для обработки небольшого подмножества совсем не обязательно извлекать все строки. В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] класс <xref:System.Data.Linq.EntitySet%601> реализует интерфейс <xref:System.Linq.IQueryable>. Этот метод гарантирует удаленное выполнение подобных запросов. Благодаря этому методу пользователь получает два существенных преимущества:  
  
- Извлекаются только необходимые данные.  
  
- Запросы, выполняемые ядром базы данных зачастую более эффективны благодаря индексам базы данных.  
  
## <a name="local-execution"></a>Локальное выполнение  

 В других случаях бывает необходимо иметь полный набор связанных записей в локальном кэше. Для этой цели класс <xref:System.Data.Linq.EntitySet%601> предоставляет метод <xref:System.Data.Linq.EntitySet%601.Load%2A> для явной загрузки всех членов класса <xref:System.Data.Linq.EntitySet%601>.  
  
 Если класс <xref:System.Data.Linq.EntitySet%601> уже загружен, последующие запросы выполняются локально. Этот метод полезен с двух точек зрения.  
  
- Если полный набор необходимо использовать локально или несколько раз, можно избежать удаленных запросов и связанных с ними задержек.  
  
- Сущность можно сериализовать как полную сущность.  
  
 В следующем фрагменте кода показывается, как добиться локального выполнения.  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a>Сравнение  

 Эти две возможности предоставляют мощное сочетание параметров: удаленное выполнение для больших коллекций и локальное выполнение для малых коллекций или в тех случаях, когда требуется вся коллекция. Удаленное выполнение реализуется с помощью интерфейса <xref:System.Linq.IQueryable>, а локальное выполнение - посредством хранящейся в памяти коллекции <xref:System.Collections.Generic.IEnumerable%601>. Чтобы принудительно выполнить локальное выполнение (то есть <xref:System.Collections.Generic.IEnumerable%601> ), см. статью [Преобразование типа в универсальный интерфейс IEnumerable](convert-a-type-to-a-generic-ienumerable.md).  
  
### <a name="queries-against-unordered-sets"></a>Запросы к неупорядоченным наборам  

 Обратите внимание на важное различие между локальной коллекцией, реализующей интерфейс, <xref:System.Collections.Generic.List%601> и коллекцией, которая предоставляет удаленные запросы к *неупорядоченным наборам* в реляционной базе данных. Для методов <xref:System.Collections.Generic.List%601>, например при использовании значений индексов, требуется семантика списка, которая, как правило, не реализуется посредством удаленного запроса к неупорядоченному набору. По этой причине подобные методы неявно загружают класс <xref:System.Data.Linq.EntitySet%601>, чтобы получить возможность локального выполнения.  
  
## <a name="see-also"></a>См. также

- [Основные принципы запросов](query-concepts.md)

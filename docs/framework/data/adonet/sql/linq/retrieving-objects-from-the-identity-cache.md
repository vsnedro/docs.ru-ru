---
description: 'Дополнительные сведения: получение объектов из кэша удостоверений'
title: Извлечение объектов из кэша идентификации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
ms.openlocfilehash: 1f3d5f839a6fff33d62d4e0cb2281bd087f2d320
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695090"
---
# <a name="retrieving-objects-from-the-identity-cache"></a>Извлечение объектов из кэша идентификации

В этом разделе описаны типы запросов LINQ to SQL, которые возвращают объект из кэша идентификаторов, управляемого <xref:System.Data.Linq.DataContext>.  
  
 В LINQ to SQL в качестве одного из способов управления объектами <xref:System.Data.Linq.DataContext> регистрируют идентификаторы объектов в кэше идентификаторов во время выполнения запросов. В некоторых случаях LINQ to SQL пытается получить объект из кэша идентификаторов перед выполнением запроса в базе данных.  
  
 Обычно, чтобы запрос LINQ to SQL мог вернуть объект из кэша идентификаторов, запрос должен быть основан на первичном ключе объекта и должен возвращать одиночный объект. В частности, запрос должен иметь одну из общих форм, представленных далее.  
  
> [!NOTE]
> Предварительно скомпилированные запросы не возвращают объекты из кэша идентификаторов. Дополнительные сведения о предварительно скомпилированных запросах см <xref:System.Data.Linq.CompiledQuery> . [в разделе и инструкции. Хранение и повторное использование запросов](how-to-store-and-reuse-queries.md).  
  
 Чтобы получить объект из кэша идентификаторов, запрос должен иметь одну из следующих общих форм.  
  
- <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`  
  
- <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`  
  
 В этих общих формах параметры `Function1`, `Function2` и `predicate` определяются следующим образом.  
  
 Параметр `Function1` может иметь любое из следующих значений.  
  
- <xref:System.Linq.Queryable.Where%2A>  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 Параметр `Function2` может иметь любое из следующих значений.  
  
- <xref:System.Linq.Queryable.First%2A>  
  
- <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
- <xref:System.Linq.Queryable.Single%2A>  
  
- <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 Параметр `predicate` должен быть выражением, в котором свойство первичного ключа объекта устанавливается в постоянное значение. Если первичный ключ определен в нескольких свойствах объекта, то в каждом свойстве должно быть задано постоянное значение. Далее представлены примеры формы, которую должен принимать параметр `predicate`.  
  
- `c => c.PK == constant_value`  
  
- `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## <a name="example"></a>Пример  

 В следующем коде приводятся примеры типов запросов LINQ to SQL, которые получают объект из кэша идентификаторов.  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Основные принципы запросов](query-concepts.md)
- [Идентификация объектов](object-identity.md)
- [Основные сведения](background-information.md)
- [Идентификация объектов](object-identity.md)

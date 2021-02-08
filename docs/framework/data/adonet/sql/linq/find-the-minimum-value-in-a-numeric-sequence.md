---
description: Дополнительные сведения см. в статье Поиск минимального значения в числовой последовательности.
title: Нахождение минимального значения в числовой последовательности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
ms.openlocfilehash: 6f265c6db3e143bdd5371aa9d30b4dd248e8fe3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803845"
---
# <a name="find-the-minimum-value-in-a-numeric-sequence"></a>Нахождение минимального значения в числовой последовательности

Для возвращения минимального значения из последовательности числовых значений используется оператор <xref:System.Linq.Enumerable.Min%2A>.  
  
## <a name="example"></a>Пример  

 В следующем примере выполняется поиск минимальной цены продукта.  
  
 Если выполнить этот запрос в образце базы данных Northwind, то будут получены следующие выходные данные: `2.5000`.  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## <a name="example"></a>Пример  

 В следующем примере выполняется поиск минимального объема доставки для заказа.  
  
 Если выполнить этот запрос в образце базы данных Northwind, то будут получены следующие выходные данные: `0.0200`.  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## <a name="example"></a>Пример  

 В следующем примере для поиска `Products`, имеющего минимальную цену за единицу в каждой категории используется функция Min. Результат упорядочивается по категории.  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 Если выполнить предыдущий запрос для учебной базы данных "Northwind", результаты будут выглядеть следующим образом.  
  
 `1`  
  
 `Guaraná Fantástica`  
  
 `2`  
  
 `Aniseed Syrup`  
  
 `3`  
  
 `Teatime Chocolate Biscuits`  
  
 `4`  
  
 `Geitost`  
  
 `5`  
  
 `Filo Mix`  
  
 `6`  
  
 `Tourtière`  
  
 `7`  
  
 `Longlife Tofu`  
  
 `8`  
  
 `Konbu`  
  
## <a name="see-also"></a>См. также

- [Статистические запросы](aggregate-queries.md)
- [Загрузка примеров баз данных](downloading-sample-databases.md)

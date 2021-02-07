---
description: 'Дополнительные сведения: неподдерживаемые функции'
title: Неподдерживаемые функциональные возможности
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 5c44dd4aad2d2ee4ec5e00ce42f4de9400cea478
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680893"
---
# <a name="unsupported-functionality"></a>Неподдерживаемые функциональные возможности

В LINQ to SQL следующие функции SQL недоступны путем преобразования существующих конструкций среды CLR и .NET Framework.  
  
- `STDDEV`  
  
- `LIKE`  
  
     Хотя функция `LIKE` не поддерживается прямым преобразованием, аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>. Для получения дополнительной информации см. <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
- `DATEDIFF`  
  
     В LINQ to SQL реализована ограниченная поддержка функции `DATEDIFF`. Аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>.  
  
- `ROUND`  
  
     В LINQ to SQL реализована ограниченная поддержка функции `ROUND`. Дополнительные сведения см. в разделе [методы System. Math](system-math-methods.md).  
  
## <a name="see-also"></a>См. также

- [Типы данных и функции](data-types-and-functions.md)

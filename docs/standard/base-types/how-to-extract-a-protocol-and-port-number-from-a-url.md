---
title: Практическое руководство. Извлечение протокола и номера порта из URL-адреса
ms.date: 06/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET regular expressions, examples
- regular expressions [.NET], examples
- pattern-matching with regular expressions, examples
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
ms.openlocfilehash: ba512fbe4ebc7ec35ca590541fe5bf94d07c465d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734521"
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>Практическое руководство. Извлечение протокола и номера порта из URL-адреса

В следующем примере выполняется извлечение протокола и номера порта из URL-адреса.  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a>Пример  

 Этот пример использует метод <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>, чтобы вернуть имя протокола и номер порта, разделенные двоеточием.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 Возможные интерпретации шаблона регулярного выражения `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` показаны в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`^`|Соответствие должно обнаруживаться в начале строки.|  
|`(?<proto>\w+)`|Совпадение с одним или несколькими символами слова. Присвойте этой группе имя `proto`.|  
|`://`|Совпадение с двоеточием, за которым следуют две косые черты.|  
|`[^/]+?`|Совпадение с одним или несколькими вхождениями (но как можно меньшему числу) любого символа, отличного от косой черты.|  
|`(?<port>:\d+)?`|Совпадение с вхождениями в количестве 0 или 1 двоеточия, за которым следует одна или несколько цифр. Присвойте этой группе имя `port`.|  
|`/`|Совпадение с косой чертой.|  
  
 Метод <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> разворачивает последовательность замены `${proto}${port}`, которая объединяет захваченное значение из двух именованных групп в шаблоне регулярного выражения. Это удобная альтернатива явному объединению строк, извлеченных из объекта коллекции, который был возвращен свойством <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>.  
  
 В примере используется метод <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> с двумя подстановками `${proto}` и `${port}` для включения захваченных групп в выходную строку. Вместо этого вы можете извлечь захваченные группы из объекта <xref:System.Text.RegularExpressions.GroupCollection> в сопоставлении, как показано в следующем примере кода.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a>См. также раздел

- [Регулярные выражения .NET](regular-expressions.md)

---
title: Базовые операции со строками в .NET
description: См. пример, который вызывает много строковых методов.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
ms.openlocfilehash: cc04f0c874b732668b4813f8325bd7060927f22a
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889131"
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a>Практическое руководство. Выполнение базовых операций со строками в .NET

В следующем примере некоторые методы, описанные в руководстве по [базовым операциям со строками](basic-string-operations.md), используются для создания класса, который выполняет обработку строк так же, как это происходит в реальном приложении. Класс `MailToData` хранит имя и адрес человека в отдельных свойствах и предоставляет способ объединения полей `City`, `State` и `Zip` в одну строку для отображения пользователю. Более того, данный класс позволяет пользователю вводить сведения о городе, области и почтовом индексе в одну строку. Приложение автоматически анализирует эту строку и вводит необходимые сведения в соответствующее свойство.  
  
В этом упрощенном примере используется консольное приложение с интерфейсом командной строки.  
  
## <a name="example"></a>Пример  

[!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
[!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
При выполнении предыдущего кода пользователю предлагается ввести его имя и адрес. Приложение размещает сведения в соответствующих свойствах и отображает их для пользователя, создавая одну строку, в которой представлены сведения о городе, области и почтовом индексе.  
  
## <a name="see-also"></a>См. также

- [Базовые операции со строками в .NET Framework](basic-string-operations.md)

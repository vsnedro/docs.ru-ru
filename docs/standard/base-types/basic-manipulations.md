---
title: Базовые операции со строками в .NET
description: См. пример, который вызывает много строковых методов.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
ms.openlocfilehash: e3e969520e068bde234c13d45ad790b76ecf8fdb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825161"
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a>Практическое руководство. Выполнение базовых операций со строками в .NET

В следующем примере некоторые методы, описанные в руководстве по [базовым операциям со строками](basic-string-operations.md), используются для создания класса, который выполняет обработку строк так же, как это происходит в реальном приложении. Класс `MailToData` хранит имя и адрес человека в отдельных свойствах и предоставляет способ объединения полей `City`, `State` и `Zip` в одну строку для отображения пользователю. Кроме того, при использовании этого класса пользователь может указать город, область и почтовый индекс в виде одной строки. Приложение автоматически анализирует одну строку и вводит соответствующие сведения в соответствующее свойство.

В этом упрощенном примере используется консольное приложение с интерфейсом командной строки.

## <a name="example"></a>Пример

[!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
[!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]

При выполнении предыдущего кода пользователю предлагается ввести его имя и адрес. Приложение размещает сведения в соответствующих свойствах и отображает их для пользователя, создавая одну строку, в которой представлены сведения о городе, области и почтовом индексе.

## <a name="see-also"></a>См. также

- [Базовые операции со строками в .NET Framework](basic-string-operations.md)

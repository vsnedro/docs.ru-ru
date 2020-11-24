---
title: Практическое руководство. Использование блоков Finally
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
ms.openlocfilehash: 8bc36ce9a755762bb5159a27f9ef5699b2992f0e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828040"
---
# <a name="how-to-use-finally-blocks"></a>Использование блоков finally

При возникновении исключения выполнение останавливается, и управление передается соответствующему обработчику исключений. Часто это означает, что ожидаемые вами строки кода пропускаются. Даже при возникновении исключения требуется определенная очистка ресурсов, например закрытие файла. Для этого можно использовать блок `finally`. Блок `finally` выполняются всегда, независимо от того, возникает ли исключение.

В следующем примере кода блок `try`/`catch` используется, чтобы перехватить <xref:System.ArgumentOutOfRangeException>. Метод `Main` создает два массива и пытается скопировать один из них в другой. Это действие создает исключение <xref:System.ArgumentOutOfRangeException>, и ошибка выводится на консоль. Блок `finally` выполняется вне зависимости от результата операции копирования.

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a>См. также раздел

- [Исключения](index.md)

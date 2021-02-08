---
description: 'Дополнительные сведения о: BC30106: число индексов превышает число измерений индексированного массива'
title: Количество индексов превышает размерность индексированного массива
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: 35ec1ea106e67022046179412b142cd92712c822
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795615"
---
# <a name="bc30106-number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a>BC30106: число индексов превышает число измерений индексированного массива

Число индексов, используемых для доступа к элементу массива, должно быть точно равно рангу массива, то есть числу измерений, объявленных для него.

 **Идентификатор ошибки:** BC30106

## <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите индексы из ссылки на массив, пока общее число индексов не станет рангом массива. Пример:

    ```vb
    Dim gameBoard(3, 3) As String

    ' Incorrect code. The array has two dimensions.
    gameBoard(1, 1, 1) = "X"
    gameBoard(2, 1, 1) = "O"

    ' Correct code.
    gameBoard(0, 0) = "X"
    gameBoard(1, 0) = "O"
    ```

## <a name="see-also"></a>См. также

- [Массивы](../../programming-guide/language-features/arrays/index.md)

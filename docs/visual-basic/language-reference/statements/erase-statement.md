---
title: Оператор Erase
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 31aeaf822bc9c1de59a5c5f68406c6521216ae0e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404723"
---
# <a name="erase-statement-visual-basic"></a>Оператор Erase (Visual Basic)
Используется для высвобождения переменных массива и освобождения памяти, используемой для их элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>Компоненты  
 `arraylist`  
 Обязательный. Список переменных массива для удаления. Переменные разделяются запятыми.  
  
## <a name="remarks"></a>Комментарии  
 `Erase`Инструкция может использоваться только на уровне процедуры. Это означает, что массивы можно освобождать внутри процедуры, но не на уровне класса или модуля.  
  
 `Erase`Оператор эквивалентен присвоению `Nothing` каждой переменной массива.  
  
## <a name="example"></a>Пример  
 В следующем примере инструкция используется `Erase` для очистки двух массивов и освобождения памяти (1000 и 100, соответственно). `ReDim`Затем оператор присваивает новый экземпляр массива трехмерному массиву.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>См. также раздел

- [Nothing](../nothing.md)
- [Оператор reDim](redim-statement.md)

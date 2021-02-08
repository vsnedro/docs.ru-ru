---
description: 'Дополнительные сведения об инструкции: Erase (Visual Basic)'
title: Оператор Erase
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 295abec89f3d69f8f2641a5a3d574a2d10f98474
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769160"
---
# <a name="erase-statement-visual-basic"></a>Оператор Erase (Visual Basic)

Используется для высвобождения переменных массива и освобождения памяти, используемой для их элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>Компоненты  

 `arraylist`  
 Обязательный элемент. Список переменных массива для удаления. Переменные разделяются запятыми.  
  
## <a name="remarks"></a>Remarks  

 `Erase`Инструкция может использоваться только на уровне процедуры. Это означает, что массивы можно освобождать внутри процедуры, но не на уровне класса или модуля.  
  
 `Erase`Оператор эквивалентен присвоению `Nothing` каждой переменной массива.  
  
## <a name="example"></a>Пример  

 В следующем примере инструкция используется `Erase` для очистки двух массивов и освобождения памяти (1000 и 100, соответственно). `ReDim`Затем оператор присваивает новый экземпляр массива трехмерному массиву.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>См. также

- [Nothing](../nothing.md)
- [Оператор reDim](redim-statement.md)

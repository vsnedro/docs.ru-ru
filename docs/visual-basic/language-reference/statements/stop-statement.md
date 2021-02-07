---
description: Дополнительные сведения о операторе "завершение" (Visual Basic)
title: Оператор Stop
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 1e25eb88d1b85f38a53023dfb7dfbc877f498e5e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741085"
---
# <a name="stop-statement-visual-basic"></a>Оператор Stop (Visual Basic)

Приостанавливает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a>Remarks  

 Операторы можно разместить `Stop` в любом месте процедуры, чтобы приостановить выполнение. Использование `Stop` инструкции аналогично установке точки останова в коде.  
  
 `Stop`Инструкция приостанавливает выполнение, но в отличие от этого `End` она не закрывает никакие файлы и не очищает переменные, если она не обнаружена в скомпилированном исполняемом файле (exe).  
  
> [!NOTE]
> Если `Stop` инструкция обнаружена в коде, который выполняется вне интегрированной среды разработки (IDE), вызывается отладчик. Это справедливо независимо от того, был ли код скомпилирован в режиме отладки или розничной торговли.  
  
## <a name="example"></a>Пример  

 В этом примере используется `Stop` оператор для приостановки выполнения для каждой итерации в `For...Next` цикле.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>См. также

- [End, инструкция](end-statement.md)

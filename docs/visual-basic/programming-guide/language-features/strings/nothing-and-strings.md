---
title: Nothing и строки
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d4c7ee6d13334617a80abb845af52bf388a12797
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072526"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing и строки в Visual Basic

Среда выполнения Visual Basic и .NET Framework оцениваются по- `Nothing` разному, когда речь идет о строках.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Среда выполнения Visual Basic и .NET Framework  

 Рассмотрим следующий пример.  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Среда выполнения Visual Basic обычно вычисляется `Nothing` как пустая строка (""). Однако .NET Framework не создает исключение, когда выполняется попытка выполнить операцию со строкой `Nothing` .  
  
## <a name="see-also"></a>См. также

- [Знакомство со строками в Visual Basic](introduction-to-strings.md)

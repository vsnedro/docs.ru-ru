---
description: 'Дополнительные сведения о: Nothing и строках в Visual Basic'
title: Nothing и строки
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: a32dd8b38033f1845f2ada87bf5f538d45fede18
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424350"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing и строки в Visual Basic

Среда выполнения Visual Basic и платформа .NET Framework оцениваются по- `Nothing` разному, когда речь идет о строках.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Среда выполнения Visual Basic и платформа .NET Framework  

 Рассмотрим следующий пример.  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Среда выполнения Visual Basic обычно вычисляется `Nothing` как пустая строка (""). Однако платформа .NET Framework не создает исключение, когда выполняется попытка выполнить операцию со строкой `Nothing` .  
  
## <a name="see-also"></a>См. также раздел

- [Знакомство со строками в Visual Basic](introduction-to-strings.md)

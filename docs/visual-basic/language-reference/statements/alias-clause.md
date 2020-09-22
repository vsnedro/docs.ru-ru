---
title: Предложение Alias
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 77d4685f242864842e5a84b3a3de3ba1793e9aa4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866689"
---
# <a name="alias-clause-visual-basic"></a>Предложение Alias (Visual Basic)

Указывает, что у внешней процедуры есть другое имя в своей библиотеке DLL.  
  
## <a name="remarks"></a>Remarks  

 `Alias`Ключевое слово можно использовать в следующем контексте:  
  
 [Declare Statement](declare-statement.md)  
  
 В следующем примере `Alias` ключевое слово используется для предоставления имени функции в advapi32.dll, `GetUserNameA` , `getUserName` используемом вместо в этом примере. Функция `getUserName` вызывается в подпрограмме `getUser` , которая отображает имя текущего пользователя.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>См. также

- [Ключевые слова](../keywords/index.md)

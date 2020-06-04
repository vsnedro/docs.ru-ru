---
title: Предложение Alias
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: c28e931a376b20b2058a7187551405cd9523d4fe
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408475"
---
# <a name="alias-clause-visual-basic"></a>Предложение Alias (Visual Basic)
Указывает, что у внешней процедуры есть другое имя в своей библиотеке DLL.  
  
## <a name="remarks"></a>Комментарии  
 `Alias`Ключевое слово можно использовать в следующем контексте:  
  
 [Declare Statement](declare-statement.md)  
  
 В следующем примере `Alias` ключевое слово используется для предоставления имени функции в advapi32. dll, `GetUserNameA` , которая `getUserName` используется вместо в этом примере. Функция `getUserName` вызывается в подпрограмме `getUser` , которая отображает имя текущего пользователя.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>См. также раздел

- [Ключевые слова](../keywords/index.md)

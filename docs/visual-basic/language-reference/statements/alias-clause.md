---
description: Дополнительные сведения о предложении Alias (Visual Basic)
title: Предложение Alias
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: bf0ee1c22105b29aedb99ce45a99ba866f4b93c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674081"
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

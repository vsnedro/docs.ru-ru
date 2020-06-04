---
title: В типе <typename> отсутствуют конструкторы
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: de0d825c7eec603f3ad1e43b1e4aaa0cc78fd1db
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408514"
---
# <a name="type-typename-has-no-constructors"></a>В типе \<typename> отсутствуют конструкторы
Тип не поддерживает вызов в `Sub New()`. Одной из возможных причин является повреждение компилятора или двоичного файла.  
  
 **Идентификатор ошибки:** BC30251  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Если тип находится в другом проекте или в заданном ссылкой файле, переустановите этот проект или файл.  
  
2. Если тип находится в том же самом проекте, перекомпилируйте сборку, содержащую тип.  
  
3. Если ошибка повторяется, переустановите компилятор Visual Basic.  
  
4. Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
## <a name="see-also"></a>См. также раздел

- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
- [Обращайтесь к нам](/visualstudio/ide/feedback-options)

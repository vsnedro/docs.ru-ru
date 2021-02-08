---
description: 'Дополнительные сведения о: BC30043: " <keyword> " допустимо только в методе экземпляра'
title: <keyword> разрешено использовать только в методе экземпляра
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 0bca2df44e096da016c9cb0c2031a8ef6faeb2b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795980"
---
# <a name="bc30043-keyword-is-valid-only-within-an-instance-method"></a>BC30043: " \<keyword> " является допустимым только в пределах метода экземпляра

`Me` `MyClass` Ключевые слова, и `MyBase` относятся к конкретным экземплярам класса. Их нельзя использовать в общей `Function` или `Sub` процедурной среде.

*Идентификатор ошибки:** BC30043

## <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите ключевое слово из процедуры или удалите `Shared` ключевое слово из объявления процедуры.

## <a name="see-also"></a>См. также

- [Присваивание объектных переменных](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase и MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)

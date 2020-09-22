---
title: <keyword> разрешено использовать только в методе экземпляра
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af436b8fd57ff0d2747c766a64af175760931009
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873906"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>\<keyword> разрешено использовать только в методе экземпляра

`Me` `MyClass` Ключевые слова, и `MyBase` относятся к конкретным экземплярам класса. Их нельзя использовать в общей `Function` или `Sub` процедурной среде.  
  
 **Идентификатор ошибки:** BC30043  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите ключевое слово из процедуры или удалите `Shared` ключевое слово из объявления процедуры.  
  
## <a name="see-also"></a>См. также

- [Присваивание объектных переменных](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase и MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)

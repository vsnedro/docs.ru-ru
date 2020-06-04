---
title: <keyword> разрешено использовать только в методе экземпляра
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 537689405ea30bdd7c075320eba58a8723a93cdb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397406"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>\<keyword> разрешено использовать только в методе экземпляра
`Me` `MyClass` Ключевые слова, и `MyBase` относятся к конкретным экземплярам класса. Их нельзя использовать в общей `Function` или `Sub` процедурной среде.  
  
 **Идентификатор ошибки:** BC30043  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите ключевое слово из процедуры или удалите `Shared` ключевое слово из объявления процедуры.  
  
## <a name="see-also"></a>См. также раздел

- [Присваивание объектных переменных](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase и MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)

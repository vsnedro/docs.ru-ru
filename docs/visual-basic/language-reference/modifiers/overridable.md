---
description: Дополнительные сведения о переопределяемых параметрах (Visual Basic)
title: Overridable
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: acbbd715113c836a3fb7f8a88bf74307c38ac682
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730503"
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)

Указывает, что свойство или процедура может быть переопределена свойством или процедурой с идентичным именем в производном классе.  
  
## <a name="remarks"></a>Remarks  

 `Overridable`Модификатор позволяет переопределять свойство или метод в производном классе. Модификатор [NotOverridable](notoverridable.md) предотвращает переопределение свойства или метода в производном классе.  Дополнительные сведения см. в статье [Inheritance Basics (Visual Basic)](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md) (Основная информация о наследовании в Visual Basic).  
  
 Если `Overridable` Модификатор или `NotOverridable` не задан, значение по умолчанию зависит от того, переопределяет ли свойство или метод свойство или метод базового класса. Если свойство или метод переопределяет свойство или метод базового класса, параметр по умолчанию имеет значение `Overridable` ; в противном случае — `NotOverridable` .  
  
 Можно выполнить затенение или переопределение, чтобы переопределить наследуемый элемент, но существуют значительные различия между этими двумя подходами. Дополнительные сведения см. [в разделе теневая поддержка в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).  
  
 Элемент, который можно переопределить, иногда называется *виртуальным* элементом. Если он может быть переопределен, но не обязательно должен быть, он иногда также называется *конкретным* элементом.  
  
 Можно использовать `Overridable` только в операторе объявления свойства или процедуры.  
  
## <a name="combined-modifiers"></a>Комбинированные модификаторы  

 Нельзя указывать `Overridable` или `NotOverridable` для `Private` метода.  
  
 Нельзя указывать `Overridable` вместе с `MustOverride` , `NotOverridable` или `Shared` в одном объявлении.  
  
 Так как переопределяемый элемент является неявно переопределяемым, нельзя объединять `Overridable` с `Overrides`.  
  
## <a name="usage"></a>Использование  

 Модификатор `Overridable` можно использовать в следующих контекстах:  
  
 [Оператор Function](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Оператор Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [Модификаторы](index.md)
- [Основы наследования](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Переопределения](overrides.md)
- [Ключевые слова](../keywords/index.md)
- [Сокрытие в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)

---
title: Пространство имен или тип, указанный в Imports <qualifiedelementname>, не содержит общих членов или не найден
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 284a8c71fee8835f78ca5435932819fded1b1f30
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160136"
---
# <a name="bc40056-namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>BC40056: пространство имен или тип, указанные в Imports " \<qualifiedelementname> ", не содержат открытых членов или не могут быть найдены

Пространство имен или тип, указанные в Imports " \<qualifiedelementname> ", не содержат открытых членов или не могут быть найдены. Убедитесь, что пространство имен или тип определены и содержат по крайней мере один открытый член. Убедитесь, что имя псевдонима не содержит других псевдонимов.

`Imports`Оператор указывает содержащий элемент, который либо не может быть найден, либо не определяет какие-либо `Public` элементы.

*Содержащий элемент* может быть пространством имен, классом, структурой, модулем, интерфейсом или перечислением. Содержащий элемент содержит такие элементы, как переменные, процедуры или другие элементы, содержащие.

Цель импорта заключается в том, чтобы предоставить коду доступ к пространству имен или членам типа без необходимости уточнять их. В проекте также может потребоваться добавить ссылку на пространство имен или тип. Дополнительные сведения см. в разделе "Импорт содержащихся элементов" в [ссылках на объявленные элементы](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

Если компилятор не может найти указанный содержащий элемент, он не сможет разрешить ссылки, которые его используют. Если он находит элемент, но элемент не предоставляет никаких `Public` членов, ссылка не может быть успешной. В любом случае нет смысла импортировать элемент.

Помните, что при импорте содержащего элемента и присвоении ему псевдонима импорта нельзя использовать этот псевдоним импорта для импорта другого элемента. Следующий код приводит к ошибке компилятора.

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

**Идентификатор ошибки:** BC40056

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что содержащий элемент доступен из проекта.

2. Убедитесь, что спецификация содержащего элемента не содержит псевдоним импорта из другого импорта.

3. Убедитесь, что содержащий элемент предоставляет по крайней мере один `Public` элемент.

## <a name="see-also"></a>См. также

- [Оператор Imports (пространство имен .NET и тип)](../statements/imports-statement-net-namespace-and-type.md)
- [Оператор Namespace](../statements/namespace-statement.md)
- [Общедоступная](../modifiers/public.md)
- [Пространства имен в Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

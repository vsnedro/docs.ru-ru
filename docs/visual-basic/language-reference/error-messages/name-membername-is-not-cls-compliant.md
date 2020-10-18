---
title: Имя <membername> не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 43fff3f12295f3837148b0a349887e8405126819
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160240"
---
# <a name="bc40031-name-membername-is-not-cls-compliant"></a>BC40031: имя несовместимо \<membername> с CLS

Сборка помечается как, `<CLSCompliant(True)>` но предоставляет член с именем, которое начинается с символа подчеркивания ( `_` ).

 Программный элемент может содержать один или несколько символов подчеркивания, но для соответствия [языковым независимостьм и Language-Independent компонентам](../../../standard/language-independence-and-language-independent-components.md) (CLS) он не должен начинаться с символа подчеркивания. См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.

 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.

 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Идентификатор ошибки:** BC40031

## <a name="to-correct-this-error"></a>Исправление ошибки

- Если вы управляете исходным кодом, измените его имя так, чтобы оно не начиналось с символа подчеркивания.

- Если требуется, чтобы имя элемента оставалось без изменений, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте как `<CLSCompliant(False)>` . Вы по-прежнему можете пометить сборку как `<CLSCompliant(True)>` .

## <a name="see-also"></a>См. также

- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Соглашения об именах Visual Basic](../../programming-guide/program-structure/naming-conventions.md)

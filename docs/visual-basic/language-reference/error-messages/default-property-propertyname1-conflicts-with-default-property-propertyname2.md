---
description: 'Дополнительные сведения о: BC40007: свойство по умолчанию " <propertyname1> " конфликтует со свойством по умолчанию " <propertyname2> " в " <classname> " и поэтому должно быть объявлено как "Shadows"'
title: Свойство <propertyname1>, используемое по умолчанию, конфликтует со свойством <propertyname2>, используемым по умолчанию в классе <classname>, и должно быть объявлено с ключевым словом Shadows
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 8ec7e36da18bbf8dda35e1a521d64268d14b7b26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796643"
---
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>BC40007: свойство по умолчанию " \<propertyname1> " конфликтует со свойством по умолчанию " \<propertyname2> " в " \<classname> " и поэтому должно быть объявлено как "Shadows"

Свойство объявлено с тем же именем, что и у свойства, определенного в базовом классе. В этом случае свойство в этом классе должно скрывать свойство базового класса.

 Это сообщение является предупреждением. `Shadows` подразумевается по умолчанию. Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Идентификатор ошибки:** BC40007

## <a name="to-correct-this-error"></a>Исправление ошибки

- Добавьте `Shadows` ключевое слово в объявление или измените имя объявляемого свойства.

## <a name="see-also"></a>См. также

- [Shadows](../modifiers/shadows.md)
- [Сокрытие в Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)

---
description: 'Дополнительные сведения о: BC40029: " <classname> " несовместим с CLS, поскольку интерфейс "", который <interfacename> он реализует, НЕСОВМЕСТИМ с CLS'
title: <classname> несовместимо с CLS, так как интерфейс <interfacename>, который он реализует, несовместим с CLS
ms.date: 07/20/2015
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
ms.openlocfilehash: 28264dd602bd20a6b33bebd965982ca12d402d01
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796774"
---
# <a name="bc40029-classname-is-not-cls-compliant-because-the-interface-interfacename-it-implements-is-not-cls-compliant"></a>BC40029: " \<classname> " несовместим с CLS, поскольку интерфейс "", который \<interfacename> он реализует, НЕСОВМЕСТИМ с CLS

Класс или интерфейс помечен как `<CLSCompliant(True)>` , если он наследует или реализует тип, помеченный как `<CLSCompliant(False)>` или не помеченный совсем.

 Чтобы класс или интерфейс соответствовал требованиям [независимости от языка и Language-Independent компонентов](../../../standard/language-independence-and-language-independent-components.md) (CLS), его полная иерархия наследования должна соответствовать требованиям. Это означает, что каждый тип, от которого он наследуется прямо или косвенно, должен быть соответствующим. Аналогично, если класс реализует один или несколько интерфейсов, то все они должны быть совместимыми по всей иерархии наследования.

 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.

 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.

 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Идентификатор ошибки:** BC40029

## <a name="to-correct-this-error"></a>Исправление ошибки

- Если требуется совместимость с CLS, определите этот тип в другой иерархии наследования или схеме реализации.

- Если требуется, чтобы этот тип оставался в текущей иерархии наследования или схеме реализации, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>`.

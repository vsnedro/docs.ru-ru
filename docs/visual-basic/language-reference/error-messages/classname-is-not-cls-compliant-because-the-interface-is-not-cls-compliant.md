---
title: <classname> несовместимо с CLS, так как интерфейс <interfacename>, который он реализует, несовместим с CLS
ms.date: 07/20/2015
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
ms.openlocfilehash: a482d14094a3fa86b56ca84af46c45e6093416c5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874624"
---
# <a name="classname-is-not-cls-compliant-because-the-interface-interfacename-it-implements-is-not-cls-compliant"></a>\<classname> несовместимо с CLS, так как интерфейс \<interfacename>, который он реализует, несовместим с CLS

Класс или интерфейс помечен как `<CLSCompliant(True)>` , если он наследует или реализует тип, помеченный как `<CLSCompliant(False)>` или не помеченный совсем.  
  
 Чтобы класс или интерфейс был совместим с [независимостьм от языка и независимыми от языка компонентами](../../../standard/language-independence-and-language-independent-components.md) (CLS), его полная иерархия наследования должна быть соответствующей. Это означает, что каждый тип, от которого он наследуется прямо или косвенно, должен быть соответствующим. Аналогично, если класс реализует один или несколько интерфейсов, то все они должны быть совместимыми по всей иерархии наследования.  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.  
  
 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40029  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Если требуется совместимость с CLS, определите этот тип в другой иерархии наследования или схеме реализации.  
  
- Если требуется, чтобы этот тип оставался в текущей иерархии наследования или схеме реализации, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>`.  

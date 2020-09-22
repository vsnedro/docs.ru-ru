---
title: CLS-несовместимый <membername> не допускается в CLS-совместимом интерфейсе
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: d8394fb995bb7b009b4ee40dccc41e3435ae7309
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873698"
---
# <a name="non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a>CLS-несовместимый \<membername> не допускается в CLS-совместимом интерфейсе

Свойство, процедура или событие в интерфейсе помечается так, как `<CLSCompliant(True)>` если бы сам интерфейс был помечен как `<CLSCompliant(False)>` или, не помечен.  
  
 Чтобы интерфейс был совместим с [независимостьм от языка и зависимыми от языка компонентами](../../../standard/language-independence-and-language-independent-components.md) (CLS), все его члены должны быть соответствующими.  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.  
  
 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40033  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Если требуется обеспечить соответствие требованиям CLS и контролировать исходный код интерфейса, пометьте интерфейс как, `<CLSCompliant(True)>` Если все его члены соответствуют требованиям.  
  
- Если требуется CLS-совместимость и отсутствует контроль над исходным кодом интерфейса или если он не соответствует требованиям, определите этот член в другом интерфейсе.  
  
- Если требуется, чтобы этот член оставался в текущем интерфейсе, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>` .  
  
## <a name="see-also"></a>См. также

- [Оператор Interface](../statements/interface-statement.md)

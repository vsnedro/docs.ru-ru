---
description: 'Дополнительные сведения о: BC40035: несовместим с <proceduresignature1> CLS, так как он перегружает <proceduresignature2> , который отличается от него только массивом типов параметров массива или рангом типов параметров массива.'
title: <proceduresignature1> не соответствует CLS, поскольку он перегружает <proceduresignature2>, который отличается от него только массивом типов параметров или рангом типов параметра массива
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 056683033a4eacdc6ad783f5056b639e849e3507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795395"
---
# <a name="bc40035-proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>BC40035: несовместим с \<proceduresignature1> CLS, поскольку он перегружает \<proceduresignature2> , который отличается от него только массивом типов параметров массива или рангом типов параметров массива.

Процедура или свойство помечается так, как `<CLSCompliant(True)>` если бы оно переопределяет другую процедуру или свойство, а единственное различие между их списками параметров — уровень вложенности массива массивов или ранг массива.

 В следующих объявлениях второе и третье объявления создают эту ошибку:

 `Overloads Sub ProcessArray(arrayParam() As Integer)`

 `Overloads Sub ProcessArray(arrayParam()() As Integer)`

 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`

 Второе объявление изменяет исходный одномерный параметр `arrayParam` на массив массивов. Третье объявление изменяется `arrayParam` на двумерный массив (ранг 2). Хотя Visual Basic допускает, чтобы перегрузки отличались только одним из этих изменений, такая перегрузка не соответствует требованиям независимости от [языка и Language-Independent компонентов](../../../standard/language-independence-and-language-independent-components.md) (CLS).

 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.

 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.

 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Идентификатор ошибки:** BC40035

## <a name="to-correct-this-error"></a>Исправление ошибки

- Если требуется CLS-совместимость, определите перегрузки так, чтобы они отличались друг от друга более разными способами, чем изменения, упомянутые на этой странице справки.
- Если требуется, чтобы перегрузки отличались только изменениями, упоминаемыми на этой странице справки, удалите <xref:System.CLSCompliantAttribute> из их определений или пометьте их как `<CLSCompliant(False)>` .

## <a name="see-also"></a>См. также

- [Перегрузка процедур](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [Перегрузки](../modifiers/overloads.md)

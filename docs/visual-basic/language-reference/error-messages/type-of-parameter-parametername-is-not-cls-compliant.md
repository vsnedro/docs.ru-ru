---
description: 'Дополнительные сведения о: BC40028: тип параметра "" несовместим с <parametername> CLS'
title: Тип параметра <parametername> не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: 5e430e55e24001d779243645cf4b409d1801d6f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731123"
---
# <a name="bc40028-type-of-parameter-parametername-is-not-cls-compliant"></a>BC40028: тип параметра "" несовместим с \<parametername> CLS

Процедура помечена как `<CLSCompliant(True)>` , но объявляет параметр с типом, помеченным как `<CLSCompliant(False)>` , не помечен или не является подходящим, поскольку является несоответствующим типом.

 Для соответствия требованиям, описанным в статье [Независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), процедура должна использовать только типы, совместимые с CLS. Это касается типов параметров, типа возвращаемого значения и типов всех локальных переменных.

 Следующие типы данных Visual Basic несовместимы с CLS:

- [Тип данных SByte](../data-types/sbyte-data-type.md)

- [Тип данных UInteger](../data-types/uinteger-data-type.md)

- [Тип данных ULong](../data-types/ulong-data-type.md)

- [Тип данных UShort](../data-types/ushort-data-type.md)

 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.

 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.

 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Идентификатор ошибки:** BC40028

## <a name="to-correct-this-error"></a>Исправление ошибки

- Если процедура должна принимать параметр этого конкретного типа, удалите <xref:System.CLSCompliantAttribute> . Процедура не может быть совместимой с CLS.

- Если процедура должна быть CLS-совместимой, измените тип этого параметра на ближайший CLS-совместимый тип. Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647. Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.

- При взаимоработе с автоматизацией или COM-объектами Помните, что некоторые типы имеют разную ширину данных, чем в платформа .NET Framework. Например, данные типа `int` часто являются 16-битными в других средах. Если вы принимаете 16-разрядное целое число из такого компонента, объявите его как `Short` вместо `Integer` в управляемом коде Visual Basic.

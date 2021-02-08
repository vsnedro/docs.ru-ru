---
description: 'Дополнительные сведения о: BC30424: константы должны быть встроенными или перечисляемыми типами, а не классом, структурой, параметром типа или типом массива'
title: Константа должна быть величиной внутреннего или перечислимого типа, а не классом, структурой, параметром типа или массивом
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: e9765d78ff671d6b99f47242509b1c3b4560c029
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796734"
---
# <a name="bc30424-constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>BC30424: константы должны иметь встроенный или перечислимый тип, а не класс, структуру, параметр типа или тип массива

Предпринята попытка объявить константу как класс, структуру или тип массива или как параметр типа, определенный содержащим универсальным типом.

 Константы должны иметь встроенный тип ( `Boolean` , `Byte` ,, `Date` , `Decimal` `Double` , `Integer` , `Long` ,,,,,,, `Object` `SByte` `Short` `Single` `String` `UInteger` `ULong` или `UShort` ) или тип, `Enum` основанный на одном из целочисленных типов.

 **Идентификатор ошибки:** BC30424

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Объявите константу как внутренний или `Enum` тип.

2. Константа также может быть специальным значением, таким как `True` , `False` или `Nothing` . Компилятор считает эти предопределенные значения соответствующим внутренним типом.

## <a name="see-also"></a>См. также

- [Константы и перечисления](../constants-and-enumerations.md)
- [Типы данных](../../programming-guide/language-features/data-types/index.md)
- [Типы данных](../data-types/index.md)

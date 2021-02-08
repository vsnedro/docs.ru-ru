---
description: 'Дополнительные сведения о: BC30812: необязательные параметры должны указывать значение по умолчанию'
title: Для необязательных параметров должно быть задано значение по умолчанию
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 1cbed1c0f1297ecacdae94d9234d18a3d268f487
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795538"
---
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a>BC30812: необязательные параметры должны указывать значение по умолчанию

Необязательные параметры должны предоставлять значения по умолчанию, которые можно использовать, если вызывающая процедура не предоставляет параметр.

**Идентификатор ошибки:** BC30812

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки BC30812:

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a>Исправление ошибки

Укажите значения по умолчанию для необязательных параметров:

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a>См. также

- [Необязательно](../modifiers/optional.md)

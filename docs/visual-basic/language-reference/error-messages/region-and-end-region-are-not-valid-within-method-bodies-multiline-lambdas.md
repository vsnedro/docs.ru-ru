---
title: 'Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c792fa1a42bde22959ae21439cb2a0a1e4be343f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162288"
---
# <a name="bc32025-region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>BC32025: операторы "#Region" и "#End Region" недопустимы в теле метода/многострочных лямбда-выражений

`#Region`Блок должен быть объявлен на уровне класса, модуля или пространства имен. Свертываемая область может включать одну или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.

 **Идентификатор ошибки:** BC32025

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что предыдущая процедура правильно завершается `End Function` `End Sub` оператором или.

2. Убедитесь, что `#Region` `#End Region` директивы и находятся в одном блоке кода.

## <a name="see-also"></a>См. также

- [Директива #Region](../directives/region-directive.md)

---
title: 'Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 5652139ab139ea93258eb116f97ba21b76986a24
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400387"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах
`#Region`Блок должен быть объявлен на уровне класса, модуля или пространства имен. Свертываемая область может включать одну или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.  
  
 **Идентификатор ошибки:** BC32025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что предыдущая процедура правильно завершается `End Function` `End Sub` оператором или.  
  
2. Убедитесь, что `#Region` `#End Region` директивы и находятся в одном блоке кода.  
  
## <a name="see-also"></a>См. также раздел

- [Директива #Region](../directives/region-directive.md)

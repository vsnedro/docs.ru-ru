---
title: 'Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: e3147b6192f54ce85d0fecd6b67f7d80f6281b54
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870882"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах

`#Region`Блок должен быть объявлен на уровне класса, модуля или пространства имен. Свертываемая область может включать одну или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.  
  
 **Идентификатор ошибки:** BC32025  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что предыдущая процедура правильно завершается `End Function` `End Sub` оператором или.  
  
2. Убедитесь, что `#Region` `#End Region` директивы и находятся в одном блоке кода.  
  
## <a name="see-also"></a>См. также

- [Директива #Region](../directives/region-directive.md)

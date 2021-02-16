---
description: Дополнительные сведения см. в статье Устранение неполадок наследуемых обработчиков событий в Visual Basic
title: Устранение неполадок, связанных с унаследованными обработчиками событий
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: b489b6c85510bb942b403a508b6bbe232c3e1853
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424480"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic

В этом разделе перечислены распространенные проблемы, возникающие при работе с обработчиками событий в наследуемых компонентах.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Код в обработчике событий выполняется дважды для каждого вызова  
  
- Наследуемый обработчик событий не должен включать предложение [Handles](../../../language-reference/statements/handles-clause.md) . Метод в базовом классе уже связан с событием и будет срабатывать соответствующим образом. Удалите `Handles` предложение из унаследованного метода.  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- Если наследуемый метод не имеет `Handles` ключевого слова, убедитесь, что код не содержит лишних [операторов AddHandler](../../../language-reference/statements/addhandler-statement.md) или дополнительных методов, обрабатывающих это же событие.  
  
## <a name="see-also"></a>См. также

- [События](index.md)

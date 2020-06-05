---
title: Устранение неполадок, связанных с унаследованными обработчиками событий
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: 4e7bedd1de5197fcf8b69091f4cc878f41b01cd5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405110"
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

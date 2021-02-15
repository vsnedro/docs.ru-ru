---
description: 'Дополнительные сведения о: как принудительно передавать аргумент по значению (Visual Basic)'
title: Практическое руководство. Принудительная передача аргумента по значению
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 471ddbf8993ad671dc4285729a11f5b17a5b19dc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475426"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Практическое руководство. Принудительная передача аргумента по значению (Visual Basic)

Объявление процедуры определяет механизм передачи. Если параметр объявлен как [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic предполагался передать соответствующий аргумент по ссылке. Это позволяет процедуре изменять значение программного элемента, лежащего в основе аргумента в вызывающем коде. Если вы хотите защитить базовый элемент от таких изменений, можно переопределить `ByRef` механизм передачи в вызове процедуры, заключив имя аргумента в круглые скобки. Эти скобки являются дополнением к круглым скобкам, включающим список аргументов в вызове.  
  
 Вызывающий код не может переопределить механизм [ByVal](../../../language-reference/modifiers/byval.md) .  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Принудительная передача аргумента по значению  
  
- Если соответствующий параметр объявлен `ByVal` в процедуре, вам не нужно предпринимать никаких дополнительных действий. Visual Basic уже ждет передачи аргумента по значению.  
  
- Если соответствующий параметр объявлен `ByRef` в процедуре, заключите аргумент в круглые скобки в вызове процедуры.  
  
## <a name="example"></a>Пример  

 В следующем примере переопределяется `ByRef` объявление параметра. В вызове, который вызывает принудительное выполнение `ByVal` , обратите внимание на два уровня круглых скобок.  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 Если `str` аргумент заключен в круглые скобки в списке аргументов, `setNewString` процедура не может изменить ее значение в вызывающем коде и `MsgBox` выводит "не может быть заменен, если передано ByVal". Если `str` не заключен в круглые скобки, процедура может изменить ее и `MsgBox` выводит "это новое значение для аргумента строки".  
  
## <a name="compile-the-code"></a>Компиляция кода  

 При передаче переменной по ссылке необходимо использовать `ByRef` ключевое слово, чтобы указать этот механизм.  
  
 По умолчанию в Visual Basic передаются аргументы по значению. Однако рекомендуется включать ключевое слово [ByVal](../../../language-reference/modifiers/byval.md) или [ByRef](../../../language-reference/modifiers/byref.md) с каждым объявленным параметром. Это упрощает чтение кода.  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 Если процедура объявляет параметр [ByRef](../../../language-reference/modifiers/byref.md), правильное выполнение кода может зависеть от возможности изменения базового элемента в вызывающем коде. Если вызывающий код переопределяет этот механизм вызова, заключив аргумент в круглые скобки или передавая неизменяемый аргумент, процедура не может изменить базовый элемент. Это может привести к непредвиденным результатам в вызывающем коде.  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  

 Всегда существует потенциальный риск, позволяющий процедуре изменять значение, которое является базовым для аргумента в вызывающем коде. Убедитесь, что это значение было изменено, и будьте готовы проверить его на допустимость перед его использованием.  
  
## <a name="see-also"></a>См. также раздел

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Различия между изменяемыми и неизменяемыми аргументами](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Практическое руководство. Изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)
- [Практическое руководство. Защита аргумента процедуры от изменений значения](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../data-types/value-types-and-reference-types.md)

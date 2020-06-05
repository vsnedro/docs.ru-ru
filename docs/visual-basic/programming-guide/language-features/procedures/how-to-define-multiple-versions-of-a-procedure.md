---
title: Практическое руководство. Определение различных версий процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: 870a18dbf3a7e28b7d7b612e853beeec6908cf6f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387937"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Практическое руководство. Определение различных версий процедуры (Visual Basic)
Вы можете определить процедуру в нескольких версиях, *перегружая* ее, используя одно и то же имя, но различные списки параметров для каждой версии. Целью перегрузки является определение нескольких тесно связанных версий процедуры без необходимости отличать их по имени.  
  
 Дополнительные сведения см. в разделе [Procedure Overloading](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Определение нескольких версий процедуры  
  
1. Напишите `Sub` `Function` оператор объявления или для каждой версии процедуры, которую необходимо определить. Используйте одно и то же имя процедуры в каждом объявлении.  
  
2. Перед ключевым словом `Sub` или `Function` в каждом объявлении с ключевым словом [Overloads](../../../language-reference/modifiers/overloads.md) . При необходимости можно опустить `Overloads` объявления, но если включить его в любое из объявлений, его необходимо включить в каждое объявление.  
  
3. После каждого оператора объявления напишите код процедуры для обработки конкретного случая, когда вызывающий код предоставляет аргументы, соответствующие списку параметров этой версии. Нет необходимости проверять, какие параметры предоставил вызывающий код. Visual Basic передает управление соответствующей версии процедуры.  
  
4. При необходимости Завершите каждую версию процедуры `End Sub` `End Function` оператором или.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `Sub` процедура для публикации транзакции по балансу клиента. Он использует `Overloads` ключевое слово для определения двух версий процедуры, одна из которых принимает клиента по имени, а другая — по номеру счета.  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 Вызывающий код может получить идентификатор клиента как `String` или `Integer` , а затем использовать тот же оператор вызова в любом случае.  
  
 Сведения о том, как вызывать эти версии `post` процедуры, см. [в разделе как вызвать перегруженную процедуру](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compile-the-code"></a>Компиляция кода  
 Убедитесь, что Каждая перегруженная версия имеет одно и то же имя процедуры, но другой список параметров.  
  
## <a name="see-also"></a>См. также раздел

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)
- [Практическое руководство. Перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md)
- [Разрешение перегрузки](./overload-resolution.md)

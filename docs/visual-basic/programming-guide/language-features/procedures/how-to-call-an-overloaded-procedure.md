---
description: Дополнительные сведения см. в статье как вызвать перегруженную процедуру (Visual Basic).
title: Практическое руководство. Вызов перегруженной процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 6a67a598bd4a42964fd8fc01bc22b1b919f5e2a9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472596"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Практическое руководство. Вызов перегруженной процедуры (Visual Basic)

Преимущество перегрузки процедуры заключается в гибкости вызова. Вызывающий код может получить сведения, необходимые для передачи в процедуру, а затем вызвать одно имя процедуры независимо от передаваемых аргументов.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Вызов процедуры, для которой определено более одной версии  
  
1. В вызывающем коде определите, какие данные должны быть переданы в процедуру.  
  
2. Напишите вызов процедуры обычным способом, предоставляя данные в списке аргументов. Убедитесь, что аргументы соответствуют списку параметров в одной из версий, определенных для процедуры.  
  
3. Не нужно определять, какую версию процедуры нужно вызвать. Visual Basic передает управление версии, соответствующей списку аргументов.  
  
     В следующем примере вызывается `post` процедура, объявленная в разделе [как определить несколько версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md). Он получает идентификатор клиента, определяет, является ли он `String` или `Integer` , а затем в любом случае вызывает одну и ту же процедуру.  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>См. также раздел

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Перегрузка процедур](./procedure-overloading.md)
- [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)
- [Практическое руководство. Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)
- [Практическое руководство. Перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md)
- [Overload Resolution](./overload-resolution.md)
- [Перегрузки](../../../language-reference/modifiers/overloads.md)

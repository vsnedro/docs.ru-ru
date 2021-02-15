---
description: 'Дополнительные сведения о: как перегрузить процедуру, которая принимает неопределенное число параметров (Visual Basic)'
title: Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 97e391c2981760e012d56e1f93c24eb60ce3ebfe
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100460050"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров (Visual Basic)

Если процедура имеет параметр [ParamArray](../../../language-reference/modifiers/paramarray.md) , нельзя определить перегруженную версию, принимающую одномерный массив для массива параметров. Дополнительные сведения см. в разделе "Неявные перегрузки для параметра ParamArray" раздела [рекомендации по перегрузке процедур](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>Перегрузка процедуры, принимающей переменное число параметров  
  
1. Выясните, что процедура и вызов логики кода имеют преимущества от перегруженных версий больше, чем из `ParamArray` параметра. См. раздел "Overloads and Парамаррайс" в разделе [рекомендации по перегрузке процедур](./considerations-in-overloading-procedures.md).  
  
2. Определите, какое количество представленных значений должна принимать процедура в переменной части списка параметров. Это может включать отсутствие значения и может включать в себя регистр одного одномерного массива.  
  
3. Для каждого допустимого числа представленных значений напишите `Sub` `Function` оператор объявления или, определяющий соответствующий список параметров. Не используйте в `Optional` `ParamArray` этой перегруженной версии ключевое слово или.  
  
4. В каждом объявлении перед `Sub` `Function` ключевым словом или зарезервированным словом [Overloads](../../../language-reference/modifiers/overloads.md) .  
  
5. После каждого объявления напишите код процедуры, который должен выполняться, когда вызывающий код предоставляет значения, соответствующие списку параметров этого объявления.  
  
6. При необходимости Завершите каждую `End Sub` процедуру `End Function` оператором или.  
  
## <a name="example"></a>Пример  

 В следующем примере показана процедура, определенная с параметром [ParamArray](../../../language-reference/modifiers/paramarray.md) , а затем эквивалентный набор перегруженных процедур.  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 Невозможно перегрузить такую процедуру со списком параметров, принимающим одномерный массив для массива параметров. Однако можно использовать сигнатуры других неявных перегрузок. Это показано в следующих объявлениях.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 Код в перегруженных версиях не должен проверять, предоставлен ли вызывающему коду одно или несколько значений для `ParamArray` параметра, или, если да, то сколько. Visual Basic передает управление версии, соответствующей списку аргументов вызова.  
  
## <a name="compile-the-code"></a>Компиляция кода  

 Так как процедура с `ParamArray` параметром эквивалентна набору перегруженных версий, нельзя перегружать такую процедуру со списком параметров, соответствующим любому из этих неявных перегрузок. Дополнительные сведения см. [в разделе рекомендации по перегрузке процедур](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  

 Всякий раз при работе с массивом, который может быть неограниченным большим, существует риск перегрузки внутренней емкости приложения. Если вы принимаете массив параметров, следует проверить длину массива, которому был передан вызывающий код, и предпринять соответствующие шаги, если оно слишком велико для вашего приложения.  
  
## <a name="see-also"></a>См. также раздел

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Необязательные параметры](./optional-parameters.md)
- [Массивы параметров](./parameter-arrays.md)
- [Перегрузка процедур](./procedure-overloading.md)
- [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)
- [Практическое руководство. Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)
- [Практическое руководство. Вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md)
- [Практическое руководство. Перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Overload Resolution](./overload-resolution.md)

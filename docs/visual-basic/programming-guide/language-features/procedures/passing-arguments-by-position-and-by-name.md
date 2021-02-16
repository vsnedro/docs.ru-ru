---
description: 'Дополнительные сведения: Передача аргументов по положению и по имени (Visual Basic)'
title: Передача аргументов по позиции и по имени
ms.date: 02/01/2018
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
ms.openlocfilehash: 2938638bbdeb411bec53f338371d4215140dc4a0
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466696"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Передача аргументов по позиции и по имени (Visual Basic)

При вызове `Sub` процедуры или `Function` можно передавать аргументы *по положению* , в том порядке, в котором они отображаются в определении процедуры, или передавать их *по имени*, не обращаясь к положению.

При передаче аргумента по имени указывается объявленное имя аргумента, за которым следует двоеточие и знак равенства ( `:=` ), за которым следует значение аргумента. Именованные аргументы можно указывать в любом порядке.

Например, следующая `Sub` процедура принимает три аргумента:

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

При вызове этой процедуры аргументы можно указать по положению, по имени или с помощью сочетания обоих типов.

## <a name="passing-arguments-by-position"></a>Передача аргументов по положению

Метод можно вызвать `Display` с аргументами, передаваемыми по положению и разделенным запятыми, как показано в следующем примере:

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

Если необязательный аргумент не указан в списке позиционированных аргументов, необходимо держать его место с запятой. В следующем примере вызывается `Display` метод без `age` аргумента:

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a>Передача аргументов по имени

Кроме того, можно вызвать `Display` с аргументами, передаваемыми по имени, также разделенными запятыми, как показано в следующем примере:

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

Передача аргументов по имени таким способом особенно полезна при вызове процедуры, имеющей более одного необязательного аргумента. Если аргументы указываются по имени, не нужно использовать последовательные запятые для обозначения пропущенных аргументов. Передача аргументов по имени также упрощает отслеживание передаваемых аргументов и тех, которые вы пропускаете.

## <a name="mixing-arguments-by-position-and-by-name"></a>Смешивание аргументов по положению и по имени

Аргументы можно указать как по положению, так и по имени в одном вызове процедуры, как показано в следующем примере:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

В предыдущем примере не требуется дополнительная запятая для размещения пропущенного `age` аргумента, так как `birth` передается по имени.

В версиях Visual Basic до 15,5, при указании аргументов в сочетании с аргументами "расположение" и "имя" все аргументы должны быть первыми. После указания аргумента по имени все остальные аргументы должны передаваться по имени.  Например, при следующем вызове `Display` метода отображается ошибка компилятора [BC30241: Ожидается именованный аргумент](../../../misc/bc30241.md).

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

Начиная с Visual Basic 15,5, позиционированные аргументы могут следовать именованным аргументам, если конечные аргументы конца находятся в правильном положении. При компиляции в разделе Visual Basic 15,5 предыдущий вызов `Display` метода компилируется успешно и больше не создает ошибку компилятора [BC30241](../../../misc/bc30241.md).

Возможность смешивать и сопоставлять именованные и позиционированные аргументы в любом порядке особенно полезна, если нужно использовать именованный аргумент, чтобы сделать код более удобочитаемым. Например, следующий `Person` конструктор класса требует два аргумента типа `Person` , оба из которых могут иметь значение `Nothing` .

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

Использование смешанных именованных и позиционированных аргументов позволяет сделать код понятным, если `father` `mother` аргументы и имеют значение `Nothing` :

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

Чтобы следовать аргументам с именованными аргументами, необходимо добавить в файл проекта Visual Basic ( \* VBPROJ) следующий элемент:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Дополнительные сведения см. [в разделе Задание языковой версии Visual Basic](../../../language-reference/configure-language-version.md).

## <a name="restrictions-on-supplying-arguments-by-name"></a>Ограничения на предоставление аргументов по имени

Аргументы нельзя передавать по имени, чтобы избежать ввода обязательных аргументов. Можно опустить только необязательные аргументы.

Невозможно передать массив параметров по имени. Это происходит потому, что при вызове процедуры вы предоставляете неопределенное число аргументов, разделенных запятыми, для массива параметров, и компилятор не может связать более одного аргумента с одним именем.

## <a name="see-also"></a>См. также раздел

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Необязательные параметры](./optional-parameters.md)
- [Массивы параметров](./parameter-arrays.md)
- [Необязательно](../../../language-reference/modifiers/optional.md)
- [ParamArray](../../../language-reference/modifiers/paramarray.md)

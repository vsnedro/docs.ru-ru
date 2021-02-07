---
description: Дополнительные сведения см. в списке параметров (Visual Basic)
title: Список параметров
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: f69063fac82887ba4da3119d8ec4fcac11b7f4c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741410"
---
# <a name="parameter-list-visual-basic"></a>Список параметров (Visual Basic)

Указывает параметры, которые должны быть вызваны процедурой при ее вызове. Несколько параметров разделяются запятыми. Ниже приведен синтаксис для одного параметра.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a>Компоненты

`attributelist`  
Необязательный элемент. Список атрибутов, применяемых к этому параметру. [Список атрибутов](attribute-list.md) необходимо заключить в угловые скобки (" `<` " и " `>` ").

`Optional`  
Необязательный элемент. Указывает, что этот параметр не является обязательным при вызове процедуры.

`ByVal`  
Необязательный элемент. Указывает, что процедура не может заменить или переназначить элемент переменной, лежащий в основе соответствующего аргумента в вызывающем коде.

`ByRef`  
Необязательный элемент. Указывает, что процедура может изменить базовый элемент Variable в вызывающем коде так же, как и сам вызывающий код.

`ParamArray`  
Необязательный элемент. Указывает, что последний параметр в списке параметров является необязательным массивом элементов указанного типа данных. Это позволяет вызывающему коду передавать процедуре произвольное число аргументов.

`parametername`  
Обязательный элемент. Имя локальной переменной, представляющей параметр.

`parametertype`  
Обязательный `Option Strict` , если имеет значение `On` . Тип данных локальной переменной, представляющей параметр.

`defaultvalue`  
Требуется для `Optional` параметров. Любое константное или константное выражение, результатом которого является тип данных параметра. Если тип — `Object` , или класс, интерфейс, массив или структура, значением по умолчанию может быть только `Nothing` .

## <a name="remarks"></a>Remarks

Параметры заключаются в круглые скобки и разделяются запятыми. Параметр может быть объявлен с любым типом данных. Если не указать `parametertype` , по умолчанию используется значение `Object` .

Когда вызывающий код вызывает процедуру, он передает *аргумент* в каждый обязательный параметр. Дополнительные сведения см. в разделе [различия между параметрами и аргументами](../../programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).

Аргумент, который вызывающий код передает каждому параметру, является указателем на базовый элемент в вызывающем коде. Если этот элемент является *неизменяемым* (константой, литералом, перечислением или выражением), любой код изменить его невозможно. Если это элемент *переменной* (объявленная переменная, поле, свойство, элемент массива или элемент структуры), вызывающий код может изменить его. Дополнительные сведения см. в разделе [различия между изменяемыми и неизменяемыми аргументами](../../programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).

Если передается элемент переменной `ByRef` , процедура также может изменить ее. Дополнительные сведения см. в разделе [различия между передачей аргумента по значению и по ссылке](../../programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).

## <a name="rules"></a>Правила

- **Скобки.** Если указан список параметров, его необходимо заключить в круглые скобки. Если параметры отсутствуют, можно по-прежнему использовать круглые скобки, включающие пустой список. Это повышает удобочитаемость кода путем уточнения того, что элемент является процедурой.

- **Необязательные параметры.** При использовании `Optional` модификатора для параметра все последующие параметры в списке также должны быть необязательными и объявлены с помощью `Optional` модификатора.

     Каждое объявление необязательного параметра должно предоставлять `defaultvalue` предложение.

     Дополнительные сведения см. в разделе [необязательные параметры](../../programming-guide/language-features/procedures/optional-parameters.md).

- **Массивы параметров.** `ByVal`Для параметра необходимо указать `ParamArray` .

     `Optional`В одном списке параметров нельзя использовать и, и `ParamArray` .

     Дополнительные сведения см. в разделе [массивы параметров](../../programming-guide/language-features/procedures/parameter-arrays.md).

- **Механизм передачи.** Механизмом по умолчанию для каждого аргумента является `ByVal` , что означает, что процедура не может изменить базовый элемент Variable. Однако если элемент является ссылочным типом, процедура может изменить содержимое или члены базового объекта, даже если он не может заменить или переназначить сам объект.

- **Имена параметров.** Если тип данных параметра является массивом, `parametername` сразу после круглых скобок. Дополнительные сведения об именах параметров см. в разделе [Имена объявленных элементов](../../programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="example"></a>Пример

В следующем примере показана `Function` процедура, определяющая два параметра.

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Оператор Function](function-statement.md)
- [Оператор Sub](sub-statement.md)
- [Declare Statement](declare-statement.md)
- [Оператор Structure](structure-statement.md)
- [Оператор Option Strict](option-strict-statement.md)
- [Обзор атрибутов](../../programming-guide/concepts/attributes/index.md)
- [Практическое руководство. Разбиение и объединение инструкций в коде](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

---
description: 'Дополнительные сведения о: BC42110: тип для переменной " <variablename> " не будет определен, так как он привязан к полю во внешней области видимости'
title: Тип для переменной <variablename> не будет определен, так как она привязана к полю во включающей области
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: db31f1a6e87a2fd133f095e2fbdde7bc6bded97e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641243"
---
# <a name="bc42110-the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>BC42110: тип для переменной " \<variablename> " не будет определен, так как он привязан к полю во внешней области видимости

Тип для переменной " \<variablename> " не будет определен, так как он привязан к полю во внешней области видимости. Либо измените имя " \<variablename> ", либо используйте полное имя (например, "Me. variablename" или "MyBase. variablename").

Переменная цикла в коде имеет то же имя, что и поле класса или другой включающей области. Так как переменная управления используется без `As` предложения, она привязывается к полю во включающей области, и компилятор не создает для него новую переменную или не выводит ее тип.

В следующем примере `Index` Переменная элемента управления в `For` операторе привязана к `Index` полю в `Customer` классе. Компилятор не создает новую переменную для управляющей переменной `Index` или выводит ее тип.

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

    ' The following line will raise this warning.
        For Index = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

По умолчанию данное сообщение является предупреждением. Дополнительные сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки, см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

**Идентификатор ошибки:** BC42110

## <a name="to-address-this-warning"></a>Устранение предупреждения

- Сделайте переменную управления циклом локальной, изменив ее имя на идентификатор, который не является именем поля класса.

  ```vb
  For I = 1 To 10
  ```

- Уточните, что управляющая переменная цикла привязывается к полю класса путем добавления префикса `Me.` к имени переменной.

  ```vb
  For Me.Index = 1 To 10
  ```

- Вместо того чтобы полагаться на вывод локального типа, используйте `As` предложение, чтобы указать тип для управляющей переменной цикла.

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a>Пример

 В следующем коде показан предыдущий пример с первым исправлением.

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

        For I = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

## <a name="see-also"></a>См. также

- [Оператор Option Infer](../statements/option-infer-statement.md)
- [Оператор For Each…Next](../statements/for-each-next-statement.md)
- [Оператор For…Next](../statements/for-next-statement.md)
- [Практическое руководство. Ссылка на текущий экземпляр объекта](../../programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Вывод локального типа](../../programming-guide/language-features/variables/local-type-inference.md)
- [Me, My, MyBase и MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)

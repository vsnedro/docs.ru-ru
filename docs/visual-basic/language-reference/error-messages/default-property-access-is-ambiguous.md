---
description: 'Дополнительные сведения о: BC30686: неоднозначность доступа к свойству по умолчанию между унаследованными членами интерфейса "" <defaultpropertyname> интерфейса "" <interfacename1> и " <defaultpropertyname> " интерфейса "<interfacename2>'
title: 'При доступе к свойству по умолчанию возникает неоднозначность между членами наследуемых интерфейсов: <defaultpropertyname> интерфейса <interfacename1> и <defaultpropertyname> интерфейса <interfacename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 5ae5e5b2dc7a61540e26d125e960d4755141d975
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796656"
---
# <a name="bc30686-default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a>BC30686: неоднозначность доступа к свойству по умолчанию между унаследованными членами интерфейса "" \<defaultpropertyname> интерфейса "" \<interfacename1> и " \<defaultpropertyname> " интерфейса " \<interfacename2> "

Интерфейс наследует от двух интерфейсов, каждый из которых объявляет свойство по умолчанию с тем же именем. Компилятор не может разрешить доступ к этому свойству по умолчанию без уточнения. Это показано в следующем примере.

```vb
Public Interface Iface1
    Default Property prop(ByVal arg As Integer) As Integer
End Interface
Public Interface Iface2
    Default Property prop(ByVal arg As Integer) As Integer
End Interface
Public Interface Iface3
    Inherits Iface1, Iface2
End Interface
Public Class testClass
    Public Sub accessDefaultProperty()
        Dim testObj As Iface3
        Dim testInt As Integer = testObj(1)
    End Sub
End Class
```

При указании `testObj(1)` компилятор пытается разрешить его в свойство по умолчанию. Однако существует два возможных свойства по умолчанию из-за наследуемых интерфейсов, поэтому компилятор сообщает об этой ошибке.

**Идентификатор ошибки:** BC30686

## <a name="to-correct-this-error"></a>Исправление ошибки

- Избегайте наследования членов с одинаковыми именами. В предыдущем примере, если не `testObj` требуется ни один из членов, скажем, `Iface2` , объявить его следующим образом:

  ```vb
  Dim testObj As Iface1
  ```

  \-или-

- Реализуйте наследуемый интерфейс в классе. Затем можно реализовать каждое из наследуемых свойств с разными именами. Однако только один из них может быть свойством по умолчанию реализующего класса. Это показано в следующем примере.

  ```vb
  Public Class useIface3
      Implements Iface3
      Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop
          ' Insert code to define Get and Set procedures for prop1.
      End Property
      Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop
          ' Insert code to define Get and Set procedures for prop2.
      End Property
  End Class
  ```

## <a name="see-also"></a>См. также

- [Интерфейсы](../../programming-guide/language-features/interfaces/index.md)

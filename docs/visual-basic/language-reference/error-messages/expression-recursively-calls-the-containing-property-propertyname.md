---
title: Выражение рекурсивно вызывает содержащее свойство <propertyname>
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: e3a9f4cf2f4105d2c449813bf0c593860df7d1f0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409534"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a>Выражение рекурсивно вызывает содержащее свойство \<propertyname>
Оператор в `Set` процедуре определения свойства сохраняет значение в имени свойства.  
  
 Рекомендуемый подход к удержанию значения свойства — определить `Private` переменную в контейнере свойства и использовать ее в `Get` `Set` процедурах и. `Set`Процедура должна сохранить входящее значение в этой `Private` переменной.  
  
 `Get`Процедура ведет себя как `Function` процедура, поэтому ей можно присвоить значение имени свойства и вернуть управление, выполнив `End Get` инструкцию. Однако рекомендуемый подход заключается в включении `Private` переменной в качестве значения в [операторе return](../statements/return-statement.md).  
  
 `Set`Процедура ведет себя как `Sub` процедура, которая не возвращает значение. Следовательно, имя процедуры или свойства не имеет особого смысла в `Set` процедуре, и в ней нельзя хранить значение.  
  
 В следующем примере показан подход, который может вызвать эту ошибку, за которым следует рекомендуемый подход.  
  
```vb  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. [в разделе Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42026  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Перепишите определение свойства, чтобы использовать рекомендуемый подход, как показано в предыдущем примере.  
  
## <a name="see-also"></a>См. также раздел

- [Процедуры свойств](../../programming-guide/language-features/procedures/property-procedures.md)
- [Property Statement](../statements/property-statement.md)
- [Инструкция SET](../statements/set-statement.md)

---
description: Дополнительные сведения:?. перетаскивани? ()-условные операторы null (Visual Basic)
title: Условные операторы null
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 558b8921d0da4089505dd1035cb6039af24a2802
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665371"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. перетаскивани? ()-условные операторы null (Visual Basic)

Проверяет значение левого операнда для NULL ( `Nothing` ) перед выполнением операции доступа к члену ( `?.` ) или индекса ( `?()` ); возвращает, `Nothing` если левый операнд принимает значение `Nothing` . Обратите внимание, что в выражениях, которые обычно возвращают типы значений, условный оператор null возвращает <xref:System.Nullable%601> .

Эти операторы помогают писать меньше кода для проверки значений NULL, особенно при сортировке по структурам данных. Пример:

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

Для сравнения альтернативный код для первого из этих выражений без условного оператора null имеет значение:

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

Иногда необходимо выполнить действие над объектом, который может иметь значение null, на основе значения логического элемента в этом объекте (например, логическое свойство `IsAllowedFreeShipping` в следующем примере):

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

Вы можете сократить код и избежать ручной проверки значения NULL с помощью оператора Conditional, как показано ниже:

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

Операторы с условием NULL предусматривают сокращенную обработку.  Если одна операция в цепочке операций доступа к условному элементу и операциям с индексами возвращает `Nothing` , оставшаяся часть выполнения цепочки останавливается.  В следующем примере `C(E)` не вычисляется, если `A` , `B` или `C` имеет значение `Nothing` .

```vb
A?.B?.C?(E)
```

Другим вариантом использования для доступа к членам с атрибутом null является вызов делегатов потокобезопасным способом с гораздо меньшим объемом кода.  В следующем примере определяются два типа: `NewsBroadcaster` и `NewsReceiver` . Элементы новостей отправляются получателю `NewsBroadcaster.SendNews` делегатом.

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String)

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

Если в `SendNews` списке вызовов нет элементов, `SendNews` делегат создает исключение <xref:System.NullReferenceException> . Перед пустыми условными операторами, код, подобный приведенному ниже, гарантирует, что список вызовов делегата не был `Nothing` :

```vb
SendNews = SendNews.Combine({SendNews, client})
If SendNews IsNot Nothing Then
   SendNews("Just in...")
End If
```

Новый способ гораздо проще:

```vb
SendNews = SendNews.Combine({SendNews, client})
SendNews?.Invoke("Just in...")
```

Новый способ является потокобезопасным, так как компилятор создает код для вычисления `SendNews` только один раз, запоминая результат во временной переменной. Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `SendNews?(String)` для вызова делегатов с условием NULL.

## <a name="see-also"></a>См. также

- [Операторы (Visual Basic)](index.md)
- [Руководство по программированию на Visual Basic](../../programming-guide/index.md)
- [Справочник по языку Visual Basic](../index.md)

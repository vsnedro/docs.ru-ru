---
title: Практическое руководство. Вызов метода делегата
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: f319727c007b93c7b334af0598f1b9f7c034144d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410725"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="8870a-102">Практическое руководство. Вызов метода делегата (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8870a-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>

<span data-ttu-id="8870a-103">В этом примере показано, как связать метод с делегатом, а затем вызвать этот метод через делегат.</span><span class="sxs-lookup"><span data-stu-id="8870a-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>

### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="8870a-104">Создание делегата и процедур сопоставления</span><span class="sxs-lookup"><span data-stu-id="8870a-104">Create the delegate and matching procedures</span></span>

1. <span data-ttu-id="8870a-105">Создайте делегат с именем `MySubDelegate` .</span><span class="sxs-lookup"><span data-stu-id="8870a-105">Create a delegate named `MySubDelegate`.</span></span>

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. <span data-ttu-id="8870a-106">Объявите класс, содержащий метод с той же сигнатурой, что и у делегата.</span><span class="sxs-lookup"><span data-stu-id="8870a-106">Declare a class that contains a method with the same signature as the delegate.</span></span>

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. <span data-ttu-id="8870a-107">Определите метод, который создает экземпляр делегата и вызывает метод, связанный с делегатом, вызвав встроенный `Invoke` метод.</span><span class="sxs-lookup"><span data-stu-id="8870a-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a><span data-ttu-id="8870a-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8870a-108">See also</span></span>

- [<span data-ttu-id="8870a-109">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="8870a-109">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="8870a-110">Делегаты</span><span class="sxs-lookup"><span data-stu-id="8870a-110">Delegates</span></span>](index.md)
- [<span data-ttu-id="8870a-111">События</span><span class="sxs-lookup"><span data-stu-id="8870a-111">Events</span></span>](../events/index.md)
- [<span data-ttu-id="8870a-112">Многопоточные приложения</span><span class="sxs-lookup"><span data-stu-id="8870a-112">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)

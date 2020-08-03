---
title: Использование вариативности в универсальных методах-делегатах Func и Action (C#)
description: Узнайте об использовании ковариации и контрвариантности в универсальных делегатах Func и Action для формирования более гибкого кода.
ms.date: 07/20/2015
ms.assetid: 1826774f-2b7a-470f-b110-17cfdd6abdae
ms.openlocfilehash: d7174b0f734d10ab69d0936cb5ca4aa2f4fafdf7
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105704"
---
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a><span data-ttu-id="26e2a-103">Использование вариативности в универсальных методах-делегатах Func и Action (C#)</span><span class="sxs-lookup"><span data-stu-id="26e2a-103">Using Variance for Func and Action Generic Delegates (C#)</span></span>
<span data-ttu-id="26e2a-104">Эти примеры показывают, как обеспечить возможность многократного использования методов и сделать код более гибким, используя ковариацию и контравариацию в универсальных методах-делегатах `Func` и `Action`.</span><span class="sxs-lookup"><span data-stu-id="26e2a-104">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>  
  
 <span data-ttu-id="26e2a-105">Дополнительные сведения о ковариации и контравариации см. в разделе [Вариативность в делегатах (C#)](./variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="26e2a-105">For more information about covariance and contravariance, see [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="26e2a-106">Использование методов-делегатов с параметрами ковариантного типа</span><span class="sxs-lookup"><span data-stu-id="26e2a-106">Using Delegates with Covariant Type Parameters</span></span>  
 <span data-ttu-id="26e2a-107">Следующий пример иллюстрирует преимущества поддержки ковариации в универсальных методах-делегатах `Func`.</span><span class="sxs-lookup"><span data-stu-id="26e2a-107">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="26e2a-108">Метод `FindByTitle` принимает параметр типа `String` и возвращает объект типа `Employee`.</span><span class="sxs-lookup"><span data-stu-id="26e2a-108">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="26e2a-109">При этом данный метод можно назначить методу-делегату `Func<String, Person>`, поскольку `Employee` наследует `Person`.</span><span class="sxs-lookup"><span data-stu-id="26e2a-109">However, you can assign this method to the `Func<String, Person>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static Employee FindByTitle(String title)  
    {  
        // This is a stub for a method that returns  
        // an employee that has the specified title.  
        return new Employee();  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Func<String, Employee> findEmployee = FindByTitle;  
  
        // The delegate expects a method to return Person,  
        // but you can assign it a method that returns Employee.  
        Func<String, Person> findPerson = FindByTitle;  
  
        // You can also assign a delegate
        // that returns a more derived type
        // to a delegate that returns a less derived type.  
        findPerson = findEmployee;  
  
    }  
}  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="26e2a-110">Использование методов-делегатов с параметрами контравариантного типа</span><span class="sxs-lookup"><span data-stu-id="26e2a-110">Using Delegates with Contravariant Type Parameters</span></span>  
 <span data-ttu-id="26e2a-111">Следующий пример иллюстрирует преимущества поддержки контравариации в универсальных методах-делегатах `Action`.</span><span class="sxs-lookup"><span data-stu-id="26e2a-111">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="26e2a-112">Метод `AddToContacts` принимает параметр типа `Person`.</span><span class="sxs-lookup"><span data-stu-id="26e2a-112">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="26e2a-113">При этом данный метод можно назначить методу-делегату `Action<Employee>`, поскольку `Employee` наследует `Person`.</span><span class="sxs-lookup"><span data-stu-id="26e2a-113">However, you can assign this method to the `Action<Employee>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static void AddToContacts(Person person)  
    {  
        // This method adds a Person object  
        // to a contact list.  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Action<Person> addPersonToContacts = AddToContacts;  
  
        // The Action delegate expects
        // a method that has an Employee parameter,  
        // but you can assign it a method that has a Person parameter  
        // because Employee derives from Person.  
        Action<Employee> addEmployeeToContacts = AddToContacts;  
  
        // You can also assign a delegate
        // that accepts a less derived parameter to a delegate
        // that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="26e2a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="26e2a-114">See also</span></span>

- [<span data-ttu-id="26e2a-115">Ковариация и контрвариантность (C#)</span><span class="sxs-lookup"><span data-stu-id="26e2a-115">Covariance and Contravariance (C#)</span></span>](./index.md)
- [<span data-ttu-id="26e2a-116">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="26e2a-116">Generics</span></span>](../../../../standard/generics/index.md)

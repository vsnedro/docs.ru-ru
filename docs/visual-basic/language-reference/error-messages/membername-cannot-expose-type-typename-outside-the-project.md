---
title: <membername> не может представлять тип <typename> вне проекта посредством <containertype><containertypename>
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 31d44c93d62163df4d81cb8503b633f0eb317372
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873811"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="13aeb-102">\<membername> не может представлять тип \<typename> вне проекта посредством \<containertype>\<containertypename></span><span class="sxs-lookup"><span data-stu-id="13aeb-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>

<span data-ttu-id="13aeb-103">Переменная, параметр процедуры или возвращаемое значение функции предоставляется за пределами своего контейнера, но она объявляется как тип, который не должен предоставляться за пределами контейнера.</span><span class="sxs-lookup"><span data-stu-id="13aeb-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="13aeb-104">В приведенном ниже коде показана ситуация, которая приводит к возникновению этой ошибки.</span><span class="sxs-lookup"><span data-stu-id="13aeb-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="13aeb-105">Тип, который объявлен как `Protected` , `Friend` , `Protected Friend` или, `Private` предназначен для ограниченного доступа за пределами контекста объявления.</span><span class="sxs-lookup"><span data-stu-id="13aeb-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="13aeb-106">Использование его в качестве типа данных переменной с меньшим доступом было бы непреднамеренно.</span><span class="sxs-lookup"><span data-stu-id="13aeb-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="13aeb-107">В предыдущем скелете кода `exposedVar` имеет значение `Public` и будет предоставлять `privateClass` код, который не должен иметь к нему доступа.</span><span class="sxs-lookup"><span data-stu-id="13aeb-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="13aeb-108">**Идентификатор ошибки:** BC30909</span><span class="sxs-lookup"><span data-stu-id="13aeb-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="13aeb-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="13aeb-109">To correct this error</span></span>  
  
- <span data-ttu-id="13aeb-110">Измените уровень доступа переменной, параметра процедуры или функции, чтобы он был по крайней мере ограничен уровнем доступа его типа данных.</span><span class="sxs-lookup"><span data-stu-id="13aeb-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13aeb-111">См. также</span><span class="sxs-lookup"><span data-stu-id="13aeb-111">See also</span></span>

- [<span data-ttu-id="13aeb-112">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13aeb-112">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)

---
title: Тип <typename> не определен
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 89e2d1d18b456c96f62d6b9ee1dd8dc9d41bf665
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386936"
---
# <a name="type-typename-is-not-defined"></a><span data-ttu-id="87e30-102">Тип \<typename> не определен</span><span class="sxs-lookup"><span data-stu-id="87e30-102">Type '\<typename>' is not defined</span></span>
<span data-ttu-id="87e30-103">Оператор выполнил ссылку на тип, который не был определен.</span><span class="sxs-lookup"><span data-stu-id="87e30-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="87e30-104">Тип можно определить в операторе объявления, например,, `Enum` `Structure` `Class` или `Interface` .</span><span class="sxs-lookup"><span data-stu-id="87e30-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="87e30-105">**Идентификатор ошибки:** BC30002</span><span class="sxs-lookup"><span data-stu-id="87e30-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="87e30-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="87e30-106">To correct this error</span></span>  
  
- <span data-ttu-id="87e30-107">Убедитесь, что определение типа и его ссылка используют одинаковое написание.</span><span class="sxs-lookup"><span data-stu-id="87e30-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
- <span data-ttu-id="87e30-108">Убедитесь, что определение типа доступно для ссылки.</span><span class="sxs-lookup"><span data-stu-id="87e30-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="87e30-109">Например, если тип находится в другом модуле и был объявлен `Private` , переместите определение типа в ссылающийся модуль или объявите его `Public` .</span><span class="sxs-lookup"><span data-stu-id="87e30-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
- <span data-ttu-id="87e30-110">Убедитесь, что пространство имен типа не переопределено в проекте.</span><span class="sxs-lookup"><span data-stu-id="87e30-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="87e30-111">Если это так, используйте `Global` ключевое слово, чтобы полностью определить имя типа.</span><span class="sxs-lookup"><span data-stu-id="87e30-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="87e30-112">Например, если проект определяет пространство имен с именем `System` , доступ к этому <xref:System.Object?displayProperty=nameWithType> типу невозможен, если он не является полным с `Global` ключевым словом: `Global.System.Object` .</span><span class="sxs-lookup"><span data-stu-id="87e30-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
- <span data-ttu-id="87e30-113">Если тип определен, но библиотека объектов или библиотека типов, в которой он определен, не зарегистрирована в Visual Basic, щелкните **Добавить ссылку** в меню **проект** , а затем выберите соответствующую библиотеку объектов или библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="87e30-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
- <span data-ttu-id="87e30-114">Убедитесь, что тип находится в сборке, которая является частью целевого .NET Framework профиля.</span><span class="sxs-lookup"><span data-stu-id="87e30-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="87e30-115">Дополнительные сведения см. в разделе [Устранение неполадок .NET Framework нацеливание на ошибки](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="87e30-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e30-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="87e30-116">See also</span></span>

- [<span data-ttu-id="87e30-117">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="87e30-117">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="87e30-118">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="87e30-118">Enum Statement</span></span>](../statements/enum-statement.md)
- [<span data-ttu-id="87e30-119">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="87e30-119">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="87e30-120">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="87e30-120">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="87e30-121">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="87e30-121">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="87e30-122">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="87e30-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)

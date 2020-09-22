---
title: Тип <typename> не определен
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 3c22e6a5199bd52cb9fae66a15a66ac9ce095e81
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872196"
---
# <a name="type-typename-is-not-defined"></a><span data-ttu-id="125e2-102">Тип \<typename> не определен</span><span class="sxs-lookup"><span data-stu-id="125e2-102">Type '\<typename>' is not defined</span></span>

<span data-ttu-id="125e2-103">Оператор выполнил ссылку на тип, который не был определен.</span><span class="sxs-lookup"><span data-stu-id="125e2-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="125e2-104">Тип можно определить в операторе объявления, например,, `Enum` `Structure` `Class` или `Interface` .</span><span class="sxs-lookup"><span data-stu-id="125e2-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="125e2-105">**Идентификатор ошибки:** BC30002</span><span class="sxs-lookup"><span data-stu-id="125e2-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="125e2-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="125e2-106">To correct this error</span></span>  
  
- <span data-ttu-id="125e2-107">Убедитесь, что определение типа и его ссылка используют одинаковое написание.</span><span class="sxs-lookup"><span data-stu-id="125e2-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
- <span data-ttu-id="125e2-108">Убедитесь, что определение типа доступно для ссылки.</span><span class="sxs-lookup"><span data-stu-id="125e2-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="125e2-109">Например, если тип находится в другом модуле и был объявлен `Private` , переместите определение типа в ссылающийся модуль или объявите его `Public` .</span><span class="sxs-lookup"><span data-stu-id="125e2-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
- <span data-ttu-id="125e2-110">Убедитесь, что пространство имен типа не переопределено в проекте.</span><span class="sxs-lookup"><span data-stu-id="125e2-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="125e2-111">Если это так, используйте `Global` ключевое слово, чтобы полностью определить имя типа.</span><span class="sxs-lookup"><span data-stu-id="125e2-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="125e2-112">Например, если проект определяет пространство имен с именем `System` , доступ к этому <xref:System.Object?displayProperty=nameWithType> типу невозможен, если он не является полным с `Global` ключевым словом: `Global.System.Object` .</span><span class="sxs-lookup"><span data-stu-id="125e2-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
- <span data-ttu-id="125e2-113">Если тип определен, но библиотека объектов или библиотека типов, в которой он определен, не зарегистрирована в Visual Basic, щелкните **Добавить ссылку** в меню **проект** , а затем выберите соответствующую библиотеку объектов или библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="125e2-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
- <span data-ttu-id="125e2-114">Убедитесь, что тип находится в сборке, которая является частью целевого .NET Framework профиля.</span><span class="sxs-lookup"><span data-stu-id="125e2-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="125e2-115">Дополнительные сведения см. в разделе [Устранение неполадок, связанных с настройкой для определенных версий платформы .NET Framework](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="125e2-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="125e2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="125e2-116">See also</span></span>

- [<span data-ttu-id="125e2-117">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="125e2-117">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="125e2-118">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="125e2-118">Enum Statement</span></span>](../statements/enum-statement.md)
- [<span data-ttu-id="125e2-119">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="125e2-119">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="125e2-120">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="125e2-120">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="125e2-121">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="125e2-121">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="125e2-122">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="125e2-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)

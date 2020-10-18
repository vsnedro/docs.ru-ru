---
title: Тип <typename> не определен
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 195e749e29494d438dbd052e8e308250f4cce1ca
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161898"
---
# <a name="bc30002-type-typename-is-not-defined"></a><span data-ttu-id="571d3-102">BC30002: тип " \<typename> " не определен</span><span class="sxs-lookup"><span data-stu-id="571d3-102">BC30002: Type '\<typename>' is not defined</span></span>

<span data-ttu-id="571d3-103">Оператор выполнил ссылку на тип, который не был определен.</span><span class="sxs-lookup"><span data-stu-id="571d3-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="571d3-104">Тип можно определить в операторе объявления, например,, `Enum` `Structure` `Class` или `Interface` .</span><span class="sxs-lookup"><span data-stu-id="571d3-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>

 <span data-ttu-id="571d3-105">**Идентификатор ошибки:** BC30002</span><span class="sxs-lookup"><span data-stu-id="571d3-105">**Error ID:** BC30002</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="571d3-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="571d3-106">To correct this error</span></span>

- <span data-ttu-id="571d3-107">Убедитесь, что определение типа и его ссылка используют одинаковое написание.</span><span class="sxs-lookup"><span data-stu-id="571d3-107">Ensure that the type definition and its reference both use the same spelling.</span></span>

- <span data-ttu-id="571d3-108">Убедитесь, что определение типа доступно для ссылки.</span><span class="sxs-lookup"><span data-stu-id="571d3-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="571d3-109">Например, если тип находится в другом модуле и был объявлен `Private` , переместите определение типа в ссылающийся модуль или объявите его `Public` .</span><span class="sxs-lookup"><span data-stu-id="571d3-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>

- <span data-ttu-id="571d3-110">Убедитесь, что пространство имен типа не переопределено в проекте.</span><span class="sxs-lookup"><span data-stu-id="571d3-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="571d3-111">Если это так, используйте `Global` ключевое слово, чтобы полностью определить имя типа.</span><span class="sxs-lookup"><span data-stu-id="571d3-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="571d3-112">Например, если проект определяет пространство имен с именем `System` , доступ к этому <xref:System.Object?displayProperty=nameWithType> типу невозможен, если он не является полным с `Global` ключевым словом: `Global.System.Object` .</span><span class="sxs-lookup"><span data-stu-id="571d3-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>

- <span data-ttu-id="571d3-113">Если тип определен, но библиотека объектов или библиотека типов, в которой он определен, не зарегистрирована в Visual Basic, щелкните **Добавить ссылку** в меню **проект** , а затем выберите соответствующую библиотеку объектов или библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="571d3-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>

- <span data-ttu-id="571d3-114">Убедитесь, что тип находится в сборке, которая является частью целевого .NET Framework профиля.</span><span class="sxs-lookup"><span data-stu-id="571d3-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="571d3-115">Дополнительные сведения см. в разделе [Устранение неполадок, связанных с настройкой для определенных версий платформы .NET Framework](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="571d3-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>

## <a name="see-also"></a><span data-ttu-id="571d3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="571d3-116">See also</span></span>

- [<span data-ttu-id="571d3-117">Пространства имен в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="571d3-117">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="571d3-118">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="571d3-118">Enum Statement</span></span>](../statements/enum-statement.md)
- [<span data-ttu-id="571d3-119">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="571d3-119">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="571d3-120">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="571d3-120">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="571d3-121">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="571d3-121">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="571d3-122">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="571d3-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)

---
title: Требуется ссылка на сборку <assemblyname>, содержащую базовый класс <classname>
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: d2fb3498219dfe3318ec418ede250de818874ba9
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162340"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a><span data-ttu-id="1361c-102">BC30007: требуется ссылка на сборку " \<assemblyname> ", содержащую базовый класс " \<classname> "</span><span class="sxs-lookup"><span data-stu-id="1361c-102">BC30007: Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'</span></span>

<span data-ttu-id="1361c-103">Требуется ссылка на сборку " \<assemblyname> ", содержащую базовый класс " \<classname> ".</span><span class="sxs-lookup"><span data-stu-id="1361c-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="1361c-104">Добавьте эту ссылку в проект.</span><span class="sxs-lookup"><span data-stu-id="1361c-104">Add one to your project.</span></span>

 <span data-ttu-id="1361c-105">Класс определяется в библиотеке динамической компоновки (DLL) или в сборке, на которую в проекте нет прямой ссылки.</span><span class="sxs-lookup"><span data-stu-id="1361c-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="1361c-106">Компилятору Visual Basic требуется ссылка, чтобы избежать неоднозначности в случае, если класс определен в нескольких библиотеках DLL или сборках.</span><span class="sxs-lookup"><span data-stu-id="1361c-106">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>

 <span data-ttu-id="1361c-107">**Идентификатор ошибки:** BC30007</span><span class="sxs-lookup"><span data-stu-id="1361c-107">**Error ID:** BC30007</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1361c-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1361c-108">To correct this error</span></span>

- <span data-ttu-id="1361c-109">Включите в ссылки проекта имя библиотеки DLL или сборки, на которую нет ссылки.</span><span class="sxs-lookup"><span data-stu-id="1361c-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>

## <a name="see-also"></a><span data-ttu-id="1361c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1361c-110">See also</span></span>

- [<span data-ttu-id="1361c-111">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="1361c-111">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="1361c-112">Troubleshooting Broken References</span><span class="sxs-lookup"><span data-stu-id="1361c-112">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)

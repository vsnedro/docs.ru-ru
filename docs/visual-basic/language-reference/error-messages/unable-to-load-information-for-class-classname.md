---
title: Не удается выполнить загрузку сведений для класса <classname>
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 05c3303db90a396479bc396c5c2395c3afbb59ae
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161612"
---
# <a name="bc30712-unable-to-load-information-for-class-classname"></a><span data-ttu-id="d4f8d-102">BC30712: не удалось загрузить сведения для класса " \<classname> "</span><span class="sxs-lookup"><span data-stu-id="d4f8d-102">BC30712: Unable to load information for class '\<classname>'</span></span>

<span data-ttu-id="d4f8d-103">Была сделана ссылка на класс, который недоступен.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-103">A reference was made to a class that is not available.</span></span>

 <span data-ttu-id="d4f8d-104">**Идентификатор ошибки:** BC30712</span><span class="sxs-lookup"><span data-stu-id="d4f8d-104">**Error ID:** BC30712</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d4f8d-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d4f8d-105">To correct this error</span></span>

1. <span data-ttu-id="d4f8d-106">Убедитесь, что класс определен и имя указано правильно.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-106">Verify that the class is defined and that you spelled the name correctly.</span></span>

2. <span data-ttu-id="d4f8d-107">Попробуйте обратиться к одному из членов, объявленных в модуле.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="d4f8d-108">В некоторых случаях среда отладки не может найти члены, потому что модули, в которых они объявлены, еще не были загружены.</span><span class="sxs-lookup"><span data-stu-id="d4f8d-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4f8d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d4f8d-109">See also</span></span>

- [<span data-ttu-id="d4f8d-110">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d4f8d-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)

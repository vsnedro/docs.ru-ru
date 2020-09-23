---
title: Слишком много приложений-клиентов DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
ms.openlocfilehash: dcac2658b18b753166770ba5b67024fe88b78b45
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078428"
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="37626-102">Слишком много приложений-клиентов DLL</span><span class="sxs-lookup"><span data-stu-id="37626-102">Too many DLL application clients</span></span>

<span data-ttu-id="37626-103">Библиотека динамической компоновки (DLL) для Visual Basic может поддерживать доступ только ограниченное количество ведущих приложений.</span><span class="sxs-lookup"><span data-stu-id="37626-103">The dynamic-link library (DLL) for Visual Basic can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="37626-104">Приложение и другие приложения, Visual Basic узлы (некоторые из которых могут быть доступны приложению), пытаются одновременно получить доступ к библиотеке DLL Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="37626-104">Your application and other applications that are Visual Basic hosts (some of which may be accessed by your application) are all attempting to access the Visual Basic DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="37626-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="37626-105">To correct this error</span></span>  
  
- <span data-ttu-id="37626-106">Сократите число открытых приложений, обращающихся к Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="37626-106">Reduce the number of open applications accessing Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37626-107">См. также</span><span class="sxs-lookup"><span data-stu-id="37626-107">See also</span></span>

- [<span data-ttu-id="37626-108">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="37626-108">Error Types</span></span>](../programming-guide/language-features/error-types.md)

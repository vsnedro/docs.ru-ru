---
title: Доступ к формам приложения
ms.date: 07/20/2015
helpviewer_keywords:
- forms [Visual Basic], communicating between
- application forms [Visual Basic], accessing
- forms [Visual Basic], accessing one from another
- My.Forms object
- forms [Visual Basic], accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
ms.openlocfilehash: 44f98632fd2fd6c4c087a78b805d5b7da750df87
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410209"
---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="ae878-102">Доступ к формам приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae878-102">Accessing Application Forms (Visual Basic)</span></span>

<span data-ttu-id="ae878-103">Объект `My.Forms` предоставляет простой способ доступа к экземпляру каждой формы Windows, объявленной в проекте приложения.</span><span class="sxs-lookup"><span data-stu-id="ae878-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="ae878-104">Для доступа к экрану-заставке и основной форме приложения, а также для получения списка открытых форм приложения можно также использовать свойства объекта `My.Application`.</span><span class="sxs-lookup"><span data-stu-id="ae878-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="ae878-105">Задания</span><span class="sxs-lookup"><span data-stu-id="ae878-105">Tasks</span></span>  

 <span data-ttu-id="ae878-106">Приведенная ниже таблица содержит примеры, показывающие, как получить доступ к формам приложения.</span><span class="sxs-lookup"><span data-stu-id="ae878-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="ae878-107">Чтобы</span><span class="sxs-lookup"><span data-stu-id="ae878-107">To</span></span>|<span data-ttu-id="ae878-108">См.</span><span class="sxs-lookup"><span data-stu-id="ae878-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="ae878-109">Доступ к одной форме приложения из другой</span><span class="sxs-lookup"><span data-stu-id="ae878-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="ae878-110">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="ae878-110">My.Forms Object</span></span>](../../language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="ae878-111">Отображение заголовков всех открытых форм приложения</span><span class="sxs-lookup"><span data-stu-id="ae878-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="ae878-112">Обновление данных о состоянии на экране-заставке при запуске приложения</span><span class="sxs-lookup"><span data-stu-id="ae878-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="ae878-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ae878-113">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>
- [<span data-ttu-id="ae878-114">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="ae878-114">My.Forms Object</span></span>](../../language-reference/objects/my-forms-object.md)

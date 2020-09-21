---
title: Разработка клиентских приложений Windows с использованием .NET Framework
description: Разработка приложений Windows с использованием .NET. Вы можете использовать универсальную платформу Windows (UWP), Windows Presentation Foundation (WPF) или Windows Forms.
ms.date: 01/09/2018
helpviewer_keywords:
- client application services
- applications [Windows Forms]
- Windows Presentation Foundation, in Visual Studio
- WPF, in Visual Studio
- Windows applications
- rich client applications
- .NET applications, Windows applications
- Visual Basic code, creating applications
- Visual C#, creating applications
- client/server applications, Windows applications
ms.assetid: 2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68
ms.openlocfilehash: 33d0ca2918e4e3b00e2b09f7a47c538bbe903dba
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547913"
---
# <a name="develop-client-applications-with-net-framework"></a><span data-ttu-id="6f400-104">Разработка клиентских приложений с использованием .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6f400-104">Develop client applications with .NET Framework</span></span>

<span data-ttu-id="6f400-105">Существует несколько способов разработки приложений Windows с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f400-105">There are several ways to develop Windows-based applications with .NET Framework.</span></span> <span data-ttu-id="6f400-106">Вы можете использовать любые из этих средств и платформ.</span><span class="sxs-lookup"><span data-stu-id="6f400-106">You can use any of these tools and frameworks:</span></span>

- [<span data-ttu-id="6f400-107">Универсальная платформа Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="6f400-107">Universal Windows Platform (UWP)</span></span>](/windows/uwp/)
- [<span data-ttu-id="6f400-108">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="6f400-108">Windows Presentation Foundation (WPF)</span></span>](/dotnet/desktop/wpf/)
- [<span data-ttu-id="6f400-109">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f400-109">Windows Forms</span></span>](/dotnet/desktop/winforms/)

<span data-ttu-id="6f400-110">В темах этой статьи описаны способы создания приложений Windows с помощью Windows Presentation Foundation и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6f400-110">This section contains articles that describe how to create Windows-based applications by using Windows Presentation Foundation or Windows Forms.</span></span> <span data-ttu-id="6f400-111">Но с помощью .NET Framework вы можете создавать и веб-приложения, а также клиентские приложения для компьютеров и устройств, публикуемые в Microsoft Store (приложения универсальной платформы Windows).</span><span class="sxs-lookup"><span data-stu-id="6f400-111">However, you can also create web applications using .NET Framework and client applications for computers or devices that you make available through Microsoft Store (UWP apps).</span></span>

## <a name="related-sections"></a><span data-ttu-id="6f400-112">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6f400-112">Related sections</span></span>

<span data-ttu-id="6f400-113">[Универсальная платформа Windows](/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="6f400-113">[Universal Windows Platform](/windows/uwp/)</span></span>\
<span data-ttu-id="6f400-114">Создание приложений универсальной платформы Windows (UWP) для предоставления пользователям через Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="6f400-114">Describes how to create UWP applications that you can make available to users through Microsoft Store.</span></span>

<span data-ttu-id="6f400-115">[.NET API для приложений UWP](../../api/index.md?view=dotnet-uwp-10.0)</span><span class="sxs-lookup"><span data-stu-id="6f400-115">[.NET API for UWP apps](../../api/index.md?view=dotnet-uwp-10.0)</span></span>\
<span data-ttu-id="6f400-116">Справочник по типам .NET, которые поддерживают приложения UWP.</span><span class="sxs-lookup"><span data-stu-id="6f400-116">Reference for .NET types that support UWP apps.</span></span>
  
<span data-ttu-id="6f400-117">[Разработка для множества платформ](../standard/cross-platform/index.md)</span><span class="sxs-lookup"><span data-stu-id="6f400-117">[Develop for Multiple Platforms](../standard/cross-platform/index.md)</span></span>\
<span data-ttu-id="6f400-118">Описание методов, которыми можно использовать .NET Framework для разных типов клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="6f400-118">Describes the different methods you can use .NET Framework to target multiple client app types.</span></span>

<span data-ttu-id="6f400-119">[Начало работы с веб-страницами ASP.NET](https://dotnet.microsoft.com/apps/aspnet/web-apps)</span><span class="sxs-lookup"><span data-stu-id="6f400-119">[Get Started with ASP.NET Web Sites](https://dotnet.microsoft.com/apps/aspnet/web-apps)</span></span>\
<span data-ttu-id="6f400-120">Способы разработки веб-приложений с помощью ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6f400-120">Describes the ways you can develop web apps using ASP.NET.</span></span>

<span data-ttu-id="6f400-121">[.NET API для Windows Phone Silverlight](/previous-versions/windows/apps/jj207211\(v=vs.105\))</span><span class="sxs-lookup"><span data-stu-id="6f400-121">[.NET API for Windows Phone Silverlight](/previous-versions/windows/apps/jj207211\(v=vs.105\))</span></span>\
<span data-ttu-id="6f400-122">Список API-интерфейсов .NET Framework, которые можно использовать для создания приложений с помощью Windows Phone Silverlight.</span><span class="sxs-lookup"><span data-stu-id="6f400-122">Lists .NET Framework APIs you can use for building apps with Windows Phone Silverlight.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f400-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6f400-123">See also</span></span>

- [<span data-ttu-id="6f400-124">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="6f400-124">.NET Standard</span></span>](../standard/net-standard.md)
- [<span data-ttu-id="6f400-125">Обзор</span><span class="sxs-lookup"><span data-stu-id="6f400-125">Overview</span></span>](./get-started/overview.md)
- [<span data-ttu-id="6f400-126">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="6f400-126">Development Guide</span></span>](./development-guide.md)
- [<span data-ttu-id="6f400-127">Приложения служб Windows</span><span class="sxs-lookup"><span data-stu-id="6f400-127">Windows Service Applications</span></span>](./windows-services/index.md)

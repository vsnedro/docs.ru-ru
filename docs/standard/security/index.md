---
title: Безопасность в .NET
description: Сведения о безопасности в .NET. Используйте ссылки, описывающие основные понятия безопасности, безопасность на основе ролей, модель шифрования и рекомендации по безопасному кодированию.
ms.date: 06/04/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, security
- security [.NET], about security
- application development [.NET], security
- security [.NET Framework]
- security [.NET]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
ms.openlocfilehash: 21511b580a4f922d2aef04cc79f5d551f0406b45
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767823"
---
# <a name="security-in-net"></a><span data-ttu-id="62363-104">Безопасность в .NET</span><span class="sxs-lookup"><span data-stu-id="62363-104">Security in .NET</span></span>

<span data-ttu-id="62363-105">Среда CLR и .NET предоставляют множество полезных классов и служб, которые позволяют разработчикам легко писать безопасный код и предоставлять системным администраторам возможность настраивать разрешения, предоставленные коду, чтобы он мог получить доступ к защищенным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="62363-105">The common language runtime and the .NET provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="62363-106">Кроме того, среда выполнения и .NET предоставляют полезные классы и службы, которые упрощают использование криптографии и безопасности на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="62363-106">In addition, the runtime and the .NET provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="62363-107">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="62363-107">In this section</span></span>

- [<span data-ttu-id="62363-108">Основные понятия безопасности</span><span class="sxs-lookup"><span data-stu-id="62363-108">Key Security Concepts</span></span>](key-security-concepts.md)  
<span data-ttu-id="62363-109">Обзор функций безопасности среды CLR.</span><span class="sxs-lookup"><span data-stu-id="62363-109">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="62363-110">Этот раздел представляет интерес для разработчиков и системных администраторов.</span><span class="sxs-lookup"><span data-stu-id="62363-110">This section is of interest to developers and system administrators.</span></span>

- [<span data-ttu-id="62363-111">Безопасность на основе ролей</span><span class="sxs-lookup"><span data-stu-id="62363-111">Role-Based Security</span></span>](role-based-security.md)  
<span data-ttu-id="62363-112">Описывается взаимодействие кода с системой безопасности на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="62363-112">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="62363-113">Этот раздел представляет интерес для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="62363-113">This section is of interest to developers.</span></span>

- [<span data-ttu-id="62363-114">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="62363-114">Cryptography Model</span></span>](cryptography-model.md)  
<span data-ttu-id="62363-115">Содержит общие сведения о службах шифрования, предоставляемых .NET.</span><span class="sxs-lookup"><span data-stu-id="62363-115">Provides an overview of cryptographic services provided by .NET.</span></span> <span data-ttu-id="62363-116">Этот раздел представляет интерес для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="62363-116">This section is of interest to developers.</span></span>

- [<span data-ttu-id="62363-117">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="62363-117">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)  
<span data-ttu-id="62363-118">Описывает некоторые рекомендации по созданию надежных приложений .NET.</span><span class="sxs-lookup"><span data-stu-id="62363-118">Describes some of the best practices for creating reliable .NET applications.</span></span> <span data-ttu-id="62363-119">Этот раздел представляет интерес для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="62363-119">This section is of interest to developers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="62363-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="62363-120">Related sections</span></span>

[<span data-ttu-id="62363-121">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="62363-121">Development Guide</span></span>](../../framework/development-guide.md)  
<span data-ttu-id="62363-122">Здесь содержится руководство по всем ключевым технологическим областям и задачам для разработки приложений, включая создание, настройку, отладку, безопасность и развертывание приложений, а также сведения о динамическом программировании, взаимодействии, расширении среды, управлении памятью и работе с потоками.</span><span class="sxs-lookup"><span data-stu-id="62363-122">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

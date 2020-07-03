---
title: Многофайловые сборки
description: Многофайловые сборки можно создавать с помощью компиляторов командной строки или Visual Studio, используя инструменты Visual C++. Один из файлов сборки обязательно должен содержать ее манифест.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
ms.openlocfilehash: a5fb41b3b136a325e6b8658da521cba3176e929f
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104642"
---
# <a name="multifile-assemblies"></a><span data-ttu-id="fb83f-104">Многофайловые сборки</span><span class="sxs-lookup"><span data-stu-id="fb83f-104">Multifile assemblies</span></span>

<span data-ttu-id="fb83f-105">Многофайловые сборки, ориентированные на .NET Framework, можно создавать с помощью компиляторов командной строки или в Visual Studio, используя Visual C++.</span><span class="sxs-lookup"><span data-stu-id="fb83f-105">You can create multifile assemblies that target the .NET Framework using command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="fb83f-106">Один из файлов сборки обязательно должен содержать ее манифест.</span><span class="sxs-lookup"><span data-stu-id="fb83f-106">One file in the assembly must contain the assembly manifest.</span></span> <span data-ttu-id="fb83f-107">Кроме того, сборка, запускающая приложение, должна содержать точку входа, такую как метод `Main` или `WinMain`.</span><span class="sxs-lookup"><span data-stu-id="fb83f-107">An assembly that starts an application must also contain an entry point, such as a `Main` or `WinMain` method.</span></span>

<span data-ttu-id="fb83f-108">Например, предположим, что есть приложение, содержащее два модуля кода — *Client.cs* и *Stringer.cs*.</span><span class="sxs-lookup"><span data-stu-id="fb83f-108">For example, suppose you have an application that contains two code modules, *Client.cs* and *Stringer.cs*.</span></span> <span data-ttu-id="fb83f-109">Модуль *Stringer.cs* создает пространство имен `myStringer`, на которое ссылается код в модуле *Client.cs*.</span><span class="sxs-lookup"><span data-stu-id="fb83f-109">*Stringer.cs* creates the `myStringer` namespace that is referenced by the code in *Client.cs*.</span></span> <span data-ttu-id="fb83f-110">Модуль *Client.cs* содержит метод `Main`, который является точкой входа приложения.</span><span class="sxs-lookup"><span data-stu-id="fb83f-110">*Client.cs* contains the `Main` method, which is the application's entry point.</span></span> <span data-ttu-id="fb83f-111">В этом примере выполняется компиляция двух модулей кода, затем создается третий файл, содержащий манифест сборки, который и запускает приложение.</span><span class="sxs-lookup"><span data-stu-id="fb83f-111">In this example, you compile the two code modules, and then create a third file that contains the assembly manifest, which launches the application.</span></span> <span data-ttu-id="fb83f-112">Манифест сборки ссылается и на оба модуля — *Client* и *Stringer*.</span><span class="sxs-lookup"><span data-stu-id="fb83f-112">The assembly manifest references both the *Client* and *Stringer* modules.</span></span>

> [!NOTE]
> <span data-ttu-id="fb83f-113">Многофайловые сборки могут иметь только одну точку входа, даже если сборка содержит несколько модулей кода.</span><span class="sxs-lookup"><span data-stu-id="fb83f-113">Multifile assemblies can have only one entry point, even if the assembly has multiple code modules.</span></span>

<span data-ttu-id="fb83f-114">Существует несколько причин, по которым может понадобиться создать многофайловую сборку.</span><span class="sxs-lookup"><span data-stu-id="fb83f-114">There are several reasons you might want to create a multifile assembly:</span></span>

- <span data-ttu-id="fb83f-115">Для объединения модулей, написанных на различных языках.</span><span class="sxs-lookup"><span data-stu-id="fb83f-115">To combine modules written in different languages.</span></span> <span data-ttu-id="fb83f-116">Это наиболее частая причина создания многофайловой сборки.</span><span class="sxs-lookup"><span data-stu-id="fb83f-116">This is the most common reason for creating a multifile assembly.</span></span>

- <span data-ttu-id="fb83f-117">Для оптимизации загрузки приложения путем выделения редко используемых типов в модуль, загружаемый только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="fb83f-117">To optimize downloading an application by putting seldom-used types in a module that is downloaded only when needed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fb83f-118">При создании приложений, загружаемых в браузере Microsoft Internet Explorer с помощью тега `<object>`, важно создавать именно многофайловые сборки.</span><span class="sxs-lookup"><span data-stu-id="fb83f-118">If you are creating applications that will be downloaded using the `<object>` tag with Microsoft Internet Explorer, it is important that you create multifile assemblies.</span></span> <span data-ttu-id="fb83f-119">Согласно этому сценарию создается отдельный от модулей кода файл, который содержит только манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="fb83f-119">In this scenario, you create a file separate from your code modules that contains only the assembly manifest.</span></span> <span data-ttu-id="fb83f-120">Обозреватель Internet Explorer в первую очередь загружает манифест, а затем создает рабочие потоки для загрузки любых требуемых дополнительных модулей или сборок.</span><span class="sxs-lookup"><span data-stu-id="fb83f-120">Internet Explorer downloads the assembly manifest first, and then creates worker threads to download any additional modules or assemblies required.</span></span> <span data-ttu-id="fb83f-121">При загрузке файла, содержащего манифест сборки, обозреватель Internet Explorer не реагирует на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="fb83f-121">While the file containing the assembly manifest is being downloaded, Internet Explorer will be unresponsive to user input.</span></span> <span data-ttu-id="fb83f-122">Чем меньше размер файла, содержащего манифест сборки, тем меньше времени обозреватель Internet Explorer будет оставаться в таком состоянии.</span><span class="sxs-lookup"><span data-stu-id="fb83f-122">The smaller the file containing the assembly manifest, the less time Internet Explorer will be unresponsive.</span></span>

- <span data-ttu-id="fb83f-123">Для объединения модулей кода, созданных несколькими разработчиками.</span><span class="sxs-lookup"><span data-stu-id="fb83f-123">To combine code modules written by several developers.</span></span> <span data-ttu-id="fb83f-124">Несмотря на то что каждый разработчик может скомпилировать модуль кода в сборку, это может привести к принудительному экспорту некоторых типов, которые бы не экспортировались, если бы все модули были помещены в многофайловую сборку.</span><span class="sxs-lookup"><span data-stu-id="fb83f-124">Although each developer can compile each code module into an assembly, this can force some types to be exposed publicly that are not exposed if all modules are put into a multifile assembly.</span></span>

<span data-ttu-id="fb83f-125">Сразу же после создания сборки можно подписать файл, содержащий манифест сборки (и, следовательно, подписать саму сборку), или же задать для файла (и для сборки) строгое имя и поместить его в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="fb83f-125">Once you create the assembly, you can sign the file that contains the assembly manifest, and hence the assembly, or you can give the file and the assembly a strong name and put it in the global assembly cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb83f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fb83f-126">See also</span></span>

- [<span data-ttu-id="fb83f-127">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="fb83f-127">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="fb83f-128">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="fb83f-128">Program with assemblies</span></span>](../../standard/assembly/index.md)

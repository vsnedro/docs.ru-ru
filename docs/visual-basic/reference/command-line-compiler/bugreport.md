---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 02d84bceb0242988c70889ddd5d3dc7530f6e808
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793549"
---
# <a name="-bugreport"></a><span data-ttu-id="654d5-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="654d5-102">-bugreport</span></span>

<span data-ttu-id="654d5-103">Создает файл, который можно использовать при создании отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="654d5-103">Creates a file that you can use when you file a bug report.</span></span>

## <a name="syntax"></a><span data-ttu-id="654d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="654d5-104">Syntax</span></span>

```console
-bugreport:file
```

## <a name="arguments"></a><span data-ttu-id="654d5-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="654d5-105">Arguments</span></span>

|<span data-ttu-id="654d5-106">Термин</span><span class="sxs-lookup"><span data-stu-id="654d5-106">Term</span></span>|<span data-ttu-id="654d5-107">Определение</span><span class="sxs-lookup"><span data-stu-id="654d5-107">Definition</span></span>|
|---|---|
|`file`|<span data-ttu-id="654d5-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="654d5-108">Required.</span></span> <span data-ttu-id="654d5-109">Имя файла, который будет содержать отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="654d5-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="654d5-110">Если имя файла содержит пробел, заключите это имя в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="654d5-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|

## <a name="remarks"></a><span data-ttu-id="654d5-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="654d5-111">Remarks</span></span>

<span data-ttu-id="654d5-112">В `file` добавляются следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="654d5-112">The following information is added to `file`:</span></span>

- <span data-ttu-id="654d5-113">Копия всех файлов исходного кода, включенных в компиляцию.</span><span class="sxs-lookup"><span data-stu-id="654d5-113">A copy of all source-code files in the compilation.</span></span>

- <span data-ttu-id="654d5-114">Список параметров компилятора, используемых при компиляции.</span><span class="sxs-lookup"><span data-stu-id="654d5-114">A list of the compiler options used in the compilation.</span></span>

- <span data-ttu-id="654d5-115">Сведения о версии компилятора, среды CLR и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="654d5-115">Version information about your compiler, common language runtime, and operating system.</span></span>

- <span data-ttu-id="654d5-116">Выходные данные компилятора (если есть).</span><span class="sxs-lookup"><span data-stu-id="654d5-116">Compiler output, if any.</span></span>

- <span data-ttu-id="654d5-117">Описание проблемы, которое нужно предоставить.</span><span class="sxs-lookup"><span data-stu-id="654d5-117">A description of the problem, for which you are prompted.</span></span>

- <span data-ttu-id="654d5-118">Описание предполагаемого способа решения проблемы, которое нужно предоставить.</span><span class="sxs-lookup"><span data-stu-id="654d5-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>

<span data-ttu-id="654d5-119">Так как в `file` будут помещены копии всех файлов исходного кода, вам, возможно, потребуется воспроизвести предполагаемую ошибку в коде с использованием максимально короткой программы.</span><span class="sxs-lookup"><span data-stu-id="654d5-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="654d5-120">Параметр `-bugreport` позволяет создать файл, который может содержать конфиденциальную информацию.</span><span class="sxs-lookup"><span data-stu-id="654d5-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="654d5-121">К такой информации относится текущее время, версия компилятора, версия .NET Framework, версия ОС, имя пользователя, аргументы командной строки, с которыми был запущен компилятор, весь исходный код и двоичное представление любой базовой сборки.</span><span class="sxs-lookup"><span data-stu-id="654d5-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="654d5-122">Доступ к этому параметру можно получить, указав параметры командной строки в файле Web.config для компиляции приложения ASP.NET на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="654d5-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="654d5-123">Чтобы избежать этого, измените файл Machine.config, чтобы запретить пользователям выполнять компиляцию на сервере.</span><span class="sxs-lookup"><span data-stu-id="654d5-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>

<span data-ttu-id="654d5-124">Если этот параметр используется с `-errorreport:prompt`, `-errorreport:queue` или `-errorreport:send`, а в приложении возникает внутренняя ошибка компилятора, информация из `file` отправляется в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="654d5-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="654d5-125">Эта информация поможет инженерам Майкрософт определить причину ошибки и улучшить следующий выпуск Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="654d5-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="654d5-126">По умолчанию информация не отправляется в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="654d5-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="654d5-127">Но при компиляции приложения с использованием `-errorreport:queue` по умолчанию приложение собирает отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="654d5-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="654d5-128">Затем, когда администратор компьютера входит в систему, система сбора информации об ошибках отобразит всплывающее окно. С его помощью администратор может отправлять в корпорацию Майкрософт любые отчеты об ошибках, возникших с момента входа в систему.</span><span class="sxs-lookup"><span data-stu-id="654d5-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>

> [!NOTE]
> <span data-ttu-id="654d5-129">Параметр `-bugreport` не доступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="654d5-129">The `-bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="654d5-130">Пример</span><span class="sxs-lookup"><span data-stu-id="654d5-130">Example</span></span>

<span data-ttu-id="654d5-131">В следующем примере выполняется компиляция *T2.vb*. При этом все сведения об ошибках помещаются в файл *Problem.txt*.</span><span class="sxs-lookup"><span data-stu-id="654d5-131">The following example compiles *T2.vb* and puts all bug-reporting information in the file *Problem.txt*.</span></span>

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="654d5-132">См. также</span><span class="sxs-lookup"><span data-stu-id="654d5-132">See also</span></span>

- [<span data-ttu-id="654d5-133">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="654d5-133">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="654d5-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="654d5-134">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="654d5-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="654d5-135">-errorreport</span></span>](errorreport.md)
- [<span data-ttu-id="654d5-136">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="654d5-136">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="654d5-137">[Элемент trustLevel для элемента securityPolicy (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="654d5-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>

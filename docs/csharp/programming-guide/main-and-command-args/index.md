---
title: Руководство по программированию на C#. Main() и аргументы командной строки
description: Сведения о методе Main() и аргументах командной строки. Метод Main является точкой входа для исполняемой программы.
ms.date: 08/02/2017
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 95ec9d3dfebe4721d4b1822939f925aa37b9e9c4
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382078"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="5f70b-104">Main() и аргументы командной строки (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5f70b-104">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="5f70b-105">Метод `Main` — это точка входа приложения C#.</span><span class="sxs-lookup"><span data-stu-id="5f70b-105">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="5f70b-106">(Библиотекам и службам точка входа в виде метода `Main` не требуется.) Когда приложение запускается, первым вызывается именно метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="5f70b-106">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

<span data-ttu-id="5f70b-107">В программе на C# может существовать только одна точка входа.</span><span class="sxs-lookup"><span data-stu-id="5f70b-107">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="5f70b-108">Если у вас есть несколько классов с методом `Main`, программу нужно компилировать с параметром `-main`, чтобы указать, какой из методов `Main` будет использоваться в качестве точки входа.</span><span class="sxs-lookup"><span data-stu-id="5f70b-108">If you have more than one class that has a `Main` method, you must compile your program with the `-main` compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="5f70b-109">Дополнительные сведения см. в разделе [-main (параметры компилятора C#)](../../language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5f70b-109">For more information, see [-main (C# Compiler Options)](../../language-reference/compiler-options/main-compiler-option.md).</span></span>

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a><span data-ttu-id="5f70b-110">Обзор</span><span class="sxs-lookup"><span data-stu-id="5f70b-110">Overview</span></span>

- <span data-ttu-id="5f70b-111">Метод `Main` — это точка входа для выполняемой программы. Это начальный и завершающий этапы управления программой.</span><span class="sxs-lookup"><span data-stu-id="5f70b-111">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="5f70b-112">`Main` объявляется внутри класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="5f70b-112">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="5f70b-113">Метод `Main` должен быть [статическим](../../language-reference/keywords/static.md). Он может не быть [открытым](../../language-reference/keywords/public.md).</span><span class="sxs-lookup"><span data-stu-id="5f70b-113">`Main` must be [static](../../language-reference/keywords/static.md) and it need not be [public](../../language-reference/keywords/public.md).</span></span> <span data-ttu-id="5f70b-114">(В предыдущем примере он по умолчанию получает уровень доступа [private](../../language-reference/keywords/private.md) (закрытый).) Класс или структура, в которой он объявлен, не обязаны быть статическими.</span><span class="sxs-lookup"><span data-stu-id="5f70b-114">(In the earlier example, it receives the default access of [private](../../language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="5f70b-115">Метод `Main` может иметь значение `void`, `int` или (начиная с C# 7.1) `Task`, а также тип возвращаемого значения `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="5f70b-115">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="5f70b-116">Если только `Main` возвращает `Task` или `Task<int>`, объявление `Main` может включать модификатор [`async`](../../language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="5f70b-116">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="5f70b-117">Обратите внимание, что это, в частности, исключает метод `async void Main`.</span><span class="sxs-lookup"><span data-stu-id="5f70b-117">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="5f70b-118">Метод `Main` может быть объявлен с параметром `string[]`, который содержит аргументы командной строки, или без него.</span><span class="sxs-lookup"><span data-stu-id="5f70b-118">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="5f70b-119">Когда вы используете Visual Studio для создания Windows-приложений, вы можете добавить параметр вручную либо воспользоваться методом <xref:System.Environment.GetCommandLineArgs>, чтобы получить [аргументы командной строки](command-line-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="5f70b-119">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment.GetCommandLineArgs> method to obtain the [command-line arguments](command-line-arguments.md).</span></span> <span data-ttu-id="5f70b-120">Параметры считываются как аргументы командной строки, индексы которых начинаются с нуля.</span><span class="sxs-lookup"><span data-stu-id="5f70b-120">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="5f70b-121">В отличие от C и C++, имя программы не рассматривается как первый аргумент командной строки в массиве `args`, но является первым элементом метода <xref:System.Environment.GetCommandLineArgs>.</span><span class="sxs-lookup"><span data-stu-id="5f70b-121">Unlike C and C++, the name of the program is not treated as the first command-line argument in the `args` array, but it is the first element of the <xref:System.Environment.GetCommandLineArgs> method.</span></span>

<span data-ttu-id="5f70b-122">Ниже приведен список допустимых подписей `Main`:</span><span class="sxs-lookup"><span data-stu-id="5f70b-122">The following is a list of valid `Main` signatures:</span></span>

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

<span data-ttu-id="5f70b-123">В предыдущих примерах используется модификатор открытого метода доступа.</span><span class="sxs-lookup"><span data-stu-id="5f70b-123">The preceding examples all use the public accessor modifier.</span></span> <span data-ttu-id="5f70b-124">Эта обычная схема использования, но она не является обязательной.</span><span class="sxs-lookup"><span data-stu-id="5f70b-124">That is typical, but not required.</span></span>

<span data-ttu-id="5f70b-125">Добавление значений `async` и `Task`, а также типов возвращаемого значения `Task<int>` упрощает код программы, когда консольным приложениям требуется запустить и ожидать (`await`) асинхронные операции в `Main`.</span><span class="sxs-lookup"><span data-stu-id="5f70b-125">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5f70b-126">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5f70b-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5f70b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="5f70b-127">See also</span></span>

- [<span data-ttu-id="5f70b-128">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="5f70b-128">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="5f70b-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5f70b-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5f70b-130">Методы</span><span class="sxs-lookup"><span data-stu-id="5f70b-130">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="5f70b-131">Структура программы C#</span><span class="sxs-lookup"><span data-stu-id="5f70b-131">Inside a C# Program</span></span>](../inside-a-program/index.md)

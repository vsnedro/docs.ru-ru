---
title: Использование исключений стандартных типов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: b8e05f22a66fabeab28cc83a074471df29aae218
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291361"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="cc663-102">Использование исключений стандартных типов</span><span class="sxs-lookup"><span data-stu-id="cc663-102">Using Standard Exception Types</span></span>
<span data-ttu-id="cc663-103">В этом разделе описаны стандартные исключения, предоставляемые платформой, и сведения об их использовании.</span><span class="sxs-lookup"><span data-stu-id="cc663-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="cc663-104">Список не является исчерпывающим.</span><span class="sxs-lookup"><span data-stu-id="cc663-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="cc663-105">Сведения об использовании других типов исключений платформы см. в справочной документации по .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cc663-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>

## <a name="exception-and-systemexception"></a><span data-ttu-id="cc663-106">Exception и SystemException</span><span class="sxs-lookup"><span data-stu-id="cc663-106">Exception and SystemException</span></span>
 <span data-ttu-id="cc663-107">❌НЕ вызывайте <xref:System.Exception?displayProperty=nameWithType> или <xref:System.SystemException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="cc663-107">❌ DO NOT throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="cc663-108">❌НЕ перехватывайте `System.Exception` или `System.SystemException` в коде платформы, если только не планируется повторный вызов.</span><span class="sxs-lookup"><span data-stu-id="cc663-108">❌ DO NOT catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>

 <span data-ttu-id="cc663-109">❌Избегайте перехвата `System.Exception` или `System.SystemException` , за исключением обработчиков исключений верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="cc663-109">❌ AVOID catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>

## <a name="applicationexception"></a><span data-ttu-id="cc663-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="cc663-110">ApplicationException</span></span>
 <span data-ttu-id="cc663-111">❌НЕ вызывайте или не наследует от <xref:System.ApplicationException> .</span><span class="sxs-lookup"><span data-stu-id="cc663-111">❌ DO NOT throw or derive from <xref:System.ApplicationException>.</span></span>

## <a name="invalidoperationexception"></a><span data-ttu-id="cc663-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="cc663-112">InvalidOperationException</span></span>
 <span data-ttu-id="cc663-113">✔️ выдавать исключение, <xref:System.InvalidOperationException> Если объект находится в недопустимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="cc663-113">✔️ DO throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="cc663-114">ArgumentException, ArgumentNullException и ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="cc663-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>
 <span data-ttu-id="cc663-115">✔️ выдавать исключение <xref:System.ArgumentException> или один из его подтипов, если члену переданы неверные аргументы.</span><span class="sxs-lookup"><span data-stu-id="cc663-115">✔️ DO throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="cc663-116">Предпочитать наиболее производный тип исключения, если применимо.</span><span class="sxs-lookup"><span data-stu-id="cc663-116">Prefer the most derived exception type, if applicable.</span></span>

 <span data-ttu-id="cc663-117">✔️ задать `ParamName` свойство при вызове одного из подклассов `ArgumentException` .</span><span class="sxs-lookup"><span data-stu-id="cc663-117">✔️ DO set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>

 <span data-ttu-id="cc663-118">Это свойство представляет имя параметра, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="cc663-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="cc663-119">Обратите внимание, что свойство можно задать с помощью одной из перегрузок конструктора.</span><span class="sxs-lookup"><span data-stu-id="cc663-119">Note that the property can be set using one of the constructor overloads.</span></span>

 <span data-ttu-id="cc663-120">✔️ использовать `value` для имени параметра неявного значения для методов задания свойств.</span><span class="sxs-lookup"><span data-stu-id="cc663-120">✔️ DO use `value` for the name of the implicit value parameter of property setters.</span></span>

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="cc663-121">NullReferenceException, IndexOutOfRangeException и AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="cc663-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>
 <span data-ttu-id="cc663-122">❌НЕ разрешайте общедоступные API-интерфейсы для явного или неявного вызова <xref:System.NullReferenceException> , <xref:System.AccessViolationException> или <xref:System.IndexOutOfRangeException> .</span><span class="sxs-lookup"><span data-stu-id="cc663-122">❌ DO NOT allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="cc663-123">Эти исключения зарезервированы и создаются подсистемой выполнения и в большинстве случаев указывают на ошибку.</span><span class="sxs-lookup"><span data-stu-id="cc663-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>

 <span data-ttu-id="cc663-124">Проследите за проверкой аргументов, чтобы избежать возникновения этих исключений.</span><span class="sxs-lookup"><span data-stu-id="cc663-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="cc663-125">Создание этих исключений предоставляет сведения о реализации метода, которые могут меняться со временем.</span><span class="sxs-lookup"><span data-stu-id="cc663-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>

## <a name="stackoverflowexception"></a><span data-ttu-id="cc663-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="cc663-126">StackOverflowException</span></span>
 <span data-ttu-id="cc663-127">❌Не вызывайте явно <xref:System.StackOverflowException> .</span><span class="sxs-lookup"><span data-stu-id="cc663-127">❌ DO NOT explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="cc663-128">Исключение должно быть явно вызвано только средой CLR.</span><span class="sxs-lookup"><span data-stu-id="cc663-128">The exception should be explicitly thrown only by the CLR.</span></span>

 <span data-ttu-id="cc663-129">❌НЕ перехватывайте `StackOverflowException` .</span><span class="sxs-lookup"><span data-stu-id="cc663-129">❌ DO NOT catch `StackOverflowException`.</span></span>

 <span data-ttu-id="cc663-130">Практически невозможно написать управляемый код, который остается единообразным при наличии произвольных переходящих стеков стека.</span><span class="sxs-lookup"><span data-stu-id="cc663-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="cc663-131">Неуправляемые части среды CLR остаются неизменными с помощью зондов для перемещения передатчиков стека в четко определенные места, а не при резервном копировании из произвольных передатчиков стека.</span><span class="sxs-lookup"><span data-stu-id="cc663-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>

## <a name="outofmemoryexception"></a><span data-ttu-id="cc663-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="cc663-132">OutOfMemoryException</span></span>
 <span data-ttu-id="cc663-133">❌Не вызывайте явно <xref:System.OutOfMemoryException> .</span><span class="sxs-lookup"><span data-stu-id="cc663-133">❌ DO NOT explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="cc663-134">Это исключение возникает только в инфраструктуре среды CLR.</span><span class="sxs-lookup"><span data-stu-id="cc663-134">This exception is to be thrown only by the CLR infrastructure.</span></span>

## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="cc663-135">ComException, SEHException и ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="cc663-135">ComException, SEHException, and ExecutionEngineException</span></span>
 <span data-ttu-id="cc663-136">❌НЕ вызывайте явно <xref:System.Runtime.InteropServices.COMException> , <xref:System.ExecutionEngineException> и <xref:System.Runtime.InteropServices.SEHException> .</span><span class="sxs-lookup"><span data-stu-id="cc663-136">❌ DO NOT explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="cc663-137">Эти исключения должны вызываться только инфраструктурой CLR.</span><span class="sxs-lookup"><span data-stu-id="cc663-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>

 <span data-ttu-id="cc663-138">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="cc663-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="cc663-139">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="cc663-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="cc663-140">См. также</span><span class="sxs-lookup"><span data-stu-id="cc663-140">See also</span></span>

- [<span data-ttu-id="cc663-141">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="cc663-141">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="cc663-142">Правила разработки исключений</span><span class="sxs-lookup"><span data-stu-id="cc663-142">Design Guidelines for Exceptions</span></span>](exceptions.md)

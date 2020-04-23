---
title: 'Зарезервированные атрибуты C#: отслеживание сведений о вызывающем объекте'
ms.date: 04/09/2020
description: Эти атрибуты указывают компилятору создавать сведения о коде, который вызывает член. Для предоставления подробных сведений об отслеживании используются аргументы CallerFilePath, CallerLineNumber и CallerMemberName.
ms.openlocfilehash: ee061d4cae35bdcc0b89007e360e94fee8c5f87c
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389826"
---
# <a name="reserved-attributes-determine-caller-information"></a><span data-ttu-id="1aafc-104">Зарезервированные атрибуты: определение сведений о вызывающем объекте</span><span class="sxs-lookup"><span data-stu-id="1aafc-104">Reserved attributes: Determine caller information</span></span>

<span data-ttu-id="1aafc-105">С помощью информационных атрибутов можно получить сведения о вызывающем объекте метода.</span><span class="sxs-lookup"><span data-stu-id="1aafc-105">Using info attributes, you obtain information about the caller to a method.</span></span> <span data-ttu-id="1aafc-106">Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя члена вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="1aafc-106">You obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="1aafc-107">Для получения этих сведений используются атрибуты, которые применяются к необязательным параметрам.</span><span class="sxs-lookup"><span data-stu-id="1aafc-107">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="1aafc-108">Каждый необязательный параметр задает значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1aafc-108">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="1aafc-109">В следующей таблице перечислены информационные атрибуты вызывающего объекта, которые определены в пространстве имен <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1aafc-109">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="1aafc-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1aafc-110">Attribute</span></span>|<span data-ttu-id="1aafc-111">Описание</span><span class="sxs-lookup"><span data-stu-id="1aafc-111">Description</span></span>|<span data-ttu-id="1aafc-112">Type</span><span class="sxs-lookup"><span data-stu-id="1aafc-112">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="1aafc-113">Полный путь исходного файла, содержащего вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="1aafc-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="1aafc-114">Это путь во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="1aafc-114">The full path is the path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="1aafc-115">Номер строки в исходном файле, из которого вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="1aafc-115">Line number in the source file from which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="1aafc-116">Имя свойства или метода вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="1aafc-116">Method name or property name of the caller.</span></span>|`String`|

<span data-ttu-id="1aafc-117">Эти сведения полезны для трассировки, отладки и создания средств диагностики.</span><span class="sxs-lookup"><span data-stu-id="1aafc-117">This information helps you write tracing, debugging, and create diagnostic tools.</span></span> <span data-ttu-id="1aafc-118">В следующем примере показано, как использовать информационные атрибуты вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="1aafc-118">The following example shows how to use caller info attributes.</span></span> <span data-ttu-id="1aafc-119">При каждом вызове метода `TraceMessage` сведения о вызывающем объекте подставляются в качестве аргументов необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="1aafc-119">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>

```csharp
public void DoProcessing()
{
    TraceMessage("Something happened.");
}

public void TraceMessage(string message,
        [CallerMemberName] string memberName = "",
        [CallerFilePath] string sourceFilePath = "",
        [CallerLineNumber] int sourceLineNumber = 0)
{
    Trace.WriteLine("message: " + message);
    Trace.WriteLine("member name: " + memberName);
    Trace.WriteLine("source file path: " + sourceFilePath);
    Trace.WriteLine("source line number: " + sourceLineNumber);
}

// Sample Output:
//  message: Something happened.
//  member name: DoProcessing
//  source file path: c:\Visual Studio Projects\CallerInfoCS\CallerInfoCS\Form1.cs
//  source line number: 31
```

<span data-ttu-id="1aafc-120">Для каждого необязательного параметра указывается явное значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1aafc-120">You specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="1aafc-121">Нельзя применять информационные атрибуты вызывающего объекта к параметрам, которые не были указаны как необязательные.</span><span class="sxs-lookup"><span data-stu-id="1aafc-121">You can't apply caller info attributes to parameters that aren't specified as optional.</span></span> <span data-ttu-id="1aafc-122">Информационные атрибуты вызывающего объекта не делают параметр необязательным.</span><span class="sxs-lookup"><span data-stu-id="1aafc-122">The caller info attributes don't make a parameter optional.</span></span> <span data-ttu-id="1aafc-123">Вместо этого они влияют на значение по умолчанию, которое передается, если аргумент был опущен.</span><span class="sxs-lookup"><span data-stu-id="1aafc-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span> <span data-ttu-id="1aafc-124">Информационные значения вызывающего объекта передаются как литералы в IL во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="1aafc-124">Caller info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="1aafc-125">В отличие от результатов свойства <xref:System.Exception.StackTrace%2A> для исключений, результаты не затрагиваются запутыванием кода.</span><span class="sxs-lookup"><span data-stu-id="1aafc-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span> <span data-ttu-id="1aafc-126">Можно явно передать необязательные аргументы, чтобы управлять сведениями о вызывающем объекте или скрывать сведения о вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="1aafc-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

### <a name="member-names"></a><span data-ttu-id="1aafc-127">Имена членов</span><span class="sxs-lookup"><span data-stu-id="1aafc-127">Member names</span></span>

<span data-ttu-id="1aafc-128">Можно использовать атрибут `CallerMemberName`, чтобы не указывать имя члена в виде аргумента `String` вызываемому методу.</span><span class="sxs-lookup"><span data-stu-id="1aafc-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="1aafc-129">Этот прием позволяет избежать проблемы, заключающейся в том, что **операция рефакторинга и переименования** не изменяет значений `String`.</span><span class="sxs-lookup"><span data-stu-id="1aafc-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="1aafc-130">Это особенно полезно при выполнении следующих задач:</span><span class="sxs-lookup"><span data-stu-id="1aafc-130">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="1aafc-131">Использование процедур трассировки и диагностики.</span><span class="sxs-lookup"><span data-stu-id="1aafc-131">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="1aafc-132">Реализация интерфейса <xref:System.ComponentModel.INotifyPropertyChanged> при привязке данных.</span><span class="sxs-lookup"><span data-stu-id="1aafc-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="1aafc-133">Этот интерфейс позволяет свойству объекта уведомлять связанный элемент управления об изменении свойства, чтобы элемент управления мог отображать обновленные сведения.</span><span class="sxs-lookup"><span data-stu-id="1aafc-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="1aafc-134">Если атрибут `CallerMemberName` не используется, необходимо указать имя свойства как литерал.</span><span class="sxs-lookup"><span data-stu-id="1aafc-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="1aafc-135">В следующей таблице представлены имена членов, возвращаемых при использовании атрибута `CallerMemberName`.</span><span class="sxs-lookup"><span data-stu-id="1aafc-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>

|<span data-ttu-id="1aafc-136">Фрагмент кода, в пределах которого происходят вызовы</span><span class="sxs-lookup"><span data-stu-id="1aafc-136">Calls occur within</span></span>|<span data-ttu-id="1aafc-137">Результат имени члена</span><span class="sxs-lookup"><span data-stu-id="1aafc-137">Member name result</span></span>|
|-|-|
|<span data-ttu-id="1aafc-138">Метод, свойство или событие</span><span class="sxs-lookup"><span data-stu-id="1aafc-138">Method, property, or event</span></span>|<span data-ttu-id="1aafc-139">Имя метода, свойства или события, из которого происходил вызов.</span><span class="sxs-lookup"><span data-stu-id="1aafc-139">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="1aafc-140">Конструктор</span><span class="sxs-lookup"><span data-stu-id="1aafc-140">Constructor</span></span>|<span data-ttu-id="1aafc-141">Строка ".ctor"</span><span class="sxs-lookup"><span data-stu-id="1aafc-141">The string ".ctor"</span></span>|
|<span data-ttu-id="1aafc-142">Статический конструктор</span><span class="sxs-lookup"><span data-stu-id="1aafc-142">Static constructor</span></span>|<span data-ttu-id="1aafc-143">Строка ".cctor"</span><span class="sxs-lookup"><span data-stu-id="1aafc-143">The string ".cctor"</span></span>|
|<span data-ttu-id="1aafc-144">Деструктор</span><span class="sxs-lookup"><span data-stu-id="1aafc-144">Destructor</span></span>|<span data-ttu-id="1aafc-145">Строка "Finalize"</span><span class="sxs-lookup"><span data-stu-id="1aafc-145">The string "Finalize"</span></span>|
|<span data-ttu-id="1aafc-146">Определяемые пользователем операторы и преобразования</span><span class="sxs-lookup"><span data-stu-id="1aafc-146">User-defined operators or conversions</span></span>|<span data-ttu-id="1aafc-147">Созданное имя члена, например, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="1aafc-147">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="1aafc-148">Конструктора атрибута</span><span class="sxs-lookup"><span data-stu-id="1aafc-148">Attribute constructor</span></span>|<span data-ttu-id="1aafc-149">Имя метода или свойства, к которому применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="1aafc-149">The name of the method or property to which the attribute is applied.</span></span> <span data-ttu-id="1aafc-150">Если атрибут — любой элемент внутри члена (например, параметр, возвращаемое значение или параметр универсального типа), то результат — имя члена, который связан с этим элементом.</span><span class="sxs-lookup"><span data-stu-id="1aafc-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="1aafc-151">Нет содержащего члена (например, уровень сборки или атрибуты, примененные к типам)</span><span class="sxs-lookup"><span data-stu-id="1aafc-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="1aafc-152">Значение необязательного параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1aafc-152">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="1aafc-153">См. также</span><span class="sxs-lookup"><span data-stu-id="1aafc-153">See also</span></span>

- [<span data-ttu-id="1aafc-154">Именованные и необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="1aafc-154">Named and Optional Arguments</span></span>](../../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="1aafc-155">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1aafc-155">Attributes</span></span>](../../../standard/attributes/index.md)

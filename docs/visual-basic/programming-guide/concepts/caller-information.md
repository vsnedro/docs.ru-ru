---
title: Сведения о вызывающем
ms.date: 07/20/2015
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
ms.openlocfilehash: 93fb1e327d65ac19f293a2f77b7d5712fc5e8d2f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400672"
---
# <a name="caller-information-visual-basic"></a><span data-ttu-id="e3067-102">Caller Information (Visual Basic) (Сведения о вызывающем (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="e3067-102">Caller Information (Visual Basic)</span></span>
<span data-ttu-id="e3067-103">С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода.</span><span class="sxs-lookup"><span data-stu-id="e3067-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="e3067-104">Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="e3067-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="e3067-105">Эти сведения полезны для трассировки, отладки и создания средств диагностики.</span><span class="sxs-lookup"><span data-stu-id="e3067-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="e3067-106">Для получения этих сведений используются атрибуты, которые применяются к необязательным параметрам, каждый из которых имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e3067-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="e3067-107">В следующей таблице перечислены информационные атрибуты вызывающего объекта, которые определены в пространстве имен <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="e3067-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="e3067-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e3067-108">Attribute</span></span>|<span data-ttu-id="e3067-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e3067-109">Description</span></span>|<span data-ttu-id="e3067-110">Type</span><span class="sxs-lookup"><span data-stu-id="e3067-110">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="e3067-111">Полный путь исходного файла, содержащего вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="e3067-111">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="e3067-112">Это путь к файлу во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="e3067-112">This is the file path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="e3067-113">Номер строки в исходном файле, в которой вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="e3067-113">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="e3067-114">Имя свойства или метода вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="e3067-114">Method or property name of the caller.</span></span> <span data-ttu-id="e3067-115">См. подраздел [Имена членов](#MEMBERNAMES) ниже.</span><span class="sxs-lookup"><span data-stu-id="e3067-115">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="e3067-116">Пример</span><span class="sxs-lookup"><span data-stu-id="e3067-116">Example</span></span>  
 <span data-ttu-id="e3067-117">В следующем примере показано, как использовать информационные атрибуты вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="e3067-117">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="e3067-118">При каждом вызове метода `TraceMessage` сведения о вызывающем объекте подставляются в качестве аргументов необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="e3067-118">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
```vb  
Private Sub DoProcessing()  
    TraceMessage("Something happened.")  
End Sub  
  
Public Sub TraceMessage(message As String,  
        <System.Runtime.CompilerServices.CallerMemberName> Optional memberName As String = Nothing,  
        <System.Runtime.CompilerServices.CallerFilePath> Optional sourcefilePath As String = Nothing,  
        <System.Runtime.CompilerServices.CallerLineNumber()> Optional sourceLineNumber As Integer = 0)  
  
    System.Diagnostics.Trace.WriteLine("message: " & message)  
    System.Diagnostics.Trace.WriteLine("member name: " & memberName)  
    System.Diagnostics.Trace.WriteLine("source file path: " & sourcefilePath)  
    System.Diagnostics.Trace.WriteLine("source line number: " & sourceLineNumber)  
End Sub  
  
' Sample output:  
'   message: Something happened.  
'   member name: DoProcessing  
'   source file path: C:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoVB\CallerInfoVB\Form1.vb  
'   source line number: 15  
```  
  
## <a name="remarks"></a><span data-ttu-id="e3067-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e3067-119">Remarks</span></span>  
 <span data-ttu-id="e3067-120">Для каждого необязательного параметра необходимо указать явное значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e3067-120">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="e3067-121">Нельзя применять информационные атрибуты вызывающего объекта к параметрам, которые не были указаны как необязательные.</span><span class="sxs-lookup"><span data-stu-id="e3067-121">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="e3067-122">Информационные атрибуты вызывающего объекта не делают параметр необязательным.</span><span class="sxs-lookup"><span data-stu-id="e3067-122">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="e3067-123">Вместо этого они влияют на значение по умолчанию, которое передается, если аргумент был опущен.</span><span class="sxs-lookup"><span data-stu-id="e3067-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="e3067-124">Информационные значения вызывающего объекта передаются как литералы в IL во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="e3067-124">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="e3067-125">В отличие от результатов свойства <xref:System.Exception.StackTrace%2A> для исключений, результаты не затрагиваются запутыванием кода.</span><span class="sxs-lookup"><span data-stu-id="e3067-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="e3067-126">Можно явно передать необязательные аргументы, чтобы управлять сведениями о вызывающем объекте или скрывать сведения о вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="e3067-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
### <a name="member-names"></a><a name="MEMBERNAMES"></a><span data-ttu-id="e3067-127">Имена элементов</span><span class="sxs-lookup"><span data-stu-id="e3067-127">Member Names</span></span>  
 <span data-ttu-id="e3067-128">Можно использовать атрибут `CallerMemberName`, чтобы не указывать имя члена в виде аргумента `String` вызываемому методу.</span><span class="sxs-lookup"><span data-stu-id="e3067-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="e3067-129">Этот прием позволяет избежать проблемы, заключающейся в том, что **операция рефакторинга и переименования** не изменяет значений `String`.</span><span class="sxs-lookup"><span data-stu-id="e3067-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="e3067-130">Это особенно полезно при выполнении следующих задач:</span><span class="sxs-lookup"><span data-stu-id="e3067-130">This benefit is especially useful for the following tasks:</span></span>  
  
- <span data-ttu-id="e3067-131">Использование процедур трассировки и диагностики.</span><span class="sxs-lookup"><span data-stu-id="e3067-131">Using tracing and diagnostic routines.</span></span>  
  
- <span data-ttu-id="e3067-132">Реализация интерфейса <xref:System.ComponentModel.INotifyPropertyChanged> при привязке данных.</span><span class="sxs-lookup"><span data-stu-id="e3067-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="e3067-133">Этот интерфейс позволяет свойству объекта уведомлять связанный элемент управления об изменении свойства, чтобы элемент управления мог отображать обновленные сведения.</span><span class="sxs-lookup"><span data-stu-id="e3067-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="e3067-134">Если атрибут `CallerMemberName` не используется, необходимо указать имя свойства как литерал.</span><span class="sxs-lookup"><span data-stu-id="e3067-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="e3067-135">В следующей таблице представлены имена членов, возвращаемых при использовании атрибута `CallerMemberName`.</span><span class="sxs-lookup"><span data-stu-id="e3067-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="e3067-136">Фрагмент кода, в пределах которого происходит вызов</span><span class="sxs-lookup"><span data-stu-id="e3067-136">Calls occurs within</span></span>|<span data-ttu-id="e3067-137">Результат имени члена</span><span class="sxs-lookup"><span data-stu-id="e3067-137">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="e3067-138">Метод, свойство или событие</span><span class="sxs-lookup"><span data-stu-id="e3067-138">Method, property, or event</span></span>|<span data-ttu-id="e3067-139">Имя метода, свойства или события, из которого происходил вызов.</span><span class="sxs-lookup"><span data-stu-id="e3067-139">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="e3067-140">Конструктор</span><span class="sxs-lookup"><span data-stu-id="e3067-140">Constructor</span></span>|<span data-ttu-id="e3067-141">Строка ".ctor"</span><span class="sxs-lookup"><span data-stu-id="e3067-141">The string ".ctor"</span></span>|  
|<span data-ttu-id="e3067-142">Статический конструктор</span><span class="sxs-lookup"><span data-stu-id="e3067-142">Static constructor</span></span>|<span data-ttu-id="e3067-143">Строка ".cctor"</span><span class="sxs-lookup"><span data-stu-id="e3067-143">The string ".cctor"</span></span>|  
|<span data-ttu-id="e3067-144">Деструктор</span><span class="sxs-lookup"><span data-stu-id="e3067-144">Destructor</span></span>|<span data-ttu-id="e3067-145">Строка "Finalize"</span><span class="sxs-lookup"><span data-stu-id="e3067-145">The string "Finalize"</span></span>|  
|<span data-ttu-id="e3067-146">Определяемые пользователем операторы и преобразования</span><span class="sxs-lookup"><span data-stu-id="e3067-146">User-defined operators or conversions</span></span>|<span data-ttu-id="e3067-147">Созданное имя члена, например, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="e3067-147">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="e3067-148">Конструктора атрибута</span><span class="sxs-lookup"><span data-stu-id="e3067-148">Attribute constructor</span></span>|<span data-ttu-id="e3067-149">Имя члена, к которому применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="e3067-149">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="e3067-150">Если атрибут — любой элемент внутри члена (например, параметр, возвращаемое значение или параметр универсального типа), то результат — имя члена, который связан с этим элементом.</span><span class="sxs-lookup"><span data-stu-id="e3067-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="e3067-151">Нет содержащего члена (например, уровень сборки или атрибуты, примененные к типам)</span><span class="sxs-lookup"><span data-stu-id="e3067-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="e3067-152">Значение необязательного параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e3067-152">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3067-153">См. также</span><span class="sxs-lookup"><span data-stu-id="e3067-153">See also</span></span>

- [<span data-ttu-id="e3067-154">Атрибуты (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3067-154">Attributes (Visual Basic)</span></span>](../../language-reference/attributes.md)
- <span data-ttu-id="e3067-155">[Common Attributes (Visual Basic)](attributes/common-attributes.md) (Распространенные атрибуты (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="e3067-155">[Common Attributes (Visual Basic)](attributes/common-attributes.md)</span></span>
- [<span data-ttu-id="e3067-156">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="e3067-156">Optional Parameters</span></span>](../language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="e3067-157">Основные понятия программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3067-157">Programming Concepts (Visual Basic)</span></span>](index.md)

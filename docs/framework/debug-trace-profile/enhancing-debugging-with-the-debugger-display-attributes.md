---
title: Повышение эффективности отладки с помощью атрибутов просмотра отладчика
description: Приступая к работе с атрибутами отображения отладчика в .NET, что позволяет разработчику типа также указывать, как будет выглядеть тип при отображении в отладчике.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- debugger, display attributes
- DebuggerTypeProxyAttribute attribute
- debugging [.NET Framework], debugger display attributes
- DebuggerDisplayAttribute attribute
- display attributes for debugger
- DebuggerBrowsableAttribute attribute
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
ms.openlocfilehash: 2e556358490409a0fa7b345c4454eb43cf607e32
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244370"
---
# <a name="enhancing-debugging-with-the-debugger-display-attributes"></a><span data-ttu-id="7c55e-103">Повышение эффективности отладки с помощью атрибутов просмотра отладчика</span><span class="sxs-lookup"><span data-stu-id="7c55e-103">Enhancing Debugging with the Debugger Display Attributes</span></span>

<span data-ttu-id="7c55e-104">С помощью атрибутов просмотра отладчика разработчик типа может определить параметры отображения типа в отладчике, что позволяет лучше описать его поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7c55e-104">Debugger display attributes allow the developer of the type, who specifies and best understands the runtime behavior of that type, to also specify what that type will look like when it is displayed in a debugger.</span></span> <span data-ttu-id="7c55e-105">Кроме того, пользователи, не знакомые с соответствующим исходным кодом, могут применить на уровне сборки атрибуты просмотра отладчика, предоставляющие свойство `Target`.</span><span class="sxs-lookup"><span data-stu-id="7c55e-105">In addition, debugger display attributes that provide a `Target` property can be applied at the assembly level by users without knowledge of the source code.</span></span> <span data-ttu-id="7c55e-106">Атрибут <xref:System.Diagnostics.DebuggerDisplayAttribute> определяет, как тип или член отображается в окнах переменных отладчика.</span><span class="sxs-lookup"><span data-stu-id="7c55e-106">The <xref:System.Diagnostics.DebuggerDisplayAttribute> attribute controls how a type or member is displayed in the debugger variable windows.</span></span> <span data-ttu-id="7c55e-107">Атрибут <xref:System.Diagnostics.DebuggerBrowsableAttribute> определяет, отображается ли поле или свойство в окнах переменных отладчика, и каким образом это реализуется.</span><span class="sxs-lookup"><span data-stu-id="7c55e-107">The <xref:System.Diagnostics.DebuggerBrowsableAttribute> attribute determines if and how a field or property is displayed in the debugger variable windows.</span></span> <span data-ttu-id="7c55e-108">Атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> указывает прокси (заменяющий тип) для типа и меняет способ отображения типа в окнах отладчика.</span><span class="sxs-lookup"><span data-stu-id="7c55e-108">The <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute specifies a substitute type, or a proxy, for a type and changes the way the type is displayed in debugger windows.</span></span> <span data-ttu-id="7c55e-109">При просмотре переменной, у которой есть прокси (заменяющий тип), прокси заменяет исходный тип в окне просмотра отладчика.</span><span class="sxs-lookup"><span data-stu-id="7c55e-109">When you view a variable that has a proxy, or substitute type, the proxy stands in for the original type in the debugger display window.</span></span> <span data-ttu-id="7c55e-110">Окно переменных отладчика отображает только открытые члены прокси-типа.</span><span class="sxs-lookup"><span data-stu-id="7c55e-110">The debugger variable window displays only the public members of the proxy type.</span></span> <span data-ttu-id="7c55e-111">Закрытые члены не отображаются.</span><span class="sxs-lookup"><span data-stu-id="7c55e-111">Private members are not displayed.</span></span>  
  
## <a name="using-the-debuggerdisplayattribute"></a><span data-ttu-id="7c55e-112">Использование атрибута DebuggerDisplayAttribute</span><span class="sxs-lookup"><span data-stu-id="7c55e-112">Using the DebuggerDisplayAttribute</span></span>  

<span data-ttu-id="7c55e-113">Конструктор <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> имеет один аргумент, определяющий строку, которая должна отображаться в столбце "Значение" для экземпляров типа.</span><span class="sxs-lookup"><span data-stu-id="7c55e-113">The <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> constructor has a single argument: a string to be displayed in the value column for instances of the type.</span></span> <span data-ttu-id="7c55e-114">Эта строка может содержать фигурные скобки ({ и }).</span><span class="sxs-lookup"><span data-stu-id="7c55e-114">This string can contain braces ({ and }).</span></span> <span data-ttu-id="7c55e-115">Текст, заключенный в фигурные скобки, вычисляется как выражение.</span><span class="sxs-lookup"><span data-stu-id="7c55e-115">The text within a pair of braces is evaluated as an expression.</span></span> <span data-ttu-id="7c55e-116">Например, при нажатии на значок плюса (+) для развертывания окна просмотра отладчика для экземпляра `MyHashtable` следующий код C# отображает "Count = 4".</span><span class="sxs-lookup"><span data-stu-id="7c55e-116">For example, the following C# code causes "Count = 4" to be displayed when the plus sign (+) is selected to expand the debugger display for an instance of `MyHashtable`.</span></span>  

```csharp
[DebuggerDisplay("Count = {count}")]
class MyHashtable
{
    public int count = 4;
}
```

<span data-ttu-id="7c55e-117">Атрибуты, применяемые к свойствам, на которые есть ссылки в выражении, не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="7c55e-117">Attributes applied to properties referenced in the expression are not processed.</span></span> <span data-ttu-id="7c55e-118">Компилятор C# поддерживает только общие выражения с неявным доступом к этой ссылке для текущего экземпляра конечного типа.</span><span class="sxs-lookup"><span data-stu-id="7c55e-118">For the C# compiler, a general expression is allowed that has only implicit access to this reference for the current instance of the target type.</span></span> <span data-ttu-id="7c55e-119">Выражение ограничено и не имеет доступа к псевдонимам, локальным переменным или указателям.</span><span class="sxs-lookup"><span data-stu-id="7c55e-119">The expression is limited; there is no access to aliases, locals, or pointers.</span></span> <span data-ttu-id="7c55e-120">В C# можно использовать общее выражение в скобках, которое имеет неявный доступ к указателю `this` только для текущего экземпляра конечного типа.</span><span class="sxs-lookup"><span data-stu-id="7c55e-120">In C# code, you can use a general expression between the braces that has implicit access to the `this` pointer for the current instance of the target type only.</span></span>

<span data-ttu-id="7c55e-121">Например, если в объекте C# имеется переопределенный метод `ToString()`, отладчик будет вызывать переопределенный метод и отображать возвращаемый им результат, а не имя типа `{<typeName>}.`. Таким образом, если метод `ToString()` переопределен, нет необходимости использовать <xref:System.Diagnostics.DebuggerDisplayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7c55e-121">For example, if a C# object has an overridden `ToString()`, the debugger will call the override and show its result instead of the standard `{<typeName>}.` Thus, if you have overridden `ToString()`, you do not need to use <xref:System.Diagnostics.DebuggerDisplayAttribute>.</span></span> <span data-ttu-id="7c55e-122">Если используется и то и другое, то атрибут <xref:System.Diagnostics.DebuggerDisplayAttribute> будет иметь более высокий приоритет по отношению к переопределению `ToString()`.</span><span class="sxs-lookup"><span data-stu-id="7c55e-122">If you use both, the <xref:System.Diagnostics.DebuggerDisplayAttribute> attribute takes precedence over the `ToString()` override.</span></span>

## <a name="using-the-debuggerbrowsableattribute"></a><span data-ttu-id="7c55e-123">Использование атрибута DebuggerBrowsableAttribute</span><span class="sxs-lookup"><span data-stu-id="7c55e-123">Using the DebuggerBrowsableAttribute</span></span>

 <span data-ttu-id="7c55e-124">Применяя атрибут <xref:System.Diagnostics.DebuggerBrowsableAttribute> к полю или свойству, можно указать, как они будут отображаться в окне отладчика.</span><span class="sxs-lookup"><span data-stu-id="7c55e-124">Apply the <xref:System.Diagnostics.DebuggerBrowsableAttribute> to a field or property to specify how the field or property is to be displayed in the debugger window.</span></span> <span data-ttu-id="7c55e-125">Конструктор этого атрибута принимает одно из значений перечисления <xref:System.Diagnostics.DebuggerBrowsableState>, которое задает одно из следующих состояний:</span><span class="sxs-lookup"><span data-stu-id="7c55e-125">The constructor for this attribute takes one of the <xref:System.Diagnostics.DebuggerBrowsableState> enumeration values, which specifies one of the following states:</span></span>

- <span data-ttu-id="7c55e-126"><xref:System.Diagnostics.DebuggerBrowsableState.Never> указывает, что член не отображается в окне данных.</span><span class="sxs-lookup"><span data-stu-id="7c55e-126"><xref:System.Diagnostics.DebuggerBrowsableState.Never> indicates that the member is not displayed in the data window.</span></span>  <span data-ttu-id="7c55e-127">Например, если применить это значение к полю <xref:System.Diagnostics.DebuggerBrowsableAttribute>, это поле будет удалено из иерархии и не будет отображаться при развертывании включающего типа путем нажатия кнопки плюса (+) для экземпляра типа.</span><span class="sxs-lookup"><span data-stu-id="7c55e-127">For example, using this value for the <xref:System.Diagnostics.DebuggerBrowsableAttribute> on a field removes the field from the hierarchy; the field is not displayed when you expand the enclosing type by clicking the plus sign (+) for the type instance.</span></span>

- <span data-ttu-id="7c55e-128"><xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> указывает, что член отображается, но по умолчанию не развернут.</span><span class="sxs-lookup"><span data-stu-id="7c55e-128"><xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> indicates that the member is displayed but not expanded by default.</span></span>  <span data-ttu-id="7c55e-129">Это поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7c55e-129">This is the default behavior.</span></span>

- <span data-ttu-id="7c55e-130"><xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> указывает, что сам член не отображается, однако если это массив или коллекция, то выводятся составляющие его объекты.</span><span class="sxs-lookup"><span data-stu-id="7c55e-130"><xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> indicates that the member itself is not shown, but its constituent objects are displayed if it is an array or collection.</span></span>

> [!NOTE]
> <span data-ttu-id="7c55e-131">Атрибут <xref:System.Diagnostics.DebuggerBrowsableAttribute> не поддерживается в Visual Basic на платформе .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="7c55e-131">The <xref:System.Diagnostics.DebuggerBrowsableAttribute> is not supported by Visual Basic in the .NET Framework version 2.0.</span></span>

<span data-ttu-id="7c55e-132">В следующем примере кода показано, как использовать атрибут <xref:System.Diagnostics.DebuggerBrowsableAttribute>, чтобы отключить отображение следующего за ним свойства в окне отладки для класса.</span><span class="sxs-lookup"><span data-stu-id="7c55e-132">The following code example shows the use of the <xref:System.Diagnostics.DebuggerBrowsableAttribute> to prevent the property following it from appearing in the debug window for the class.</span></span>

```csharp
[DebuggerBrowsable(DebuggerBrowsableState.Never)]
public static string y = "Test String";
```

## <a name="using-the-debuggertypeproxy"></a><span data-ttu-id="7c55e-133">Использование атрибута DebuggerTypeProxy</span><span class="sxs-lookup"><span data-stu-id="7c55e-133">Using the DebuggerTypeProxy</span></span>

 <span data-ttu-id="7c55e-134">Атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> позволяет существенным образом изменить представление отладки для типа, не изменяя при этом сам тип.</span><span class="sxs-lookup"><span data-stu-id="7c55e-134">Use the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute when you need to significantly and fundamentally change the debugging view of a type, but not change the type itself.</span></span> <span data-ttu-id="7c55e-135">Атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> задает прокси-тип отображения для типа, позволяя разработчику настроить представление этого типа.</span><span class="sxs-lookup"><span data-stu-id="7c55e-135">The <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attribute is used to specify a display proxy for a type, allowing a developer to tailor the view for the type.</span></span>  <span data-ttu-id="7c55e-136">Как и <xref:System.Diagnostics.DebuggerDisplayAttribute>, этот атрибут можно использовать на уровне сборки. В этом случае свойство <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> задает тип, для которого будет использоваться прокси.</span><span class="sxs-lookup"><span data-stu-id="7c55e-136">This attribute, like the <xref:System.Diagnostics.DebuggerDisplayAttribute>, can be used at the assembly level, in which case the <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> property specifies the type for which the proxy will be used.</span></span> <span data-ttu-id="7c55e-137">Этот атрибут рекомендуется использовать для частного вложенного типа, входящего в тип, к которому применен этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="7c55e-137">The recommended usage is that this attribute specifies a private nested type that occurs within the type to which the attribute is applied.</span></span>  <span data-ttu-id="7c55e-138">При отображении типа вычислитель выражений, поддерживающий средства просмотра типов, проверяет наличие этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="7c55e-138">An expression evaluator that supports type viewers checks for this attribute when a type is displayed.</span></span> <span data-ttu-id="7c55e-139">Если он найден, вычислитель выражений заменяет прокси-тип отображения на тип, к которому применен этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="7c55e-139">If the attribute is found, the expression evaluator substitutes the display proxy type for the type the attribute is applied to.</span></span>

 <span data-ttu-id="7c55e-140">Если атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> задан, окно переменных отладчика отображает только открытые члены прокси-типа.</span><span class="sxs-lookup"><span data-stu-id="7c55e-140">When the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> is present, the debugger variable window displays only the public members of the proxy type.</span></span> <span data-ttu-id="7c55e-141">Закрытые члены не отображаются.</span><span class="sxs-lookup"><span data-stu-id="7c55e-141">Private members are not displayed.</span></span> <span data-ttu-id="7c55e-142">При использовании атрибутов просмотра поведение окна данных не изменяется.</span><span class="sxs-lookup"><span data-stu-id="7c55e-142">The behavior of the data window is not changed by attribute-enhanced views.</span></span>

 <span data-ttu-id="7c55e-143">Чтобы исключить потери производительности, атрибуты прокси-типа отображения обрабатываются только тогда, когда объект развертывается с помощью значка плюса (+) рядом с типом в окне данных или посредством атрибута <xref:System.Diagnostics.DebuggerBrowsableAttribute> в приложении.</span><span class="sxs-lookup"><span data-stu-id="7c55e-143">To avoid unnecessary performance penalties, attributes of the display proxy are not processed until the object is expanded, either through the user clicking the plus sign (+) next to the type in a data window, or through the application of the <xref:System.Diagnostics.DebuggerBrowsableAttribute> attribute.</span></span> <span data-ttu-id="7c55e-144">В связи с этим не рекомендуется применять атрибуты к типам отображения.</span><span class="sxs-lookup"><span data-stu-id="7c55e-144">Therefore, it is recommended that no attributes be applied to the display type.</span></span> <span data-ttu-id="7c55e-145">Атрибуты можно и нужно применять в основной части типа отображения.</span><span class="sxs-lookup"><span data-stu-id="7c55e-145">Attributes can and should be applied within the body of the display type.</span></span>

 <span data-ttu-id="7c55e-146">В следующем примере кода показано использование атрибута <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, указывающего тип, который будет использоваться в качестве прокси-типа отображения для отладчика.</span><span class="sxs-lookup"><span data-stu-id="7c55e-146">The following code example shows the use of the <xref:System.Diagnostics.DebuggerTypeProxyAttribute> to specify a type to be used as a debugger display proxy.</span></span>

```csharp
[DebuggerTypeProxy(typeof(HashtableDebugView))]
class MyHashtable : Hashtable
{
    private const string TestString =
        "This should not appear in the debug window.";

    internal class HashtableDebugView
    {
        private Hashtable hashtable;
        public const string TestStringProxy =
            "This should appear in the debug window.";

        // The constructor for the type proxy class must have a
        // constructor that takes the target type as a parameter.
        public HashtableDebugView(Hashtable hashtable)
        {
            this.hashtable = hashtable;
        }
    }
}
```

## <a name="example"></a><span data-ttu-id="7c55e-147">Пример</span><span class="sxs-lookup"><span data-stu-id="7c55e-147">Example</span></span>

### <a name="description"></a><span data-ttu-id="7c55e-148">Описание</span><span class="sxs-lookup"><span data-stu-id="7c55e-148">Description</span></span>

<span data-ttu-id="7c55e-149">Следующий пример кода можно просмотреть в Visual Studio, чтобы просмотреть результаты применения <xref:System.Diagnostics.DebuggerDisplayAttribute> <xref:System.Diagnostics.DebuggerBrowsableAttribute> атрибутов, и <xref:System.Diagnostics.DebuggerTypeProxyAttribute> .</span><span class="sxs-lookup"><span data-stu-id="7c55e-149">The following code example can be viewed in Visual Studio to see the results of applying the <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute>, and <xref:System.Diagnostics.DebuggerTypeProxyAttribute> attributes.</span></span>

### <a name="code"></a><span data-ttu-id="7c55e-150">Код</span><span class="sxs-lookup"><span data-stu-id="7c55e-150">Code</span></span>

[!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
[!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
[!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="7c55e-151">См. также</span><span class="sxs-lookup"><span data-stu-id="7c55e-151">See also</span></span>

- <xref:System.Diagnostics.DebuggerDisplayAttribute>
- <xref:System.Diagnostics.DebuggerBrowsableAttribute>
- <xref:System.Diagnostics.DebuggerTypeProxyAttribute>

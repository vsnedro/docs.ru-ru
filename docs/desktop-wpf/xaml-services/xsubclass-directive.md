---
title: Директива x:Subclass
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: e85e0fb5a0e1a865ed84a93767f8152a115bbe5f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432644"
---
# <a name="xsubclass-directive"></a><span data-ttu-id="90ce3-102">Директива x:Subclass</span><span class="sxs-lookup"><span data-stu-id="90ce3-102">x:Subclass Directive</span></span>

<span data-ttu-id="90ce3-103">Модифицирует поведение компиляции `x:Class` разметки XAML, когда это также предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="90ce3-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="90ce3-104">Вместо создания частичного класса, `x:Class`основанного `x:Class` на, при условии, создается как промежуточный класс, `x:Class`а затем ваш предоставленный производный класс, как ожидается, будет основываться на .</span><span class="sxs-lookup"><span data-stu-id="90ce3-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="90ce3-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="90ce3-105">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="90ce3-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="90ce3-106">XAML Values</span></span>

|||
|-|-|
|`namespace`|<span data-ttu-id="90ce3-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="90ce3-107">Optional.</span></span> <span data-ttu-id="90ce3-108">Упоняет пространство имен CLR, содержащее. `classname`</span><span class="sxs-lookup"><span data-stu-id="90ce3-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="90ce3-109">Если `namespace` указано, точка (.) `namespace` `classname`отделяется и .</span><span class="sxs-lookup"><span data-stu-id="90ce3-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|
|`classname`|<span data-ttu-id="90ce3-110">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="90ce3-110">Required.</span></span> <span data-ttu-id="90ce3-111">Укажите название CLR частичного класса, который соединяет загруженный XAML и ваш код-за для этого XAML.</span><span class="sxs-lookup"><span data-stu-id="90ce3-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="90ce3-112">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="90ce3-112">See Remarks.</span></span>|
|`subclassNamespace`|<span data-ttu-id="90ce3-113">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="90ce3-113">Optional.</span></span> <span data-ttu-id="90ce3-114">Может отличаться `namespace` от того, может ли каждое пространство имен решить другое.</span><span class="sxs-lookup"><span data-stu-id="90ce3-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="90ce3-115">Упоняет пространство имен CLR, содержащее. `subclassName`</span><span class="sxs-lookup"><span data-stu-id="90ce3-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="90ce3-116">Если `subclassName` указано, точка (.) `subclassNamespace` `subclassName`отделяется и .</span><span class="sxs-lookup"><span data-stu-id="90ce3-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|
|`subclassName`|<span data-ttu-id="90ce3-117">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="90ce3-117">Required.</span></span> <span data-ttu-id="90ce3-118">Упогоняет название подкласса CLR.</span><span class="sxs-lookup"><span data-stu-id="90ce3-118">Specifies the CLR name of the subclass.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="90ce3-119">Зависимости</span><span class="sxs-lookup"><span data-stu-id="90ce3-119">Dependencies</span></span>

<span data-ttu-id="90ce3-120">[x:Директива класса](xclass-directive.md) также должна быть предоставлена на одном объекте, и этот объект должен быть корневым элементом производства XAML.</span><span class="sxs-lookup"><span data-stu-id="90ce3-120">[x:Class Directive](xclass-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>

## <a name="remarks"></a><span data-ttu-id="90ce3-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="90ce3-121">Remarks</span></span>

<span data-ttu-id="90ce3-122">`x:Subclass`использование в первую очередь предназначено для языков, которые не поддерживают частичные классные декларации.</span><span class="sxs-lookup"><span data-stu-id="90ce3-122">`x:Subclass` usage is primarily intended for languages that do not support partial class declarations.</span></span>

<span data-ttu-id="90ce3-123">Класс, используемый `x:Subclass` как не вложенный `x:Subclass` класс, должен относиться к корневому объекту, как это объясняется в разделе "Зависимости".</span><span class="sxs-lookup"><span data-stu-id="90ce3-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>

<span data-ttu-id="90ce3-124">В противном случае `x:Subclass` концептуальное значение не определяется реализацией услуг .NET XAML.</span><span class="sxs-lookup"><span data-stu-id="90ce3-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET XAML Services implementation.</span></span> <span data-ttu-id="90ce3-125">Это связано с тем, что поведение .NET XAML Services не указывает общую модель программирования, с помощью которой связаны разметка XAML и код поддержки.</span><span class="sxs-lookup"><span data-stu-id="90ce3-125">This is because .NET XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="90ce3-126">Реализация дальнейших концепций, `x:Class` `x:Subclass` связанных с конкретными рамками, которые используют модели программирования или модели приложений для определения того, как подключить разметку XAML, компилированную разметку и кодна на основе CLR.</span><span class="sxs-lookup"><span data-stu-id="90ce3-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="90ce3-127">Каждая структура может иметь свои собственные действия сборки, которые позволяют некоторые из поведения, или конкретные компоненты, которые должны быть включены в среду сборки.</span><span class="sxs-lookup"><span data-stu-id="90ce3-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="90ce3-128">В рамках создания действия могут также варьироваться в зависимости от конкретного языка CLR, который используется для закидки кода.</span><span class="sxs-lookup"><span data-stu-id="90ce3-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="90ce3-129">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="90ce3-129">WPF Usage Notes</span></span>

<span data-ttu-id="90ce3-130">`x:Subclass`может быть на корне страницы или на <xref:System.Windows.Application> корне в `x:Class`определении приложения, которое уже имеется.</span><span class="sxs-lookup"><span data-stu-id="90ce3-130">`x:Subclass` can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="90ce3-131">Объявление `x:Subclass` на любой элемент, кроме страницы или корневого приложения, или указание его там, где его не `x:Class` существует, вызывает ошибку времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="90ce3-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>

<span data-ttu-id="90ce3-132">Создание производных классов, которые `x:Subclass` работают правильно для сценария, является довольно сложным.</span><span class="sxs-lookup"><span data-stu-id="90ce3-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="90ce3-133">Возможно, потребуется изучить промежуточные файлы (файлы .g, созданные в папке obj вашего проекта по компиляции разметки, с именами, которые включают имена файлов .xaml).</span><span class="sxs-lookup"><span data-stu-id="90ce3-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="90ce3-134">Эти промежуточные файлы могут помочь вам определить происхождение некоторых конструкций программирования в объединенных частичных классах в компилированном приложении.</span><span class="sxs-lookup"><span data-stu-id="90ce3-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>

<span data-ttu-id="90ce3-135">Обработчики событий в производном классе должны быть `internal override` (в`Friend Overrides` Microsoft Visual Basic) для того, чтобы переопределить заглушки для обработчиков, созданных в промежуточном классе во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="90ce3-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in Microsoft Visual Basic) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="90ce3-136">В противном случае выведенные реализации класса скрывают (тени) реализацию промежуточного класса, а обработчики промежуточных классов не вызываются.</span><span class="sxs-lookup"><span data-stu-id="90ce3-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>

<span data-ttu-id="90ce3-137">При определении `x:Class` `x:Subclass`и того, и другого не нужно предоставлять какую-либо реализацию для класса, на `x:Class`который ссылается .</span><span class="sxs-lookup"><span data-stu-id="90ce3-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="90ce3-138">Вам нужно только дать ему `x:Class` имя через атрибут, так что компилятор имеет некоторые указания для класса, который он создает в промежуточных файлах (компилятор не выбирает имя по умолчанию в этом случае).</span><span class="sxs-lookup"><span data-stu-id="90ce3-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="90ce3-139">Вы можете `x:Class` дать классу реализацию; однако, это не типичный `x:Class` сценарий для использования обоих и `x:Subclass`.</span><span class="sxs-lookup"><span data-stu-id="90ce3-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>

## <a name="see-also"></a><span data-ttu-id="90ce3-140">См. также</span><span class="sxs-lookup"><span data-stu-id="90ce3-140">See also</span></span>

- [<span data-ttu-id="90ce3-141">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="90ce3-141">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="90ce3-142">Код XAML и пользовательские классы для WPF</span><span class="sxs-lookup"><span data-stu-id="90ce3-142">XAML and Custom Classes for WPF</span></span>](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)

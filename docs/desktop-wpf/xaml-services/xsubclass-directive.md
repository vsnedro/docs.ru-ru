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
ms.openlocfilehash: b888ef73d1678fd37c984e4bb223f24e5b65d2cc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540723"
---
# <a name="xsubclass-directive"></a><span data-ttu-id="455ac-102">Директива x:Subclass</span><span class="sxs-lookup"><span data-stu-id="455ac-102">x:Subclass Directive</span></span>

<span data-ttu-id="455ac-103">Изменяет поведение компиляции разметки XAML `x:Class` , если также предоставляется.</span><span class="sxs-lookup"><span data-stu-id="455ac-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="455ac-104">Вместо создания разделяемого класса, основанного на `x:Class` , предоставленный объект `x:Class` создается как промежуточный класс, а затем предполагается, что предоставленный производный класс основан на `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="455ac-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="455ac-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="455ac-105">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="455ac-106">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="455ac-106">XAML Values</span></span>

|||
|-|-|
|`namespace`|<span data-ttu-id="455ac-107">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="455ac-107">Optional.</span></span> <span data-ttu-id="455ac-108">Указывает пространство имен CLR, содержащее `classname` .</span><span class="sxs-lookup"><span data-stu-id="455ac-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="455ac-109">Если `namespace` задано значение, точка (.) разделяет `namespace` и `classname` .</span><span class="sxs-lookup"><span data-stu-id="455ac-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|
|`classname`|<span data-ttu-id="455ac-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="455ac-110">Required.</span></span> <span data-ttu-id="455ac-111">Указывает CLR-имя разделяемого класса, который подключает загруженный XAML и код программной части для этого XAML.</span><span class="sxs-lookup"><span data-stu-id="455ac-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="455ac-112">См. заметки.</span><span class="sxs-lookup"><span data-stu-id="455ac-112">See Remarks.</span></span>|
|`subclassNamespace`|<span data-ttu-id="455ac-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="455ac-113">Optional.</span></span> <span data-ttu-id="455ac-114">Может отличаться от `namespace` , если каждое пространство имен может разрешать другое.</span><span class="sxs-lookup"><span data-stu-id="455ac-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="455ac-115">Указывает пространство имен CLR, содержащее `subclassName` .</span><span class="sxs-lookup"><span data-stu-id="455ac-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="455ac-116">Если `subclassName` задано значение, точка (.) разделяет `subclassNamespace` и `subclassName` .</span><span class="sxs-lookup"><span data-stu-id="455ac-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|
|`subclassName`|<span data-ttu-id="455ac-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="455ac-117">Required.</span></span> <span data-ttu-id="455ac-118">Задает имя подкласса CLR.</span><span class="sxs-lookup"><span data-stu-id="455ac-118">Specifies the CLR name of the subclass.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="455ac-119">Зависимости</span><span class="sxs-lookup"><span data-stu-id="455ac-119">Dependencies</span></span>

<span data-ttu-id="455ac-120">[директиву x:Class](xclass-directive.md) также необходимо предоставить для того же объекта, и этот объект должен быть корневым элементом рабочего элемента XAML.</span><span class="sxs-lookup"><span data-stu-id="455ac-120">[x:Class Directive](xclass-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>

## <a name="remarks"></a><span data-ttu-id="455ac-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="455ac-121">Remarks</span></span>

<span data-ttu-id="455ac-122">`x:Subclass` использование в основном предназначено для языков, которые не поддерживают объявления разделяемого класса.</span><span class="sxs-lookup"><span data-stu-id="455ac-122">`x:Subclass` usage is primarily intended for languages that do not support partial class declarations.</span></span>

<span data-ttu-id="455ac-123">Класс, используемый как, `x:Subclass` не может быть вложенным классом и `x:Subclass` должен ссылаться на корневой объект, как описано в разделе "зависимости".</span><span class="sxs-lookup"><span data-stu-id="455ac-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>

<span data-ttu-id="455ac-124">В противном случае концептуальное значение `x:Subclass` не определено реализацией служб XAML .NET.</span><span class="sxs-lookup"><span data-stu-id="455ac-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET XAML Services implementation.</span></span> <span data-ttu-id="455ac-125">Это обусловлено тем, что поведение служб XAML .NET не указывает общую модель программирования, с которой связаны разметка XAML и резервный код.</span><span class="sxs-lookup"><span data-stu-id="455ac-125">This is because .NET XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="455ac-126">Реализации дополнительных концепций, связанных с `x:Class` и `x:Subclass` , выполняются определенными платформами, которые используют модели программирования или модели приложений для определения способа подключения разметки XAML, скомпилированной разметки и кода программной части на основе среды CLR.</span><span class="sxs-lookup"><span data-stu-id="455ac-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="455ac-127">У каждой платформы могут быть собственные действия сборки, которые позволяют реализовать некоторое поведение или конкретные компоненты, которые должны быть включены в среду сборки.</span><span class="sxs-lookup"><span data-stu-id="455ac-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="455ac-128">В пределах платформы действия сборки также могут различаться в зависимости от конкретного языка среды CLR, используемого для кода программной части.</span><span class="sxs-lookup"><span data-stu-id="455ac-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="455ac-129">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="455ac-129">WPF Usage Notes</span></span>

<span data-ttu-id="455ac-130">`x:Subclass` может находиться в корне страницы или в <xref:System.Windows.Application> корне в определении приложения, которое уже имеет значение `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="455ac-130">`x:Subclass` can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="455ac-131">Объявление `x:Subclass` для любого элемента, отличного от корня страницы или приложения, или указания того, где не `x:Class` существует, вызывает ошибку времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="455ac-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>

<span data-ttu-id="455ac-132">Создание производных классов, правильно работающих для `x:Subclass` сценария, довольно сложно.</span><span class="sxs-lookup"><span data-stu-id="455ac-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="455ac-133">Может потребоваться изучить промежуточные файлы (файлы. g, созданные в папке obj проекта путем компиляции разметки с именами, включающими имена XAML-файлов).</span><span class="sxs-lookup"><span data-stu-id="455ac-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="455ac-134">Эти промежуточные файлы могут помочь определить происхождение определенных программных конструкций в Объединенных разделяемых классах в скомпилированном приложении.</span><span class="sxs-lookup"><span data-stu-id="455ac-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>

<span data-ttu-id="455ac-135">Обработчики событий в производном классе должны быть `internal override` ( `Friend Overrides` в Microsoft Visual Basic), чтобы переопределить заглушки для обработчиков, созданные в промежуточном классе во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="455ac-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in Microsoft Visual Basic) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="455ac-136">В противном случае реализации производного класса скрывают (затенить) реализацию промежуточного класса, а обработчики промежуточных классов не вызываются.</span><span class="sxs-lookup"><span data-stu-id="455ac-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>

<span data-ttu-id="455ac-137">При определении обоих `x:Class` методов и `x:Subclass` не требуется предоставлять какую-либо реализацию для класса, на который ссылается `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="455ac-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="455ac-138">Необходимо присвоить ему имя с помощью атрибута, `x:Class` чтобы компилятор предоставил некоторые рекомендации для класса, который он создает в промежуточных файлах (в данном случае компилятор не выбирает имя по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="455ac-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="455ac-139">Класс можно присвоить `x:Class` реализации, однако этот сценарий не является типичным для использования `x:Class` и `x:Subclass` .</span><span class="sxs-lookup"><span data-stu-id="455ac-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>

## <a name="see-also"></a><span data-ttu-id="455ac-140">См. также</span><span class="sxs-lookup"><span data-stu-id="455ac-140">See also</span></span>

- [<span data-ttu-id="455ac-141">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="455ac-141">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="455ac-142">Код XAML и пользовательские классы для WPF</span><span class="sxs-lookup"><span data-stu-id="455ac-142">XAML and Custom Classes for WPF</span></span>](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)

---
title: Элемент <compiler>
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
ms.openlocfilehash: 46676f25597f85596598d6f67c98930971cb0447
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088054"
---
# <a name="compiler-element"></a><span data-ttu-id="e3b12-102">Элемент \<compiler></span><span class="sxs-lookup"><span data-stu-id="e3b12-102">\<compiler> Element</span></span>

<span data-ttu-id="e3b12-103">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="e3b12-103">Specifies the compiler configuration attributes for a language provider.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**

## <a name="syntax"></a><span data-ttu-id="e3b12-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3b12-104">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3b12-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3b12-105">Attributes and Elements</span></span>

<span data-ttu-id="e3b12-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e3b12-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3b12-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3b12-107">Attributes</span></span>

|<span data-ttu-id="e3b12-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e3b12-108">Attribute</span></span>|<span data-ttu-id="e3b12-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="e3b12-109">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="e3b12-110">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e3b12-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e3b12-111">Задает дополнительные зависящие от компилятора аргументы для компиляции.</span><span class="sxs-lookup"><span data-stu-id="e3b12-111">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="e3b12-112">Значения для `compilerOptions` атрибута обычно перечислены в разделе параметров компилятора для компилятора.</span><span class="sxs-lookup"><span data-stu-id="e3b12-112">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="e3b12-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e3b12-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e3b12-114">Предоставляет разделенный точками с запятой список расширений имен файлов, используемых исходными файлами для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="e3b12-114">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="e3b12-115">Например, ".cs".</span><span class="sxs-lookup"><span data-stu-id="e3b12-115">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="e3b12-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e3b12-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="e3b12-117">Предоставляет разделенный точками с запятой список имен языков, поддерживаемых поставщиком языка.</span><span class="sxs-lookup"><span data-stu-id="e3b12-117">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="e3b12-118">Например, "C#;cs;csharp".</span><span class="sxs-lookup"><span data-stu-id="e3b12-118">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="e3b12-119">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e3b12-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="e3b12-120">Указывает имя типа поставщика языка, включая имя сборки, содержащей реализацию поставщика.</span><span class="sxs-lookup"><span data-stu-id="e3b12-120">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="e3b12-121">Имя типа должно соответствовать требованиям, определенным при [указании полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e3b12-121">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="e3b12-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e3b12-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e3b12-123">Задает уровень предупреждений компилятора по умолчанию. Определяет уровень, на котором поставщик языка рассматривает предупреждения компиляции как ошибки.</span><span class="sxs-lookup"><span data-stu-id="e3b12-123">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e3b12-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3b12-124">Child Elements</span></span>

|<span data-ttu-id="e3b12-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3b12-125">Element</span></span>|<span data-ttu-id="e3b12-126">Описание</span><span class="sxs-lookup"><span data-stu-id="e3b12-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3b12-127">\<providerOption>Дерев</span><span class="sxs-lookup"><span data-stu-id="e3b12-127">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="e3b12-128">Указывает атрибуты версии компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="e3b12-128">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e3b12-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3b12-129">Parent Elements</span></span>

|<span data-ttu-id="e3b12-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3b12-130">Element</span></span>|<span data-ttu-id="e3b12-131">Описание</span><span class="sxs-lookup"><span data-stu-id="e3b12-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3b12-132">\<configuration>Дерев</span><span class="sxs-lookup"><span data-stu-id="e3b12-132">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="e3b12-133">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e3b12-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="e3b12-134">\<system.codedom>Дерев</span><span class="sxs-lookup"><span data-stu-id="e3b12-134">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="e3b12-135">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="e3b12-135">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="e3b12-136">\<compilers>Дерев</span><span class="sxs-lookup"><span data-stu-id="e3b12-136">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="e3b12-137">Контейнер для элементов конфигурации компилятора; содержит ноль или более `<compiler>` элементов.</span><span class="sxs-lookup"><span data-stu-id="e3b12-137">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e3b12-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="e3b12-138">Remarks</span></span>

<span data-ttu-id="e3b12-139">Каждый `<compiler>` элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="e3b12-139">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="e3b12-140">Поставщик расширяет <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> класс для конкретного языка; `<compiler>` элемент определяет параметры компилятора и генератора кода для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="e3b12-140">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="e3b12-141">В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e3b12-141">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="e3b12-142">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="e3b12-142">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="e3b12-143">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3b12-143">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="e3b12-144">Элементы компилятора в файле приложения или веб-конфигурации могут дополнять или переопределять параметры в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="e3b12-144">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="e3b12-145">Если для одного и того же имени языка или одного расширения файла настроено несколько реализаций поставщика, последняя конфигурация сопоставления переопределяет все предыдущие настроенные поставщики для этого имени языка или расширения файла.</span><span class="sxs-lookup"><span data-stu-id="e3b12-145">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="e3b12-146">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="e3b12-146">Configuration File</span></span>

<span data-ttu-id="e3b12-147">Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e3b12-147">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="e3b12-148">Пример</span><span class="sxs-lookup"><span data-stu-id="e3b12-148">Example</span></span>

<span data-ttu-id="e3b12-149">В следующем примере показан типичный элемент конфигурации компилятора:</span><span class="sxs-lookup"><span data-stu-id="e3b12-149">The following example illustrates a typical compiler configuration element:</span></span>

```xml
<configuration>
  <system.codedom>
    <compilers>
      <!-- zero or more compiler elements -->
      <compiler
        language="c#;cs;csharp"
        extension=".cs"
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=2.0.3600.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"
        compilerOptions="/optimize"
        warningLevel="1" />
    </compilers>
  </system.codedom>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e3b12-150">См. также</span><span class="sxs-lookup"><span data-stu-id="e3b12-150">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="e3b12-151">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e3b12-151">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e3b12-152">\<compilers>Дерев</span><span class="sxs-lookup"><span data-stu-id="e3b12-152">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="e3b12-153">Указание полных имен типов</span><span class="sxs-lookup"><span data-stu-id="e3b12-153">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="e3b12-154">[Элемент compiler для элемента compilers для элемента compilation (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e3b12-154">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>

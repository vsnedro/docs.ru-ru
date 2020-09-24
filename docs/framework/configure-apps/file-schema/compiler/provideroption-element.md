---
title: Элемент <providerOption>
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: 9374fbaf7ceb61e5b72335417d32a08525477e0d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149638"
---
# <a name="provideroption-element"></a><span data-ttu-id="2f2b9-102">Элемент \<providerOption></span><span class="sxs-lookup"><span data-stu-id="2f2b9-102">\<providerOption> Element</span></span>

<span data-ttu-id="2f2b9-103">Указывает атрибуты версии компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-103">Specifies the compiler version attributes for a language provider.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**

## <a name="syntax"></a><span data-ttu-id="2f2b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f2b9-104">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f2b9-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2f2b9-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2f2b9-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f2b9-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2f2b9-107">Attributes</span></span>  
  
|<span data-ttu-id="2f2b9-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2f2b9-108">Attribute</span></span>|<span data-ttu-id="2f2b9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2f2b9-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="2f2b9-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="2f2b9-111">Указывает имя параметра. Например, "Компилерверсион".</span><span class="sxs-lookup"><span data-stu-id="2f2b9-111">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="2f2b9-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="2f2b9-113">Задает значение для параметра; Например, "v 3.5".</span><span class="sxs-lookup"><span data-stu-id="2f2b9-113">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f2b9-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2f2b9-114">Child Elements</span></span>  

 <span data-ttu-id="2f2b9-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f2b9-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2f2b9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="2f2b9-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="2f2b9-117">Element</span></span>|<span data-ttu-id="2f2b9-118">Описание</span><span class="sxs-lookup"><span data-stu-id="2f2b9-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f2b9-119">\<configuration> Элемент</span><span class="sxs-lookup"><span data-stu-id="2f2b9-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="2f2b9-120">Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-120">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="2f2b9-121">\<system.codedom> Элемент</span><span class="sxs-lookup"><span data-stu-id="2f2b9-121">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="2f2b9-122">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-122">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="2f2b9-123">\<compilers> Элемент</span><span class="sxs-lookup"><span data-stu-id="2f2b9-123">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="2f2b9-124">Контейнер для элементов конфигурации компилятора; содержит ноль или более `<compiler>` элементов.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-124">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="2f2b9-125">\<compiler> Элемент</span><span class="sxs-lookup"><span data-stu-id="2f2b9-125">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="2f2b9-126">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-126">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f2b9-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f2b9-127">Remarks</span></span>  

 <span data-ttu-id="2f2b9-128">В .NET Framework версии 3,5 поставщики кода Code Document Object Model (CodeDOM) могут поддерживать параметры, зависящие от поставщика, с помощью `<providerOption>` элемента.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-128">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="2f2b9-129">.NET Framework 3,5 включает обновленные сборки .NET Framework 2,0 и предоставляет новые сборки версии 3,5, содержащие новые типы.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-129">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="2f2b9-130">Поставщики кода Microsoft C# и Visual Basic содержатся в сборках .NET Framework 2,0, но были обновлены для поддержки компиляторов версии 3,5.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-130">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="2f2b9-131">По умолчанию обновленные поставщики кода создают код для компиляторов версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-131">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="2f2b9-132">С помощью элемента можно `<providerOption>` изменить целевую версию компилятора на 3,5.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-132">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="2f2b9-133">Для этого укажите для атрибута значение "Компилерверсион" `name` и "v 3.5" `value` .</span><span class="sxs-lookup"><span data-stu-id="2f2b9-133">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="2f2b9-134">Перед номером версии необходимо указать строчную букву "v".</span><span class="sxs-lookup"><span data-stu-id="2f2b9-134">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="2f2b9-135">Глобальную спецификацию версии можно сделать, добавив `<providerOption>` элемент в Machine.config .NET Framework 2,0 или корневой Web.config файл.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-135">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="2f2b9-136">Если вы обновляете версию компилятора по умолчанию до 3,5 в файле Machine.config, вы можете изменить ее обратно на 2,0 для каждого приложения, используя `<providerOption>` элемент в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-136">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="2f2b9-137">Разработчики поставщика кода CodeDOM могут обрабатывать пользовательские параметры, предоставляя конструктор, принимающий `providerOptions` параметр типа <xref:System.Collections.Generic.IDictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="2f2b9-137">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f2b9-138">Пример</span><span class="sxs-lookup"><span data-stu-id="2f2b9-138">Example</span></span>  

 <span data-ttu-id="2f2b9-139">В следующем примере показано, как указать, что должен использоваться поставщик кода C# версии 3,5.</span><span class="sxs-lookup"><span data-stu-id="2f2b9-139">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f2b9-140">См. также</span><span class="sxs-lookup"><span data-stu-id="2f2b9-140">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="2f2b9-141">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="2f2b9-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2f2b9-142">\<compilers> Элемент</span><span class="sxs-lookup"><span data-stu-id="2f2b9-142">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="2f2b9-143">Указание полных имен типов</span><span class="sxs-lookup"><span data-stu-id="2f2b9-143">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="2f2b9-144">[Элемент compiler для элемента compilers для элемента compilation (схема параметров ASP.NET)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2f2b9-144">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>

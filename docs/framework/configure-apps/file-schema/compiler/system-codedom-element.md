---
title: Элемент <system.codedom>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 6c35e24696be040788a0c44cbb100ebb35d37157
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149573"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="19c46-102">Элемент \<system.codedom></span><span class="sxs-lookup"><span data-stu-id="19c46-102">\<system.codedom> Element</span></span>

<span data-ttu-id="19c46-103">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="19c46-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
## <a name="syntax"></a><span data-ttu-id="19c46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19c46-104">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19c46-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="19c46-105">Attributes and Elements</span></span>  

 <span data-ttu-id="19c46-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="19c46-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19c46-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="19c46-107">Attributes</span></span>  

 <span data-ttu-id="19c46-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="19c46-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="19c46-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="19c46-109">Child Elements</span></span>  
  
|<span data-ttu-id="19c46-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="19c46-110">Element</span></span>|<span data-ttu-id="19c46-111">Описание</span><span class="sxs-lookup"><span data-stu-id="19c46-111">Description</span></span>|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|<span data-ttu-id="19c46-112">Контейнер для элементов конфигурации компилятора; содержит ноль или более [\<compiler>](compiler-element.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="19c46-112">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19c46-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="19c46-113">Parent Elements</span></span>  
  
|<span data-ttu-id="19c46-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="19c46-114">Element</span></span>|<span data-ttu-id="19c46-115">Описание</span><span class="sxs-lookup"><span data-stu-id="19c46-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="19c46-116">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19c46-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19c46-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="19c46-117">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="19c46-118">.NET Framework версии 2,0</span><span class="sxs-lookup"><span data-stu-id="19c46-118">.NET Framework Version 2.0</span></span>  

 <span data-ttu-id="19c46-119">[\<system.codedom>](system-codedom-element.md)Элемент содержит параметры конфигурации компилятора для поставщиков языков, установленных на компьютере в дополнение к поставщикам по умолчанию, которые устанавливаются вместе с .NET Framework, например <xref:Microsoft.CSharp.CSharpCodeProvider> и <xref:Microsoft.VisualBasic.VBCodeProvider> .</span><span class="sxs-lookup"><span data-stu-id="19c46-119">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="19c46-120">[\<compilers>](compilers-element.md)Элемент содержит ноль или более [\<compiler>](compiler-element.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="19c46-120">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="19c46-121">Каждый [\<compiler>](compiler-element.md) элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="19c46-121">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="19c46-122">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации в файл конфигурации компьютера (Machine.config) для новой <xref:System.CodeDom.Compiler.CodeDomProvider> реализации.</span><span class="sxs-lookup"><span data-stu-id="19c46-122">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="19c46-123">Используйте <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> метод для программного перечисления поставщиков языка по умолчанию и поставщиков языков, определенных параметрами конфигурации компилятора на компьютере.</span><span class="sxs-lookup"><span data-stu-id="19c46-123">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19c46-124">В .NET Framework версиях 1,0 и 1,1 поставщики языка по умолчанию, предоставляемые .NET Framework, идентифицируются в [\<compilers>](compilers-element.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="19c46-124">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="19c46-125">В .NET Framework версии 2,0 поставщики языка по умолчанию не определяются в [\<compilers>](compilers-element.md) элементе, но их можно перечислить с помощью <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="19c46-125">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="19c46-126">.NET Framework версии 1,0 и 1,1</span><span class="sxs-lookup"><span data-stu-id="19c46-126">.NET Framework Versions 1.0 and 1.1</span></span>  

 <span data-ttu-id="19c46-127">[\<system.codedom>](system-codedom-element.md)Элемент содержит параметры конфигурации компилятора для поставщиков языков на компьютере.</span><span class="sxs-lookup"><span data-stu-id="19c46-127">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="19c46-128">[\<compilers>](compilers-element.md)Элемент содержит ноль или более [\<compiler>](compiler-element.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="19c46-128">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="19c46-129">Каждый [\<compiler>](compiler-element.md) элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="19c46-129">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="19c46-130">В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="19c46-130">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="19c46-131">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="19c46-131">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="19c46-132">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="19c46-132">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="19c46-133">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="19c46-133">Configuration File</span></span>  

 <span data-ttu-id="19c46-134">Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="19c46-134">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19c46-135">Пример</span><span class="sxs-lookup"><span data-stu-id="19c46-135">Example</span></span>  

 <span data-ttu-id="19c46-136">В следующем примере показана типичная конфигурация компилятора.</span><span class="sxs-lookup"><span data-stu-id="19c46-136">The following example illustrates a typical compiler configuration.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=1.0.5000.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="19c46-137">См. также</span><span class="sxs-lookup"><span data-stu-id="19c46-137">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="19c46-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="19c46-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="19c46-139">Схема параметров поставщиков языков и компиляторов</span><span class="sxs-lookup"><span data-stu-id="19c46-139">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="19c46-140">\<compiler> Элемент</span><span class="sxs-lookup"><span data-stu-id="19c46-140">\<compiler> Element</span></span>](compiler-element.md)

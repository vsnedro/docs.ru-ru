---
title: Элемент <compilers>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
ms.openlocfilehash: 09b1efe321c39402c9280eda0e9def9112462470
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155418"
---
# <a name="compilers-element"></a><span data-ttu-id="4a0b9-102">Элемент \<compilers></span><span class="sxs-lookup"><span data-stu-id="4a0b9-102">\<compilers> Element</span></span>
<span data-ttu-id="4a0b9-103">Контейнер для элементов конфигурации компилятора; содержит ноль или более [\<compiler>](compiler-element.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**

## <a name="syntax"></a><span data-ttu-id="4a0b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a0b9-104">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a0b9-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4a0b9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4a0b9-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a0b9-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4a0b9-107">Attributes</span></span>  
 <span data-ttu-id="4a0b9-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4a0b9-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4a0b9-109">Child Elements</span></span>  
  
|<span data-ttu-id="4a0b9-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="4a0b9-110">Element</span></span>|<span data-ttu-id="4a0b9-111">Описание</span><span class="sxs-lookup"><span data-stu-id="4a0b9-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a0b9-112">\<compiler>Дерев</span><span class="sxs-lookup"><span data-stu-id="4a0b9-112">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="4a0b9-113">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-113">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4a0b9-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4a0b9-114">Parent Elements</span></span>  
  
|<span data-ttu-id="4a0b9-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="4a0b9-115">Element</span></span>|<span data-ttu-id="4a0b9-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4a0b9-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a0b9-117">\<configuration>Дерев</span><span class="sxs-lookup"><span data-stu-id="4a0b9-117">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="4a0b9-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="4a0b9-119">\<system.codedom>Дерев</span><span class="sxs-lookup"><span data-stu-id="4a0b9-119">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="4a0b9-120">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-120">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a0b9-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a0b9-121">Remarks</span></span>  
 <span data-ttu-id="4a0b9-122">[\<compilers>](compilers-element.md)Элемент содержит параметры конфигурации компилятора для поставщиков языков на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-122">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="4a0b9-123">Каждый [\<compiler>](compiler-element.md) элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-123">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="4a0b9-124">.NET Framework определяет начальные параметры компилятора и языка в файле конфигурации компьютера (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="4a0b9-124">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="4a0b9-125">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-125">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="4a0b9-126">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-126">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4a0b9-127">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="4a0b9-127">Configuration File</span></span>  
 <span data-ttu-id="4a0b9-128">Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-128">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a0b9-129">Пример</span><span class="sxs-lookup"><span data-stu-id="4a0b9-129">Example</span></span>  
 <span data-ttu-id="4a0b9-130">В приведенном ниже примере показан типичный элемент конфигурации компилятора.</span><span class="sxs-lookup"><span data-stu-id="4a0b9-130">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler
          language="c#;cs;csharp"
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a0b9-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4a0b9-131">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="4a0b9-132">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="4a0b9-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4a0b9-133">Схема параметров поставщиков языков и компиляторов</span><span class="sxs-lookup"><span data-stu-id="4a0b9-133">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4a0b9-134">\<compiler>Дерев</span><span class="sxs-lookup"><span data-stu-id="4a0b9-134">\<compiler> Element</span></span>](compiler-element.md)

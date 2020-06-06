---
title: Элемент <codeBase>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: 475b7df55ed509157c1da0aeb8f979de238c72b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70971891"
---
# <a name="codebase-element"></a><span data-ttu-id="fc77f-102">Элемент \<codeBase></span><span class="sxs-lookup"><span data-stu-id="fc77f-102">\<codeBase> Element</span></span>

<span data-ttu-id="fc77f-103">Указывает, где среда CLR может найти сборку.</span><span class="sxs-lookup"><span data-stu-id="fc77f-103">Specifies where the common language runtime can find an assembly.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<codeBase>**

## <a name="syntax"></a><span data-ttu-id="fc77f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc77f-104">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fc77f-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fc77f-105">Attributes and Elements</span></span>

<span data-ttu-id="fc77f-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fc77f-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fc77f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fc77f-107">Attributes</span></span>

|<span data-ttu-id="fc77f-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fc77f-108">Attribute</span></span>|<span data-ttu-id="fc77f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fc77f-109">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="fc77f-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="fc77f-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="fc77f-111">Указывает URL-адрес, по которому среда выполнения может найти указанную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="fc77f-111">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="fc77f-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="fc77f-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="fc77f-113">Указывает версию сборки, к которой применяется база кода.</span><span class="sxs-lookup"><span data-stu-id="fc77f-113">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="fc77f-114">Номер версии сборки имеет формат *основной. дополнительный. сборка. Редакция*.</span><span class="sxs-lookup"><span data-stu-id="fc77f-114">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="fc77f-115">Атрибут версии</span><span class="sxs-lookup"><span data-stu-id="fc77f-115">version Attribute</span></span>

|<span data-ttu-id="fc77f-116">Значение</span><span class="sxs-lookup"><span data-stu-id="fc77f-116">Value</span></span>|<span data-ttu-id="fc77f-117">Описание</span><span class="sxs-lookup"><span data-stu-id="fc77f-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="fc77f-118">Допустимые значения для каждой части номера версии — от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="fc77f-118">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="fc77f-119">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="fc77f-119">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fc77f-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fc77f-120">Child Elements</span></span>

<span data-ttu-id="fc77f-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fc77f-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fc77f-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fc77f-122">Parent Elements</span></span>

|<span data-ttu-id="fc77f-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="fc77f-123">Element</span></span>|<span data-ttu-id="fc77f-124">Описание</span><span class="sxs-lookup"><span data-stu-id="fc77f-124">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="fc77f-125">Определяет набор поставщиков построения, которые используются для компиляции пользовательских файлов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="fc77f-125">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="fc77f-126">Можно использовать любое число поставщиков построения.</span><span class="sxs-lookup"><span data-stu-id="fc77f-126">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="fc77f-127">Настраивает все параметры компиляции, используемые ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fc77f-127">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="fc77f-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fc77f-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="fc77f-129">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fc77f-129">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fc77f-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="fc77f-130">Remarks</span></span>

<span data-ttu-id="fc77f-131">Чтобы среда выполнения использовала **\<codeBase>** параметр в файле конфигурации компьютера или файле политики издателя, файл должен также перенаправлять версию сборки.</span><span class="sxs-lookup"><span data-stu-id="fc77f-131">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="fc77f-132">Файлы конфигурации приложения могут иметь параметр базы кода без перенаправления версии сборки.</span><span class="sxs-lookup"><span data-stu-id="fc77f-132">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="fc77f-133">После определения используемой версии сборки среда выполнения применяет параметр базы кода из файла, определяющего версию.</span><span class="sxs-lookup"><span data-stu-id="fc77f-133">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="fc77f-134">Если база кода не указана, среда выполнения проверяет наличие сборки обычным способом.</span><span class="sxs-lookup"><span data-stu-id="fc77f-134">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="fc77f-135">Если сборка имеет строгое имя, параметр базы кода может находиться в любом месте локальной интрасети или в Интернете.</span><span class="sxs-lookup"><span data-stu-id="fc77f-135">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="fc77f-136">Если сборка является закрытой, параметр базы кода должен быть путем относительно каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="fc77f-136">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="fc77f-137">Для сборок без строгого имени версия игнорируется, а загрузчик использует первый внешний вид \<codebase> внутри \<dependentAssembly> .</span><span class="sxs-lookup"><span data-stu-id="fc77f-137">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="fc77f-138">Если в файле конфигурации приложения имеется запись, которая перенаправляет привязку к другой сборке, перенаправление будет иметь приоритет, даже если версия сборки не соответствует запросу привязки.</span><span class="sxs-lookup"><span data-stu-id="fc77f-138">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="fc77f-139">Пример</span><span class="sxs-lookup"><span data-stu-id="fc77f-139">Example</span></span>

<span data-ttu-id="fc77f-140">В следующем примере показано, как указать, где среда выполнения может найти сборку.</span><span class="sxs-lookup"><span data-stu-id="fc77f-140">The following example shows how to specify where the runtime can find an assembly.</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly"
                              publicKeyToken="32ab4ba45e0a69a1"
                              culture="neutral" />
            <codeBase version="2.0.0.0"
                      href="http://www.litwareinc.com/myAssembly.dll"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="fc77f-141">См. также</span><span class="sxs-lookup"><span data-stu-id="fc77f-141">See also</span></span>

- [<span data-ttu-id="fc77f-142">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="fc77f-142">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="fc77f-143">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="fc77f-143">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="fc77f-144">Укажите расположение сборки</span><span class="sxs-lookup"><span data-stu-id="fc77f-144">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="fc77f-145">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="fc77f-145">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)

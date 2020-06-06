---
title: Схема файлов конфигурации для .NET Framework
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
ms.openlocfilehash: 35ed53fc480e218df595794f80af2458f3ecec38
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73039159"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="e24ab-102">Схема файлов конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e24ab-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="e24ab-103">Файлы конфигурации — это стандартные XML-файлы, которые можно использовать для изменения параметров и установки политик для приложений.</span><span class="sxs-lookup"><span data-stu-id="e24ab-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="e24ab-104">Схема конфигурации .NET Framework состоит из элементов, которые можно использовать в файлах конфигурации для управления поведением приложений.</span><span class="sxs-lookup"><span data-stu-id="e24ab-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="e24ab-105">Оглавление данного раздела отражает иерархию схемы для запуска, среды выполнения, сети и других типов параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e24ab-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="e24ab-106">Сведения о типах, формате и расположении файлов конфигурации см. в разделе [Настройка приложений](../index.md).</span><span class="sxs-lookup"><span data-stu-id="e24ab-106">For information about the types, format, and location of configuration files, see [Configure apps](../index.md).</span></span> <span data-ttu-id="e24ab-107">Для редактирования файлов конфигурации напрямую необходимо иметь представление о языке XML.</span><span class="sxs-lookup"><span data-stu-id="e24ab-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e24ab-108">В тегах и атрибутах XML в файлах конфигурации учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="e24ab-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e24ab-109">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="e24ab-109">In this section</span></span>

<span data-ttu-id="e24ab-110">[**\<configuration>** Дерев](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-110">[**\<configuration>** Element](configuration-element.md)</span></span>\
<span data-ttu-id="e24ab-111">Элемент верхнего уровня для всех файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e24ab-111">The top-level element for all configuration files.</span></span>

<span data-ttu-id="e24ab-112">[**\<assemblyBinding>** Дерев](assemblybinding-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-112">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="e24ab-113">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e24ab-113">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="e24ab-114">[**\<linkedConfiguration>** Дерев](linkedconfiguration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-114">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md)</span></span>\
<span data-ttu-id="e24ab-115">Указание файла конфигурации, который следует включить.</span><span class="sxs-lookup"><span data-stu-id="e24ab-115">Specifies a configuration file to include.</span></span>

<span data-ttu-id="e24ab-116">[Схема параметров запуска](./startup/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-116">[Startup Settings Schema](./startup/index.md)</span></span>\
<span data-ttu-id="e24ab-117">Элементы, указывающие используемую версию среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e24ab-117">Elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="e24ab-118">[Схема параметров среды выполнения](./runtime/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-118">[Runtime Settings Schema](./runtime/index.md)</span></span>\
<span data-ttu-id="e24ab-119">Элементы, которые настраивают привязку сборки и поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e24ab-119">Elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="e24ab-120">[Схема параметров сети](./network/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-120">[Network Settings Schema](./network/index.md)</span></span>\
<span data-ttu-id="e24ab-121">Элементы, указывающие, как .NET Framework подключается к Интернету.</span><span class="sxs-lookup"><span data-stu-id="e24ab-121">Elements that specify how the .NET Framework connects to the internet.</span></span>

<span data-ttu-id="e24ab-122">[Схема параметров шифрования](./cryptography/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-122">[Cryptography Settings Schema](./cryptography/index.md)</span></span>\
<span data-ttu-id="e24ab-123">Элементы, которые сопоставляют понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.</span><span class="sxs-lookup"><span data-stu-id="e24ab-123">Elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="e24ab-124">[Схема разделов конфигурации](configuration-sections-schema.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-124">[Configuration Sections Schema](configuration-sections-schema.md)</span></span>\
<span data-ttu-id="e24ab-125">Элементы, используемые для создания и использования разделов конфигурации для пользовательских параметров.</span><span class="sxs-lookup"><span data-stu-id="e24ab-125">Elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="e24ab-126">[Схема параметров трассировки и отладки](./trace-debug/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-126">[Trace and Debug Settings Schema](./trace-debug/index.md)</span></span>\
<span data-ttu-id="e24ab-127">Элементы, задающих переключатели и прослушиватели трассировки.</span><span class="sxs-lookup"><span data-stu-id="e24ab-127">Elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="e24ab-128">[Схема параметров поставщика языка и компилятора](./compiler/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-128">[Compiler and Language Provider Settings Schema](./compiler/index.md)</span></span>\
<span data-ttu-id="e24ab-129">Элементы, задающих конфигурацию компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="e24ab-129">Elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="e24ab-130">[Схема параметров приложения](application-settings-schema.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-130">[Application Settings Schema](application-settings-schema.md)</span></span>\
<span data-ttu-id="e24ab-131">Элементы, которые позволяют приложению Windows Forms или ASP.NET сохранять и извлекать параметры приложения и области пользователя.</span><span class="sxs-lookup"><span data-stu-id="e24ab-131">Elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="e24ab-132">[Схема параметров приложения](./appsettings/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-132">[App Settings Schema](./appsettings/index.md)</span></span>\
<span data-ttu-id="e24ab-133">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e24ab-133">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="e24ab-134">[Схема веб-параметров](./web/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-134">[Web Settings Schema](./web/index.md)</span></span>\
<span data-ttu-id="e24ab-135">Элементы для настройки работы ASP.NET с ведущим приложением, например IIS.</span><span class="sxs-lookup"><span data-stu-id="e24ab-135">Elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="e24ab-136">Используются в файлах *Aspnet.config*.</span><span class="sxs-lookup"><span data-stu-id="e24ab-136">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="e24ab-137">[Схема конфигурации Windows Forms](winforms/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-137">[Windows Forms Configuration Schema](winforms/index.md)</span></span>\
<span data-ttu-id="e24ab-138">Все элементы в разделе конфигурации приложения Windows Forms, включая настройки с поддержкой нескольких мониторов и высокого DPI.</span><span class="sxs-lookup"><span data-stu-id="e24ab-138">All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high-DPI support.</span></span>

<span data-ttu-id="e24ab-139">[Схема конфигурации WCF](./wcf/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-139">[WCF Configuration Schema](./wcf/index.md)</span></span>\
<span data-ttu-id="e24ab-140">Все элементы, которые позволяют настроить службу WCF и клиентские приложения.</span><span class="sxs-lookup"><span data-stu-id="e24ab-140">All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="e24ab-141">[Синтаксис директив WCF](./wcf-directive/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-141">[WCF Directive Syntax](./wcf-directive/index.md)</span></span>\
<span data-ttu-id="e24ab-142">Описывает `@ServiceHost` директиву, которая определяет атрибуты, зависящие от страницы, используемые компилятором SVC.</span><span class="sxs-lookup"><span data-stu-id="e24ab-142">Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="e24ab-143">[Схема конфигурации WIF](windows-identity-foundation/index.md)</span><span class="sxs-lookup"><span data-stu-id="e24ab-143">[WIF Configuration Schema](windows-identity-foundation/index.md)</span></span>\
<span data-ttu-id="e24ab-144">Все элементы схемы конфигурации Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="e24ab-144">All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="e24ab-145">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e24ab-145">Related sections</span></span>

<span data-ttu-id="e24ab-146">[Схема параметров удаленного взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e24ab-146">[Remoting Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span>\
<span data-ttu-id="e24ab-147">Описание элементов, настраивающих клиентские и серверные приложения, реализующие удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="e24ab-147">Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="e24ab-148">[Схема параметров ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e24ab-148">[ASP.NET Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span>\
<span data-ttu-id="e24ab-149">Описание элемента, управляющего поведением веб-приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e24ab-149">Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="e24ab-150">[Схема параметров веб-служб](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e24ab-150">[Web Services Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span>\
<span data-ttu-id="e24ab-151">Описание элемента, управляющего поведением веб-служб ASP.NET Web и их клиентов.</span><span class="sxs-lookup"><span data-stu-id="e24ab-151">Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="e24ab-152">[Настройка приложений .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e24ab-152">[Configuring .NET Framework Apps](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span></span>\
<span data-ttu-id="e24ab-153">Описание способов настройки безопасности, привязки сборок и удаленного взаимодействия в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e24ab-153">Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>

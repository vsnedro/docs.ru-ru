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
ms.openlocfilehash: ab6f12be01899f5b7e54a7ec2d9675d502d88bc3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555137"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="0ba15-102">Схема файлов конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0ba15-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="0ba15-103">Файлы конфигурации — это стандартные XML-файлы, которые можно использовать для изменения параметров и установки политик для приложений.</span><span class="sxs-lookup"><span data-stu-id="0ba15-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="0ba15-104">Схема конфигурации .NET Framework состоит из элементов, которые можно использовать в файлах конфигурации для управления поведением приложений.</span><span class="sxs-lookup"><span data-stu-id="0ba15-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="0ba15-105">Оглавление данного раздела отражает иерархию схемы для запуска, среды выполнения, сети и других типов параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0ba15-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="0ba15-106">Сведения о типах, формате и расположении файлов конфигурации см. в разделе [Настройка приложений](../index.md).</span><span class="sxs-lookup"><span data-stu-id="0ba15-106">For information about the types, format, and location of configuration files, see [Configure apps](../index.md).</span></span> <span data-ttu-id="0ba15-107">Для редактирования файлов конфигурации напрямую необходимо иметь представление о языке XML.</span><span class="sxs-lookup"><span data-stu-id="0ba15-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ba15-108">В тегах и атрибутах XML в файлах конфигурации учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="0ba15-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0ba15-109">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="0ba15-109">In this section</span></span>

<span data-ttu-id="0ba15-110">[**\<configuration>** Дерев](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-110">[**\<configuration>** Element](configuration-element.md)</span></span>\
<span data-ttu-id="0ba15-111">Элемент верхнего уровня для всех файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0ba15-111">The top-level element for all configuration files.</span></span>

<span data-ttu-id="0ba15-112">[**\<assemblyBinding>** Дерев](assemblybinding-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-112">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="0ba15-113">Определяет политику привязки сборок на уровне конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0ba15-113">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="0ba15-114">[**\<linkedConfiguration>** Дерев](linkedconfiguration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-114">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md)</span></span>\
<span data-ttu-id="0ba15-115">Указание файла конфигурации, который следует включить.</span><span class="sxs-lookup"><span data-stu-id="0ba15-115">Specifies a configuration file to include.</span></span>

<span data-ttu-id="0ba15-116">[Схема параметров запуска](./startup/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-116">[Startup Settings Schema](./startup/index.md)</span></span>\
<span data-ttu-id="0ba15-117">Элементы, указывающие используемую версию среды CLR.</span><span class="sxs-lookup"><span data-stu-id="0ba15-117">Elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="0ba15-118">[Схема параметров среды выполнения](./runtime/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-118">[Runtime Settings Schema](./runtime/index.md)</span></span>\
<span data-ttu-id="0ba15-119">Элементы, которые настраивают привязку сборки и поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0ba15-119">Elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="0ba15-120">[Схема параметров сети](./network/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-120">[Network Settings Schema](./network/index.md)</span></span>\
<span data-ttu-id="0ba15-121">Элементы, указывающие, как .NET Framework подключается к Интернету.</span><span class="sxs-lookup"><span data-stu-id="0ba15-121">Elements that specify how the .NET Framework connects to the internet.</span></span>

<span data-ttu-id="0ba15-122">[Схема параметров шифрования](./cryptography/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-122">[Cryptography Settings Schema](./cryptography/index.md)</span></span>\
<span data-ttu-id="0ba15-123">Элементы, которые сопоставляют понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.</span><span class="sxs-lookup"><span data-stu-id="0ba15-123">Elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="0ba15-124">[Схема разделов конфигурации](configuration-sections-schema.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-124">[Configuration Sections Schema](configuration-sections-schema.md)</span></span>\
<span data-ttu-id="0ba15-125">Элементы, используемые для создания и использования разделов конфигурации для пользовательских параметров.</span><span class="sxs-lookup"><span data-stu-id="0ba15-125">Elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="0ba15-126">[Схема параметров трассировки и отладки](./trace-debug/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-126">[Trace and Debug Settings Schema](./trace-debug/index.md)</span></span>\
<span data-ttu-id="0ba15-127">Элементы, задающих переключатели и прослушиватели трассировки.</span><span class="sxs-lookup"><span data-stu-id="0ba15-127">Elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="0ba15-128">[Схема параметров поставщика языка и компилятора](./compiler/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-128">[Compiler and Language Provider Settings Schema](./compiler/index.md)</span></span>\
<span data-ttu-id="0ba15-129">Элементы, задающих конфигурацию компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="0ba15-129">Elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="0ba15-130">[Схема параметров приложения](application-settings-schema.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-130">[Application Settings Schema](application-settings-schema.md)</span></span>\
<span data-ttu-id="0ba15-131">Элементы, которые позволяют приложению Windows Forms или ASP.NET сохранять и извлекать параметры приложения и области пользователя.</span><span class="sxs-lookup"><span data-stu-id="0ba15-131">Elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="0ba15-132">[Схема параметров приложения](./appsettings/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-132">[App Settings Schema](./appsettings/index.md)</span></span>\
<span data-ttu-id="0ba15-133">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="0ba15-133">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="0ba15-134">[Схема веб-параметров](./web/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-134">[Web Settings Schema](./web/index.md)</span></span>\
<span data-ttu-id="0ba15-135">Элементы для настройки работы ASP.NET с ведущим приложением, например IIS.</span><span class="sxs-lookup"><span data-stu-id="0ba15-135">Elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="0ba15-136">Используются в файлах *Aspnet.config*.</span><span class="sxs-lookup"><span data-stu-id="0ba15-136">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="0ba15-137">[Схема конфигурации Windows Forms](winforms/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-137">[Windows Forms Configuration Schema](winforms/index.md)</span></span>\
<span data-ttu-id="0ba15-138">Все элементы в разделе конфигурации приложения Windows Forms, включая настройки с поддержкой нескольких мониторов и высокого DPI.</span><span class="sxs-lookup"><span data-stu-id="0ba15-138">All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high-DPI support.</span></span>

<span data-ttu-id="0ba15-139">[Схема конфигурации WCF](./wcf/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-139">[WCF Configuration Schema](./wcf/index.md)</span></span>\
<span data-ttu-id="0ba15-140">Все элементы, которые позволяют настроить службу WCF и клиентские приложения.</span><span class="sxs-lookup"><span data-stu-id="0ba15-140">All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="0ba15-141">[Синтаксис директив WCF](./wcf-directive/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-141">[WCF Directive Syntax](./wcf-directive/index.md)</span></span>\
<span data-ttu-id="0ba15-142">Описывает `@ServiceHost` директиву, которая определяет атрибуты, зависящие от страницы, используемые компилятором SVC.</span><span class="sxs-lookup"><span data-stu-id="0ba15-142">Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="0ba15-143">[Схема конфигурации WIF](windows-identity-foundation/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ba15-143">[WIF Configuration Schema](windows-identity-foundation/index.md)</span></span>\
<span data-ttu-id="0ba15-144">Все элементы схемы конфигурации Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="0ba15-144">All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="0ba15-145">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0ba15-145">Related sections</span></span>

<span data-ttu-id="0ba15-146">[Схема параметров удаленного взаимодействия](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0ba15-146">[Remoting Settings Schema](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span>\
<span data-ttu-id="0ba15-147">Описание элементов, настраивающих клиентские и серверные приложения, реализующие удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="0ba15-147">Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="0ba15-148">[Схема параметров ASP.NET](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0ba15-148">[ASP.NET Settings Schema](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span>\
<span data-ttu-id="0ba15-149">Описание элемента, управляющего поведением веб-приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0ba15-149">Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="0ba15-150">[Схема параметров веб-служб](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0ba15-150">[Web Services Settings Schema](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span>\
<span data-ttu-id="0ba15-151">Описание элемента, управляющего поведением веб-служб ASP.NET Web и их клиентов.</span><span class="sxs-lookup"><span data-stu-id="0ba15-151">Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="0ba15-152">[Настройка приложений .NET Framework](/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0ba15-152">[Configuring .NET Framework Apps](/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span></span>\
<span data-ttu-id="0ba15-153">Описание способов настройки безопасности, привязки сборок и удаленного взаимодействия в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ba15-153">Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>

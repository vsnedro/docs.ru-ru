---
title: Развертывание .NET Framework и приложений
description: Начало развертывания .NET с приложением. Платформа .NET предоставляет изолированные приложения, частные компоненты по умолчанию, общий доступ к управляемому коду, а также многие другие возможности.
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], packaging
- deploying applications [.NET Framework]
- deploying applications [.NET Framework], features
- deploying applications [.NET Framework], distribution
- .NET Framework, deploying
- .NET Framework application deployment
ms.assetid: 238d8284-6042-4a38-a7f6-1ee8efd719da
ms.openlocfilehash: cce888c962c9ab83c13cce4040eb9ba50270972d
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803507"
---
# <a name="deploying-the-net-framework-and-applications"></a><span data-ttu-id="b3429-104">Развертывание .NET Framework и приложений</span><span class="sxs-lookup"><span data-stu-id="b3429-104">Deploying the .NET Framework and Applications</span></span>

<span data-ttu-id="b3429-105">Эта статья поможет приступить к развертыванию платформы .NET Framework с приложением.</span><span class="sxs-lookup"><span data-stu-id="b3429-105">This article helps you get started deploying the .NET Framework with your application.</span></span> <span data-ttu-id="b3429-106">Большая часть информации предназначена для разработчиков, изготовителей оборудования и администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="b3429-106">Most of the information is intended for developers, OEMs, and enterprise administrators.</span></span> <span data-ttu-id="b3429-107">Пользователям, которые хотят установить .NET Framework на своих компьютерах, следует прочитать статью [Установка .NET Framework](../install/index.md).</span><span class="sxs-lookup"><span data-stu-id="b3429-107">Users who want to install the .NET Framework on their computers should read [Installing the .NET Framework](../install/index.md).</span></span>

## <a name="key-deployment-resources"></a><span data-ttu-id="b3429-108">Основные ресурсы, посвященные развертыванию</span><span class="sxs-lookup"><span data-stu-id="b3429-108">Key Deployment Resources</span></span>

<span data-ttu-id="b3429-109">Для получения дополнительных сведений о развертывании и обслуживании .NET Framework воспользуйтесь приведенными ниже ссылками на другие разделы MSDN.</span><span class="sxs-lookup"><span data-stu-id="b3429-109">Use the following links to other MSDN topics for specific information about deploying and servicing the .NET Framework.</span></span>

<span data-ttu-id="b3429-110">**Установка и развертывание**</span><span class="sxs-lookup"><span data-stu-id="b3429-110">**Setup and deployment**</span></span>

- <span data-ttu-id="b3429-111">Общие сведения об установщиках и развертывании:</span><span class="sxs-lookup"><span data-stu-id="b3429-111">General installer and deployment information:</span></span>

  - <span data-ttu-id="b3429-112">Тип установщика:</span><span class="sxs-lookup"><span data-stu-id="b3429-112">Installer options:</span></span>

    - <span data-ttu-id="b3429-113">[веб-установщик](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable);</span><span class="sxs-lookup"><span data-stu-id="b3429-113">[Web installer](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)</span></span>

    - <span data-ttu-id="b3429-114">[автономный установщик](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable).</span><span class="sxs-lookup"><span data-stu-id="b3429-114">[Offline installer](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)</span></span>

  - <span data-ttu-id="b3429-115">Режимы установки:</span><span class="sxs-lookup"><span data-stu-id="b3429-115">Installation modes:</span></span>

    - <span data-ttu-id="b3429-116">[автоматическая установка](deployment-guide-for-developers.md#chaining_custom);</span><span class="sxs-lookup"><span data-stu-id="b3429-116">[Silent installation](deployment-guide-for-developers.md#chaining_custom)</span></span>

    - <span data-ttu-id="b3429-117">[отображение пользовательского интерфейса](deployment-guide-for-developers.md#chaining_default).</span><span class="sxs-lookup"><span data-stu-id="b3429-117">[Displaying a UI](deployment-guide-for-developers.md#chaining_default)</span></span>

  - [<span data-ttu-id="b3429-118">Уменьшение числа перезагрузок при установке платформы .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b3429-118">Reducing system restarts during .NET Framework 4.5 installations</span></span>](reducing-system-restarts.md)

  - [<span data-ttu-id="b3429-119">Устранение неполадок с заблокированными установками и удалениями .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b3429-119">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](../install/troubleshoot-blocked-installations-and-uninstallations.md)

- <span data-ttu-id="b3429-120">Развертывание .NET Framework с клиентским приложением (для разработчиков):</span><span class="sxs-lookup"><span data-stu-id="b3429-120">Deploying the .NET Framework with a client application (for developers):</span></span>

  - <span data-ttu-id="b3429-121">[Использование InstallShield](deployment-guide-for-developers.md#installshield-deployment) в проекте установки и развертывания.</span><span class="sxs-lookup"><span data-stu-id="b3429-121">[Using InstallShield](deployment-guide-for-developers.md#installshield-deployment) in a setup and deployment project</span></span>

  - <span data-ttu-id="b3429-122">[Использование приложения Visual Studio ClickOnce](deployment-guide-for-developers.md#clickonce-deployment).</span><span class="sxs-lookup"><span data-stu-id="b3429-122">[Using a Visual Studio ClickOnce application](deployment-guide-for-developers.md#clickonce-deployment)</span></span>

  - <span data-ttu-id="b3429-123">[Создание пакета установки WiX](deployment-guide-for-developers.md#wix).</span><span class="sxs-lookup"><span data-stu-id="b3429-123">[Creating a WiX installation package](deployment-guide-for-developers.md#wix)</span></span>

  - <span data-ttu-id="b3429-124">[Использование настраиваемого установщика](deployment-guide-for-developers.md#chaining).</span><span class="sxs-lookup"><span data-stu-id="b3429-124">[Using a custom installer](deployment-guide-for-developers.md#chaining)</span></span>

  - <span data-ttu-id="b3429-125">[Дополнительные сведения](deployment-guide-for-developers.md) для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="b3429-125">[Additional information](deployment-guide-for-developers.md) for developers</span></span>

- <span data-ttu-id="b3429-126">Развертывание .NET Framework (для изготовителей оборудования и администраторов):</span><span class="sxs-lookup"><span data-stu-id="b3429-126">Deploying the .NET Framework (for OEMs and administrators):</span></span>

  - <span data-ttu-id="b3429-127">[Комплект средств для развертывания и оценки Windows (ADK)](https://go.microsoft.com/fwlink/p/?LinkId=254976).</span><span class="sxs-lookup"><span data-stu-id="b3429-127">[Windows Assessment and Deployment Kit (ADK)](https://go.microsoft.com/fwlink/p/?LinkId=254976)</span></span>

  - <span data-ttu-id="b3429-128">[Руководство администратора](guide-for-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="b3429-128">[Administrator's guide](guide-for-administrators.md)</span></span>

<span data-ttu-id="b3429-129">**Обслуживание**</span><span class="sxs-lookup"><span data-stu-id="b3429-129">**Servicing**</span></span>

- <span data-ttu-id="b3429-130">См. общие сведения в [блоге по .NET Framework](https://devblogs.microsoft.com/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="b3429-130">For general information, see the [.NET Framework blog](https://devblogs.microsoft.com/dotnet/).</span></span>

- <span data-ttu-id="b3429-131">[Обнаружение версий](../migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="b3429-131">[Detecting versions](../migration-guide/how-to-determine-which-versions-are-installed.md)</span></span>

- <span data-ttu-id="b3429-132">[Обнаружение обновлений и пакетов обновления](../migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="b3429-132">[Detecting service packs and updates](../migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)</span></span>

## <a name="features-that-simplify-deployment"></a><span data-ttu-id="b3429-133">Возможности, упрощающие развертывание</span><span class="sxs-lookup"><span data-stu-id="b3429-133">Features That Simplify Deployment</span></span>

<span data-ttu-id="b3429-134">Платформа .NET Framework включает ряд функций, которые упрощают развертывание приложений.</span><span class="sxs-lookup"><span data-stu-id="b3429-134">The .NET Framework provides a number of basic features that make it easier to deploy your applications:</span></span>

- <span data-ttu-id="b3429-135">Изолированные приложения.</span><span class="sxs-lookup"><span data-stu-id="b3429-135">No-impact applications.</span></span>

     <span data-ttu-id="b3429-136">Эта функция обеспечивает изоляцию приложений и исключает конфликты библиотек DLL.</span><span class="sxs-lookup"><span data-stu-id="b3429-136">This feature provides application isolation and eliminates DLL conflicts.</span></span> <span data-ttu-id="b3429-137">По умолчанию компоненты не влияют на другие приложения.</span><span class="sxs-lookup"><span data-stu-id="b3429-137">By default, components do not affect other applications.</span></span>

- <span data-ttu-id="b3429-138">Частные компоненты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b3429-138">Private components by default.</span></span>

     <span data-ttu-id="b3429-139">По умолчанию компоненты развертываются в каталоге приложения и доступны только содержащему их приложению.</span><span class="sxs-lookup"><span data-stu-id="b3429-139">By default, components are deployed to the application directory and are visible only to the containing application.</span></span>

- <span data-ttu-id="b3429-140">Контролируемое совместное использование кода.</span><span class="sxs-lookup"><span data-stu-id="b3429-140">Controlled code sharing.</span></span>

     <span data-ttu-id="b3429-141">Для совместного использования кода необходимо явным образом предоставить к нему общий доступ — по умолчанию он не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="b3429-141">Code sharing requires you to explicitly make code available for sharing instead of being the default behavior.</span></span>

- <span data-ttu-id="b3429-142">Управление параллельными версиями.</span><span class="sxs-lookup"><span data-stu-id="b3429-142">Side-by-side versioning.</span></span>

     <span data-ttu-id="b3429-143">Одновременно могут сосуществовать несколько версий компонента или приложения. Вы можете выбрать используемые версии, а среда CLR применит политику управления версиями.</span><span class="sxs-lookup"><span data-stu-id="b3429-143">Multiple versions of a component or application can coexist, you can choose which versions to use, and the common language runtime enforces versioning policy.</span></span>

- <span data-ttu-id="b3429-144">Развертывание и репликация XCOPY.</span><span class="sxs-lookup"><span data-stu-id="b3429-144">XCOPY deployment and replication.</span></span>

     <span data-ttu-id="b3429-145">Самоописываемые и автономные компоненты и приложения можно развертывать без записей в реестре и зависимостей.</span><span class="sxs-lookup"><span data-stu-id="b3429-145">Self-described and self-contained components and applications can be deployed without registry entries or dependencies.</span></span>

- <span data-ttu-id="b3429-146">Оперативные обновления.</span><span class="sxs-lookup"><span data-stu-id="b3429-146">On-the-fly updates.</span></span>

     <span data-ttu-id="b3429-147">Администраторы могут использовать узлы, например ASP.NET, для обновления библиотек DLL программы даже на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="b3429-147">Administrators can use hosts, such as ASP.NET, to update program DLLs, even on remote computers.</span></span>

- <span data-ttu-id="b3429-148">Интеграция с установщиком Windows.</span><span class="sxs-lookup"><span data-stu-id="b3429-148">Integration with the Windows Installer.</span></span>

     <span data-ttu-id="b3429-149">При развертывании приложения доступны объявление, публикация, восстановление и установка по требованию.</span><span class="sxs-lookup"><span data-stu-id="b3429-149">Advertisement, publishing, repair, and install-on-demand are all available when deploying your application.</span></span>

- <span data-ttu-id="b3429-150">Корпоративное развертывание.</span><span class="sxs-lookup"><span data-stu-id="b3429-150">Enterprise deployment.</span></span>

     <span data-ttu-id="b3429-151">Эта функция упрощает распространение программного обеспечения, в том числе с помощью Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b3429-151">This feature provides easy software distribution, including using Active Directory.</span></span>

- <span data-ttu-id="b3429-152">Скачивание и кэширование.</span><span class="sxs-lookup"><span data-stu-id="b3429-152">Downloading and caching.</span></span>

     <span data-ttu-id="b3429-153">Добавочное скачивание позволяет сократить объем скачиваемых файлов. Кроме того, можно изолировать компоненты для использования только приложением, что позволяет снизить влияние развертывания на среду.</span><span class="sxs-lookup"><span data-stu-id="b3429-153">Incremental downloads keep downloads smaller, and components can be isolated for use only by the application for low-impact deployment.</span></span>

- <span data-ttu-id="b3429-154">Частично доверенный код.</span><span class="sxs-lookup"><span data-stu-id="b3429-154">Partially trusted code.</span></span>

     <span data-ttu-id="b3429-155">Идентификация производится на основе кода, а не на основе пользователя. Не выводятся диалоговые окна сертификата.</span><span class="sxs-lookup"><span data-stu-id="b3429-155">Identity is based on the code instead of the user, and no certificate dialog boxes appear.</span></span>

## <a name="packaging-and-distributing-net-framework-applications"></a><span data-ttu-id="b3429-156">Упаковка и распространение приложений .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b3429-156">Packaging and Distributing .NET Framework Applications</span></span>

<span data-ttu-id="b3429-157">Некоторые сведения о создании пакетов и развертывании для платформы .NET Framework приводятся в других разделах документации.</span><span class="sxs-lookup"><span data-stu-id="b3429-157">Some of the packaging and deployment information for the .NET Framework is described in other sections of the documentation.</span></span> <span data-ttu-id="b3429-158">В этих разделах содержатся сведения о самоописываемых блоках, называемых [сборками](../../standard/assembly/index.md), для которых не требуются записи в реестре, [сборках со строгими именами](../../standard/assembly/strong-named.md), которые гарантируют уникальность имен и предотвращают их подмену, и об [управлении версиями сборок](../../standard/assembly/versioning.md), которое решает многие проблемы, связанные с конфликтами библиотек DLL.</span><span class="sxs-lookup"><span data-stu-id="b3429-158">Those sections provide information about the self-describing units called [assemblies](../../standard/assembly/index.md), which require no registry entries, [strong-named assemblies](../../standard/assembly/strong-named.md), which ensure name uniqueness and prevent name spoofing, and [assembly versioning](../../standard/assembly/versioning.md), which addresses many of the problems associated with DLL conflicts.</span></span> <span data-ttu-id="b3429-159">В разделах ниже содержатся сведения об упаковке и распространении приложений .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3429-159">The following sections provide information about packaging and distributing .NET Framework applications.</span></span>

### <a name="packaging"></a><span data-ttu-id="b3429-160">Упаковка</span><span class="sxs-lookup"><span data-stu-id="b3429-160">Packaging</span></span>

<span data-ttu-id="b3429-161">Платформа .NET Framework предоставляет следующие способы упаковки приложений:</span><span class="sxs-lookup"><span data-stu-id="b3429-161">The .NET Framework provides the following options for packaging applications:</span></span>

- <span data-ttu-id="b3429-162">В виде отдельной сборки или коллекции сборок.</span><span class="sxs-lookup"><span data-stu-id="b3429-162">As a single assembly or as a collection of assemblies.</span></span>

     <span data-ttu-id="b3429-163">В этом варианте DLL- или EXE-файлы используются в том виде, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="b3429-163">With this option, you simply use the .dll or .exe files as they were built.</span></span>

- <span data-ttu-id="b3429-164">В виде CAB-файлов.</span><span class="sxs-lookup"><span data-stu-id="b3429-164">As cabinet (CAB) files.</span></span>

     <span data-ttu-id="b3429-165">В этом варианте файлы сжимаются в CAB-файлы, чтобы распространение или скачивание занимало меньше времени.</span><span class="sxs-lookup"><span data-stu-id="b3429-165">With this option, you compress files into .cab files to make distribution or download less time consuming.</span></span>

- <span data-ttu-id="b3429-166">В виде пакета установщика Windows или в других форматах установщика.</span><span class="sxs-lookup"><span data-stu-id="b3429-166">As a Windows Installer package or in other installer formats.</span></span>

     <span data-ttu-id="b3429-167">В этом случае вы создаете MSI-файлы для использования с установщиком Windows или пакет приложения для использования с другими установщиками.</span><span class="sxs-lookup"><span data-stu-id="b3429-167">With this option, you create .msi files for use with the Windows Installer, or you package your application for use with some other installer.</span></span>

### <a name="distribution"></a><span data-ttu-id="b3429-168">Распределение</span><span class="sxs-lookup"><span data-stu-id="b3429-168">Distribution</span></span>

<span data-ttu-id="b3429-169">Платформа .NET Framework предоставляет следующие варианты распространения приложений.</span><span class="sxs-lookup"><span data-stu-id="b3429-169">The .NET Framework provides the following options for distributing applications:</span></span>

- <span data-ttu-id="b3429-170">С помощью XCOPY или FTP.</span><span class="sxs-lookup"><span data-stu-id="b3429-170">Use XCOPY or FTP.</span></span>

     <span data-ttu-id="b3429-171">Так как приложения среды CLR являются самоописываемыми и не требуют записей в реестре, вы можете использовать XCOPY или FTP, чтобы просто скопировать приложение в соответствующий каталог.</span><span class="sxs-lookup"><span data-stu-id="b3429-171">Because common language runtime applications are self-describing and require no registry entries, you can use XCOPY or FTP to simply copy the application to an appropriate directory.</span></span> <span data-ttu-id="b3429-172">Затем приложение можно будет запустить из этого каталога.</span><span class="sxs-lookup"><span data-stu-id="b3429-172">The application can then be run from that directory.</span></span>

- <span data-ttu-id="b3429-173">С помощью скачивания кода.</span><span class="sxs-lookup"><span data-stu-id="b3429-173">Use code download.</span></span>

     <span data-ttu-id="b3429-174">Если приложение распространяется через Интернет или корпоративную интрасеть, можно просто скачать код на компьютер и запустить его.</span><span class="sxs-lookup"><span data-stu-id="b3429-174">If you are distributing your application over the Internet or through a corporate intranet, you can simply download the code to a computer and run the application there.</span></span>

- <span data-ttu-id="b3429-175">С помощью программы установки, например установщика Windows версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="b3429-175">Use an installer program such as Windows Installer 2.0.</span></span>

     <span data-ttu-id="b3429-176">Установщик Windows версии 2.0 позволяет устанавливать, восстанавливать и удалять сборки .NET Framework в глобальном кэше сборок и в личных каталогах.</span><span class="sxs-lookup"><span data-stu-id="b3429-176">Windows Installer 2.0 can install, repair, or remove .NET Framework assemblies in the global assembly cache and in private directories.</span></span>

### <a name="installation-location"></a><span data-ttu-id="b3429-177">Расположение установки</span><span class="sxs-lookup"><span data-stu-id="b3429-177">Installation Location</span></span>

<span data-ttu-id="b3429-178">Сведения о том, как выбрать место для развертывания сборок приложения таким образом, чтобы их могла найти среда выполнения, см. в статье [Обнаружение сборок в среде выполнения](how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="b3429-178">To determine where to deploy your application's assemblies so they can be found by the runtime, see [How the Runtime Locates Assemblies](how-the-runtime-locates-assemblies.md).</span></span>

<span data-ttu-id="b3429-179">На выбор способа развертывания приложения могут также влиять соображения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b3429-179">Security considerations can also affect how you deploy your application.</span></span> <span data-ttu-id="b3429-180">Разрешения безопасности предоставляются управляемому коду в соответствии с его расположением.</span><span class="sxs-lookup"><span data-stu-id="b3429-180">Security permissions are granted to managed code according to where the code is located.</span></span> <span data-ttu-id="b3429-181">Развертывание приложения или компонента в расположении, где они получают низкий уровень доверия, например в Интернете, ограничивает возможности приложения или компонента.</span><span class="sxs-lookup"><span data-stu-id="b3429-181">Deploying an application or component to a location where it receives little trust, such as the Internet, limits what the application or component can do.</span></span> <span data-ttu-id="b3429-182">Дополнительные сведения о развертывании и аспектах безопасности см. в статье [Основы управления доступом для кода](../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="b3429-182">For more information about deployment and security considerations, see [Code Access Security Basics](../misc/code-access-security-basics.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b3429-183">См. также</span><span class="sxs-lookup"><span data-stu-id="b3429-183">Related Topics</span></span>

|<span data-ttu-id="b3429-184">Заголовок</span><span class="sxs-lookup"><span data-stu-id="b3429-184">Title</span></span>|<span data-ttu-id="b3429-185">Описание</span><span class="sxs-lookup"><span data-stu-id="b3429-185">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="b3429-186">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="b3429-186">How the Runtime Locates Assemblies</span></span>](how-the-runtime-locates-assemblies.md)|<span data-ttu-id="b3429-187">Описывается то, как среда CLR определяет, какую сборку следует использовать для выполнения запроса привязки.</span><span class="sxs-lookup"><span data-stu-id="b3429-187">Describes how the common language runtime determines which assembly to use to fulfill a binding request.</span></span>|
|[<span data-ttu-id="b3429-188">Рекомендации для загрузки сборок</span><span class="sxs-lookup"><span data-stu-id="b3429-188">Best Practices for Assembly Loading</span></span>](best-practices-for-assembly-loading.md)|<span data-ttu-id="b3429-189">Описывается, как избежать проблем с идентификацией типов, которые могут привести к возникновению исключений <xref:System.InvalidCastException> и <xref:System.MissingMethodException> и других ошибок.</span><span class="sxs-lookup"><span data-stu-id="b3429-189">Discusses ways to avoid problems of type identity that can lead to <xref:System.InvalidCastException>, <xref:System.MissingMethodException>, and other errors.</span></span>|
|[<span data-ttu-id="b3429-190">Уменьшение числа перезагрузок при установке платформы .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b3429-190">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](reducing-system-restarts.md)|<span data-ttu-id="b3429-191">Описывается диспетчер перезапуска, который по возможности предотвращает перезагрузки, и его преимущества для приложений, устанавливающих платформу .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3429-191">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>|
|[<span data-ttu-id="b3429-192">Руководство по развертыванию для администраторов</span><span class="sxs-lookup"><span data-stu-id="b3429-192">Deployment Guide for Administrators</span></span>](guide-for-administrators.md)|<span data-ttu-id="b3429-193">Инструкции для системного администратора по развертыванию платформы .NET Framework и ее системных зависимостей в сети с помощью Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b3429-193">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span>|
|[<span data-ttu-id="b3429-194">Руководство по развертыванию для разработчиков</span><span class="sxs-lookup"><span data-stu-id="b3429-194">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)|<span data-ttu-id="b3429-195">Описываются способы установки .NET Framework на компьютеры пользователей вместе с приложениями.</span><span class="sxs-lookup"><span data-stu-id="b3429-195">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>|
|[<span data-ttu-id="b3429-196">Развертывание приложений, служб и компонентов</span><span class="sxs-lookup"><span data-stu-id="b3429-196">Deploying Applications, Services, and Components</span></span>](/visualstudio/deployment/deploying-applications-services-and-components)|<span data-ttu-id="b3429-197">Рассматриваются варианты развертывания в Visual Studio, включая инструкции по публикации приложения с помощью технологии ClickOnce и установщика Windows.</span><span class="sxs-lookup"><span data-stu-id="b3429-197">Discusses deployment options in Visual Studio, including instructions for publishing an application using the ClickOnce and Windows Installer technologies.</span></span>|
|[<span data-ttu-id="b3429-198">Публикация приложений ClickOnce</span><span class="sxs-lookup"><span data-stu-id="b3429-198">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)|<span data-ttu-id="b3429-199">Описывается, как упаковать приложение Windows Forms и развернуть его на клиентских компьютерах в сети с помощью технологии ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="b3429-199">Describes how to package a Windows Forms application and deploy it with ClickOnce to client computers on a network.</span></span>|
|[<span data-ttu-id="b3429-200">Упаковка и развертывание ресурсов</span><span class="sxs-lookup"><span data-stu-id="b3429-200">Packaging and Deploying Resources</span></span>](../resources/packaging-and-deploying-resources-in-desktop-apps.md)|<span data-ttu-id="b3429-201">Описывается модель "звезда", которую платформа .NET Framework использует для упаковки и развертывания ресурсов; рассматриваются соглашения об именовании ресурсов, процесс перехода на резервные ресурсы и альтернативные способы упаковки.</span><span class="sxs-lookup"><span data-stu-id="b3429-201">Describes the hub and spoke model that the .NET Framework uses to package and deploy resources; covers resource naming conventions, fallback process, and packaging alternatives.</span></span>|
|[<span data-ttu-id="b3429-202">Развертывание приложения взаимодействия</span><span class="sxs-lookup"><span data-stu-id="b3429-202">Deploying an Interop Application</span></span>](../interop/deploying-an-interop-application.md)|<span data-ttu-id="b3429-203">Описывается поставка и установка приложений взаимодействия, которые обычно включают клиентскую сборку .NET Framework, одну или несколько сборок взаимодействия (представляющих различные библиотеки типов COM) и один или несколько зарегистрированных COM-компонентов.</span><span class="sxs-lookup"><span data-stu-id="b3429-203">Explains how to ship and install interop applications, which typically include a .NET Framework client assembly, one or more interop assemblies representing distinct COM type libraries, and one or more registered COM components.</span></span>|
|[<span data-ttu-id="b3429-204">Практическое руководство. Получение хода выполнения установщика .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b3429-204">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](how-to-get-progress-from-the-dotnet-installer.md)|<span data-ttu-id="b3429-205">Описывается автоматический запуск и отслеживание процесса установки .NET Framework с выводом собственного представления хода выполнения установки.</span><span class="sxs-lookup"><span data-stu-id="b3429-205">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>|

## <a name="see-also"></a><span data-ttu-id="b3429-206">См. также</span><span class="sxs-lookup"><span data-stu-id="b3429-206">See also</span></span>

- [<span data-ttu-id="b3429-207">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="b3429-207">Development Guide</span></span>](../development-guide.md)

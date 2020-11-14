---
title: Глобализация и ICU
ms.date: 05/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- globalization [.NET], about globalization
- global applications, globalization
- international applications [.NET], globalization
- world-ready applications, globalization
- application development [.NET], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: e0ca78871d1ddf851148096c8c6cfd10076763ab
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400883"
---
# <a name="net-globalization-and-icu"></a><span data-ttu-id="b6aa1-102">Глобализация .NET и ICU</span><span class="sxs-lookup"><span data-stu-id="b6aa1-102">.NET globalization and ICU</span></span>

<span data-ttu-id="b6aa1-103">В прошлом на разных платформах API-интерфейсы глобализации .NET использовали разные базовые библиотеки.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-103">In the past, the .NET globalization APIs used different underlying libraries on different platforms.</span></span> <span data-ttu-id="b6aa1-104">В Unix API-интерфейсы использовали [международные компоненты для Юникода (ICU)](http://site.icu-project.org/home), а в Windows — [многоязыковую поддержку (NLS)](/windows/win32/intl/national-language-support).</span><span class="sxs-lookup"><span data-stu-id="b6aa1-104">On Unix, the APIs used [International Components for Unicode (ICU)](http://site.icu-project.org/home), and on Windows, they used [National Language Support (NLS)](/windows/win32/intl/national-language-support).</span></span> <span data-ttu-id="b6aa1-105">Это привело к некоторым различиям в поведении API-интерфейсов глобализации при запуске приложений на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-105">This resulted in some behavioral differences in a handful of globalization APIs when running applications on different platforms.</span></span> <span data-ttu-id="b6aa1-106">Различия в работе были очевидны в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="b6aa1-106">Behavior differences were evident in these areas:</span></span>

- <span data-ttu-id="b6aa1-107">Региональные параметры и данные языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="b6aa1-107">Cultures and culture data</span></span>
- <span data-ttu-id="b6aa1-108">Регистр строк</span><span class="sxs-lookup"><span data-stu-id="b6aa1-108">String casing</span></span>
- <span data-ttu-id="b6aa1-109">Сортировка и поиск строк</span><span class="sxs-lookup"><span data-stu-id="b6aa1-109">String sorting and searching</span></span>
- <span data-ttu-id="b6aa1-110">Сортировка ключей</span><span class="sxs-lookup"><span data-stu-id="b6aa1-110">Sort keys</span></span>
- <span data-ttu-id="b6aa1-111">Нормализация строк</span><span class="sxs-lookup"><span data-stu-id="b6aa1-111">String normalization</span></span>
- <span data-ttu-id="b6aa1-112">Поддержка международных доменных имен (IDN)</span><span class="sxs-lookup"><span data-stu-id="b6aa1-112">Internationalized Domain Names (IDN) support</span></span>
- <span data-ttu-id="b6aa1-113">Отображаемое имя часового пояса в Linux</span><span class="sxs-lookup"><span data-stu-id="b6aa1-113">Time zone display name on Linux</span></span>

<span data-ttu-id="b6aa1-114">Начиная с .NET 5.0 разработчики получили больший контроль над тем, какая базовая библиотека используется, что позволяет обеспечить единообразную работу приложений на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-114">Starting with .NET 5.0, developers have more control over which underlying library is used, enabling applications to avoid differences across platforms.</span></span>

## <a name="icu-on-windows"></a><span data-ttu-id="b6aa1-115">ICU в Windows</span><span class="sxs-lookup"><span data-stu-id="b6aa1-115">ICU on Windows</span></span>

<span data-ttu-id="b6aa1-116">В состав ОС Windows 10 с майским обновлением 2019 г. и более поздних версий включена библиотека [ICU. dll](/windows/win32/intl/international-components-for-unicode--icu-), а .NET 5.0 и более поздних версий компоненты ICU используются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-116">Windows 10 May 2019 Update and later versions include [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) as part of the OS, and .NET 5.0 and later versions use ICU by default.</span></span> <span data-ttu-id="b6aa1-117">При работе в Windows, NET 5.0 и более поздних версий попробуйте загрузить `icu.dll` и, если она доступна, используйте ее для реализации глобализации.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-117">When running on Windows, .NET 5.0 and later versions try to load `icu.dll` and, if it's available, use it for the globalization implementation.</span></span> <span data-ttu-id="b6aa1-118">Если библиотека ICU отсутствует или не загружена (например, при работе в более старых версиях Windows), платформа .NET 5.0 и более поздних версий переходит на реализации на основе NLS.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-118">If the ICU library can't be found or loaded, such as when running on older versions of Windows, .NET 5.0 and later versions fall back to the NLS-based implementation.</span></span>

> [!NOTE]
> <span data-ttu-id="b6aa1-119">Даже при использовании ICU элементы `CurrentCulture`, `CurrentUICulture` и `CurrentRegion` по-прежнему используют API операционной системы Windows, чтобы применить параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-119">Even when using ICU, the `CurrentCulture`, `CurrentUICulture`, and `CurrentRegion` members still use Windows operating system APIs to honor user settings.</span></span>

### <a name="use-nls-instead-of-icu"></a><span data-ttu-id="b6aa1-120">Использование NLS вместо ICU</span><span class="sxs-lookup"><span data-stu-id="b6aa1-120">Use NLS instead of ICU</span></span>

<span data-ttu-id="b6aa1-121">Использование ICU вместо NLS может привести к различиям в работе некоторых операций, связанных с глобализацией.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-121">Using ICU instead of NLS may result in behavioral differences with some globalization-related operations.</span></span> <span data-ttu-id="b6aa1-122">Чтобы вернуться к использованию NLS, разработчик может отказаться от реализации ICU.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-122">To revert back to using NLS, a developer can opt out of the ICU implementation.</span></span> <span data-ttu-id="b6aa1-123">Приложения могут включать режим NLS одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="b6aa1-123">Applications can enable NLS mode in any of the following ways:</span></span>

- <span data-ttu-id="b6aa1-124">В файле проекта:</span><span class="sxs-lookup"><span data-stu-id="b6aa1-124">In the project file:</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="b6aa1-125">В файле `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="b6aa1-125">In the `runtimeconfig.json` file:</span></span>

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.UseNls": true
        }
    }
  }
  ```

- <span data-ttu-id="b6aa1-126">Путем присвоения переменной среды `DOTNET_SYSTEM_GLOBALIZATION_USENLS` значения `true` или `1`.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-126">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_USENLS` to the value `true` or `1`.</span></span>

> [!NOTE]
> <span data-ttu-id="b6aa1-127">Значение, заданное в проекте или файле `runtimeconfig.json`, имеет приоритет над переменной среды.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-127">A value set in the project or in the `runtimeconfig.json` file takes precedence over the environment variable.</span></span>

<span data-ttu-id="b6aa1-128">Дополнительные сведения см. в статье [Настройки конфигурации среды выполнения](../../core/run-time-config/globalization.md#nls).</span><span class="sxs-lookup"><span data-stu-id="b6aa1-128">For more information, see [Run-time config settings](../../core/run-time-config/globalization.md#nls).</span></span>

## <a name="app-local-icu"></a><span data-ttu-id="b6aa1-129">ICU с параметром app-local</span><span class="sxs-lookup"><span data-stu-id="b6aa1-129">App-local ICU</span></span>

<span data-ttu-id="b6aa1-130">Каждый выпуск ICU включает исправления ошибок, а также обновленные данные репозитория данных общего языкового стандарта (CLDR), которые описывают языки мира.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-130">Each release of ICU may bring with it bug fixes as well as updated Common Locale Data Repository (CLDR) data that describes the world's languages.</span></span> <span data-ttu-id="b6aa1-131">Использование разных версий ICU может незначительно повлиять на работу приложения, когда дело доходит до операций, связанных с глобализацией.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-131">Moving between versions of ICU can subtly impact app behavior when it comes to globalization-related operations.</span></span> <span data-ttu-id="b6aa1-132">Чтобы помочь разработчикам приложений обеспечить согласованность всех развертываний, в .NET 5.0 и более поздних версиях приложения в Windows и Unix могут использовать собственную копию ICU.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-132">To help application developers ensure consistency across all deployments, .NET 5.0 and later versions enable apps on both Windows and Unix to carry and use their own copy of ICU.</span></span>

<span data-ttu-id="b6aa1-133">Приложения могут применить режим реализации ICU с параметром app-local одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-133">Applications can opt in to an app-local ICU implementation mode in any of the following ways:</span></span>

- <span data-ttu-id="b6aa1-134">В файле проекта:</span><span class="sxs-lookup"><span data-stu-id="b6aa1-134">In  the project file:</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
  </ItemGroup>
  ```

- <span data-ttu-id="b6aa1-135">В файле `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="b6aa1-135">In the `runtimeconfig.json` file:</span></span>

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
       }
    }
  }
  ```

- <span data-ttu-id="b6aa1-136">Путем присвоения переменной среды `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` значения `<suffix>:<version>` или `<version>`.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-136">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` to the value `<suffix>:<version>` or `<version>`.</span></span>

  <span data-ttu-id="b6aa1-137">`<suffix>`: Необязательный суффикс длиной менее 36 символов в соответствии с публичными соглашениями об упаковке ICU.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-137">`<suffix>`: Optional suffix of fewer than 36 characters in length, following the public ICU packaging conventions.</span></span> <span data-ttu-id="b6aa1-138">При создании настраиваемых ICU можно указать, чтобы имена библиотек и имена экспортированных символов содержали суффикс (например, `libicuucmyapp`, где `myapp` является суффиксом).</span><span class="sxs-lookup"><span data-stu-id="b6aa1-138">When building a custom ICU, you can customize it to produce the lib names and exported symbol names to contain a suffix, for example, `libicuucmyapp`, where `myapp` is the suffix.</span></span>

  <span data-ttu-id="b6aa1-139">`<version>`. Допустимая версия ICU (например, 67.1).</span><span class="sxs-lookup"><span data-stu-id="b6aa1-139">`<version>`: A valid ICU version, for example, 67.1.</span></span> <span data-ttu-id="b6aa1-140">Эта версия используется для загрузки двоичных файлов и получения экспортированных символов.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-140">This version is used to load the binaries and to get the exported symbols.</span></span>

<span data-ttu-id="b6aa1-141">Чтобы загрузить ICU, когда задан параметр app-local, .NET использует метод <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType>, который проверяет несколько путей.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-141">To load ICU when the app-local switch is set, .NET uses the <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> method, which probes multiple paths.</span></span> <span data-ttu-id="b6aa1-142">Сначала метод пытается найти библиотеку в свойстве `NATIVE_DLL_SEARCH_DIRECTORIES`, которое создается узлом .NET на основе файла `deps.json` для приложения.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-142">The method first tries to find the library in the `NATIVE_DLL_SEARCH_DIRECTORIES` property, which is created by the dotnet host based on the `deps.json` file for the app.</span></span> <span data-ttu-id="b6aa1-143">Дополнительные сведения см. в разделе [Проверка по умолчанию](../../core/dependency-loading/default-probing.md).</span><span class="sxs-lookup"><span data-stu-id="b6aa1-143">For more information, see [Default probing](../../core/dependency-loading/default-probing.md).</span></span>

<span data-ttu-id="b6aa1-144">В случае с автономными приложениями пользователю не требуется выполнять никаких особых действий, кроме помещения ICU в каталог приложения (для автономных приложений по умолчанию используется рабочий каталог `NATIVE_DLL_SEARCH_DIRECTORIES`).</span><span class="sxs-lookup"><span data-stu-id="b6aa1-144">For self-contained apps, no special action is required by the user, other than making sure ICU is in the app directory (for self-contained apps, the working directory defaults to `NATIVE_DLL_SEARCH_DIRECTORIES`).</span></span>

<span data-ttu-id="b6aa1-145">Если вы используете ICU через пакет NuGet, это сработает в приложениях, зависящих от платформы.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-145">If you're consuming ICU via a NuGet package, this works in framework-dependent applications.</span></span> <span data-ttu-id="b6aa1-146">NuGet разрешает собственные активы и включает их в файл `deps.json` и в выходной каталог для приложения в каталоге `runtimes`.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-146">NuGet resolves the native assets and includes them in the `deps.json` file and in the output directory for the application under the `runtimes` directory.</span></span> <span data-ttu-id="b6aa1-147">.NET загружает его отсюда.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-147">.NET loads it from there.</span></span>

<span data-ttu-id="b6aa1-148">Для приложений, зависящих от платформы (не автономных), где ICU используется из локальной сборки, необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-148">For framework-dependent apps (not self contained) where ICU is consumed from a local build, you must take additional steps.</span></span> <span data-ttu-id="b6aa1-149">В пакете SDK для .NET пока еще нет функции для включения "свободных" собственных двоичных файлов в `deps.json` (см. сведения об [этой](https://github.com/dotnet/sdk/issues/11373)проблеме с пакетом SDK).</span><span class="sxs-lookup"><span data-stu-id="b6aa1-149">The .NET SDK doesn't yet have a feature for "loose" native binaries to be incorporated into `deps.json` (see [this SDK issue](https://github.com/dotnet/sdk/issues/11373)).</span></span> <span data-ttu-id="b6aa1-150">Это можно сделать, добавив дополнительные сведения в файл проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-150">Instead, you can enable this by adding additional information into the application's project file.</span></span> <span data-ttu-id="b6aa1-151">Пример:</span><span class="sxs-lookup"><span data-stu-id="b6aa1-151">For example:</span></span>

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

<span data-ttu-id="b6aa1-152">Это необходимо сделать для всех двоичных файлов ICU для поддерживаемых сред выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-152">This must be done for all the ICU binaries for the supported runtimes.</span></span> <span data-ttu-id="b6aa1-153">Кроме того, метаданные `NuGetPackageId` в группе элементов `RuntimeTargetsCopyLocalItems` должны соответствовать пакету NuGet, на который фактически ссылается проект.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-153">Also, the `NuGetPackageId` metadata in the `RuntimeTargetsCopyLocalItems` item group needs to match a NuGet package that the project actually references.</span></span>

### <a name="macos-behavior"></a><span data-ttu-id="b6aa1-154">Поведение в macOS</span><span class="sxs-lookup"><span data-stu-id="b6aa1-154">macOS behavior</span></span>

<span data-ttu-id="b6aa1-155">`macOS` разрешает зависимые динамические библиотеки из команд загрузки, указанных в файле `match-o`, по-другому, чем загрузчик Linux.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-155">`macOS` has a different behavior for resolving dependent dynamic libraries from the load commands specified in the `match-o` file than the Linux loader.</span></span> <span data-ttu-id="b6aa1-156">В загрузчике Linux .NET пробует использовать `libicudata`, `libicuuc` и `libicui18n` (в этом порядке) для обеспечения соответствия графу зависимостей ICU.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-156">In the Linux loader, .NET can try `libicudata`, `libicuuc`, and `libicui18n` (in that order) to satisfy ICU dependency graph.</span></span> <span data-ttu-id="b6aa1-157">Однако в macOS это не работает.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-157">However, on macOS, this doesn't work.</span></span> <span data-ttu-id="b6aa1-158">При создании ICU в macOS вы по умолчанию получаете динамическую библиотеку с помощью этих команд загрузки в `libicuuc`.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-158">When building ICU on macOS, you, by default, get a dynamic library with these load commands in `libicuuc`.</span></span> <span data-ttu-id="b6aa1-159">Фрагмент кода приведен ниже.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-159">The following snippet shows an example.</span></span>

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

<span data-ttu-id="b6aa1-160">Эти команды просто ссылаются на имена зависимых библиотек для других компонентов ICU.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-160">These commands just reference the name of the dependent libraries for the other components of ICU.</span></span> <span data-ttu-id="b6aa1-161">Загрузчик выполняет поиск, следуя соглашениям `dlopen`, которые подразумевают использование этих библиотек в системных каталогах или задание переменных среды `LD_LIBRARY_PATH` или наличие ICU в каталоге уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-161">The loader performs the search following the `dlopen` conventions, which involves having these libraries in the system directories or setting the `LD_LIBRARY_PATH` env vars, or having ICU at the app-level directory.</span></span> <span data-ttu-id="b6aa1-162">Если не удается задать `LD_LIBRARY_PATH` или убедиться, что двоичные файлы ICU находятся в каталоге уровня приложения, необходимо выполнить некоторую дополнительную работу.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-162">If you can't set `LD_LIBRARY_PATH` or ensure that ICU binaries are at the app-level directory, you will need to do some extra work.</span></span>

<span data-ttu-id="b6aa1-163">Существует несколько директив для загрузчика, таких как `@loader_path`, которые указывают загрузчику выполнять поиск этой зависимости в том же каталоге, в котором находится двоичный файл с этой командой загрузки.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-163">There are some directives for the loader, like `@loader_path`, which tell the loader to search for that dependency in the same directory as the binary with that load command.</span></span> <span data-ttu-id="b6aa1-164">Это достигается двумя способами.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-164">There are two ways to achieve this:</span></span>

- `install_name_tool -change`

  <span data-ttu-id="b6aa1-165">Выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="b6aa1-165">Run the following commands:</span></span>

  ```bash
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
  install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
  ```

- <span data-ttu-id="b6aa1-166">Исправление ICU таким образом, чтобы создавались имена установки с помощью `@loader_path`</span><span class="sxs-lookup"><span data-stu-id="b6aa1-166">Patch ICU to produce the install names with `@loader_path`</span></span>

  <span data-ttu-id="b6aa1-167">Перед выполнением автонастройки (`./runConfigureICU`) измените [эти строки](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) на следующие:</span><span class="sxs-lookup"><span data-stu-id="b6aa1-167">Before running autoconf (`./runConfigureICU`), change [these lines](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) to:</span></span>

  ```
  LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
  ```

## <a name="icu-on-webassembly"></a><span data-ttu-id="b6aa1-168">ICU в WebAssembly</span><span class="sxs-lookup"><span data-stu-id="b6aa1-168">ICU on WebAssembly</span></span>

<span data-ttu-id="b6aa1-169">Доступна версия ICU, специально предназначенная для рабочих нагрузок WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-169">A version of ICU is available that's specifically for WebAssembly workloads.</span></span> <span data-ttu-id="b6aa1-170">Она обеспечивает совместимость глобализации с профилями рабочих столов.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-170">This version provides globalization compatibility with desktop profiles.</span></span> <span data-ttu-id="b6aa1-171">Чтобы уменьшить размер файла данных ICU с 24 МБ до 1,4 МБ (или около 0,3 МБ при сжатии с помощью Brotli), к этой рабочей нагрузке применяется ряд ограничений.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-171">To reduce the ICU data file size from 24 MB to 1.4 MB (or ~0.3 MB if compressed with Brotli), this workload has a handful of limitations.</span></span>

<span data-ttu-id="b6aa1-172">Не поддерживаются следующие API:</span><span class="sxs-lookup"><span data-stu-id="b6aa1-172">The following APIs are not supported:</span></span>

- <xref:System.Globalization.CultureInfo.EnglishName?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.NativeName?displayProperty=nameWithType>
- <xref:System.Globalization.DateTimeFormatInfo.NativeCalendarName?displayProperty=nameWithType>
- <xref:System.Globalization.RegionInfo.NativeName?displayProperty=nameWithType>

<span data-ttu-id="b6aa1-173">Следующие API поддерживаются с ограничениями:</span><span class="sxs-lookup"><span data-stu-id="b6aa1-173">The following APIs are supported with limitations:</span></span>

- <span data-ttu-id="b6aa1-174"><xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> и <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> не поддерживают редко используемые формы <xref:System.Text.NormalizationForm.FormKC> и <xref:System.Text.NormalizationForm.FormKD>.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-174"><xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> and <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> don't support the rarely used <xref:System.Text.NormalizationForm.FormKC> and <xref:System.Text.NormalizationForm.FormKD> forms.</span></span>
- <span data-ttu-id="b6aa1-175"><xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> возвращает то же значение, что и <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6aa1-175"><xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> returns the same value as <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b6aa1-176">Кроме того, список поддерживаемых языковых стандартов можно найти в [репозитории dotnet/icu](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).</span><span class="sxs-lookup"><span data-stu-id="b6aa1-176">In addition, a list of supported locales can be found on the [dotnet/icu repo](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).</span></span>

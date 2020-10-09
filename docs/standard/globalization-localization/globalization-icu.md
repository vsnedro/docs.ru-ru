---
title: Глобализация и ICU
ms.date: 05/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- globalization [.NET Framework], about globalization
- global applications, globalization
- international applications [.NET Framework], globalization
- world-ready applications, globalization
- application development [.NET Framework], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: 60533fbb215ffe8baba7e2d200faa1c4937294b9
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654885"
---
# <a name="net-globalization-and-icu"></a>Глобализация .NET и ICU

В прошлом на разных платформах API-интерфейсы глобализации .NET использовали разные базовые библиотеки. В Unix API-интерфейсы использовали [международные компоненты для Юникода (ICU)](http://site.icu-project.org/home), а в Windows — [многоязыковую поддержку (NLS)](/windows/win32/intl/national-language-support). Это привело к некоторым различиям в поведении API-интерфейсов глобализации при запуске приложений на разных платформах. Различия в работе были очевидны в следующих областях:

- Региональные параметры и данные языка и региональных параметров
- Регистр строк
- Сортировка и поиск строк
- Сортировка ключей
- Нормализация строк
- Поддержка международных доменных имен (IDN)
- Отображаемое имя часового пояса в Linux

Начиная с .NET 5.0 разработчики получили больший контроль над тем, какая базовая библиотека используется, что позволяет обеспечить единообразную работу приложений на разных платформах.

## <a name="icu-on-windows"></a>ICU в Windows

В состав ОС Windows 10 с майским обновлением 2019 г. и более поздних версий включена библиотека [ICU. dll](/windows/win32/intl/international-components-for-unicode--icu-), а .NET 5.0 и более поздних версий компоненты ICU используются по умолчанию. При работе в Windows платформа .NET 5.0 и более поздних версий попробуйте загрузить `icu.dll` и, если она доступна, используйте ее для реализации глобализации.  Если эта библиотека отсутствует или не загружена (например, при работе в более старых версиях Windows), платформа .NET 5.0 и более поздних версий переходит на реализации на основе NLS.

> [!NOTE]
> Даже при использовании ICU элементы `CurrentCulture`, `CurrentUICulture` и `CurrentRegion` по-прежнему используют API операционной системы Windows, чтобы применить параметры пользователя.

### <a name="using-nls-instead-of-icu"></a>Использование NLS вместо ICU

Использование ICU вместо NLS может привести к различиям в работе некоторых операций, связанных с глобализацией. Чтобы вернуться к использованию NLS, разработчик может отказаться от реализации ICU. Приложения могут включать режим NLS одним из следующих способов:

- В файле проекта:

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
</ItemGroup>
```

- В файле `runtimeconfig.json`:

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.UseNls": true
      }
  }
}
```

- Путем присвоения переменной среды `DOTNET_SYSTEM_GLOBALIZATION_USENLS` значения `true` или `1`.

> [!NOTE]
> Значение, заданное в проекте или файле `runtimeconfig.json`, имеет приоритет над переменной среды.

Дополнительные сведения см. в статье [Настройки конфигурации среды выполнения](../../core/run-time-config/globalization.md#nls).

## <a name="app-local-icu"></a>ICU с параметром app-local

Каждый выпуск ICU включает исправления ошибок, а также обновленные данные репозитория данных общего языкового стандарта (CLDR), которые описывают языки мира. Использование разных версий ICU может незначительно повлиять на работу приложения, когда дело доходит до операций, связанных с глобализацией.  Чтобы помочь разработчикам приложений обеспечить согласованность всех развертываний, в .NET 5.0 и более поздних версиях приложения в Windows и Unix могут использовать собственную копию ICU.

Приложения могут применить режим реализации ICU с параметром app-local одним из следующих способов.

- В файле проекта:

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
</ItemGroup>
```

- В файле `runtimeconfig.json`:

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
      }
  }
}
```

- Путем присвоения переменной среды `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` значения `<suffix>:<version>` или `<version>`.

`<suffix>`. Необязательный суффикс длиной менее 36 символов в соответствии с публичными соглашениями об упаковке ICU. При создании настраиваемых ICU можно указать, чтобы имена библиотек и имена экспортированных символов содержали суффикс (например, `libicuucmyapp`, где `myapp` является суффиксом).

`<version>`. Допустимая версия ICU (например, 67.1). Эта версия используется для загрузки двоичных файлов и получения экспортированных символов.

Чтобы загрузить ICU, когда задан параметр app-local, .NET использует метод <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType>, который проверяет несколько путей. Сначала метод пытается найти библиотеку в свойстве `NATIVE_DLL_SEARCH_DIRECTORIES`, которое создается узлом .NET на основе файла `deps.json` для приложения. Дополнительные сведения см. в разделе [Проверка по умолчанию](../../core/dependency-loading/default-probing.md).

В случае с автономными приложениями пользователю не требуется выполнять никаких особых действий, кроме помещения ICU в каталог приложения (для автономных приложений по умолчанию используется рабочий каталог `NATIVE_DLL_SEARCH_DIRECTORIES`).

Если вы используете ICU через пакет NuGet, это сработает в приложениях, зависящих от платформы. NuGet разрешает собственные активы и включает их в файл `deps.json` и в выходной каталог для приложения в каталоге `runtimes`. .NET загружает его отсюда.

Для приложений, зависящих от платформы (не автономных), где ICU используется из локальной сборки, необходимо выполнить дополнительные действия. В пакете SDK для .NET пока еще нет функции для включения "свободных" собственных двоичных файлов в `deps.json` (см. сведения об [этой](https://github.com/dotnet/sdk/issues/11373)проблеме с пакетом SDK). Это можно сделать, добавив дополнительные сведения в файл проекта приложения. Пример:

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

Это необходимо сделать для всех двоичных файлов ICU для поддерживаемых сред выполнения. Кроме того, метаданные `NuGetPackageId` в группе элементов `RuntimeTargetsCopyLocalItems` должны соответствовать пакету NuGet, на который фактически ссылается проект.

### <a name="macos-behavior"></a>Поведение в macOS

`macOS` разрешает зависимые динамические библиотеки из команд загрузки, указанных в файле `match-o`, по-другому, чем загрузчик Linux. В загрузчике Linux .NET пробует использовать `libicudata`, `libicuuc` и `libicui18n` (в этом порядке) для обеспечения соответствия графу зависимостей ICU. Однако в macOS это не работает. При создании ICU в macOS вы по умолчанию получаете динамическую библиотеку с помощью этих команд загрузки в `libicuuc`. Например:

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

Эти команды просто ссылаются на имена зависимых библиотек для других компонентов ICU. Загрузчик выполняет поиск, следуя соглашениям `dlopen`, которые подразумевают использование этих библиотек в системных каталогах или задание переменных среды `LD_LIBRARY_PATH` или наличие ICU в каталоге уровня приложения. Если не удается задать `LD_LIBRARY_PATH` или убедиться, что двоичные файлы ICU находятся в каталоге уровня приложения, необходимо выполнить некоторую дополнительную работу.

Существует несколько директив для загрузчика, таких как `@loader_path`, которые указывают загрузчику выполнять поиск этой зависимости в том же каталоге, в котором находится двоичный файл с этой командой загрузки. Это достигается двумя способами.

- `install_name_tool -change`

  Выполните следующие команды:

```bash
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
```

- Исправление ICU таким образом, чтобы создавались имена установки с помощью `@loader_path`

  Перед выполнением автонастройки (`./runConfigureICU`) измените [эти строки](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) на следующие:

```
LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
```

## <a name="icu-on-webassembly"></a>ICU в WebAssembly

Доступна версия ICU, специально предназначенная для рабочих нагрузок WebAssembly. Она обеспечивает совместимость глобализации с профилями рабочих столов. Чтобы уменьшить размер файла данных ICU с 24 МБ до 1,4 МБ (или около 0,3 МБ при сжатии с помощью Brotli), к этой рабочей нагрузке применяется ряд ограничений.

Не поддерживаются следующие API:

- <xref:System.Globalization.CultureInfo.EnglishName?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.NativeName?displayProperty=nameWithType>
- <xref:System.Globalization.DateTimeFormatInfo.NativeCalendarName?displayProperty=nameWithType>
- <xref:System.Globalization.RegionInfo.NativeName?displayProperty=nameWithType>

Следующие API поддерживаются с ограничениями:

- <xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> и <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> не поддерживают редко используемые формы <xref:System.Text.NormalizationForm.FormKC> и <xref:System.Text.NormalizationForm.FormKD>.
- <xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> возвращает то же значение, что и <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>.

Кроме того, список поддерживаемых языковых стандартов можно найти в [репозитории dotnet/icu](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).

---
ms.openlocfilehash: 47c676122df4f0990949a7bfbcd7af8c6144d870
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160553"
---
### <a name="built-in-support-for-winrt-is-removed-from-net"></a>Из .NET удалена встроенная поддержка WinRT

Из .NET удалена встроенная поддержка использования [API-интерфейсов в среде выполнения Windows (WinRT)](/uwp/winrt-cref/winrt-type-system).

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 6

#### <a name="change-description"></a>Описание изменений

Ранее CoreCLR поддерживал использование [файлов метаданных Windows (WinMD)](/uwp/winrt-cref/winmd-files) для активации и использования типов WinRT. Начиная с версии .NET 5.0 поддержка прямого использования файлов WinMD в CoreCLR прекращена.

При попытке добавить ссылку на неподдерживаемую сборку отображается <xref:System.IO.FileNotFoundException>. При активации класса WinRT отображается <xref:System.PlatformNotSupportedException>.

Это критическое изменение добавлено по следующим причинам:

- Таким образом, разрабатывать и совершенствовать WinRT можно отдельно от среды выполнения .NET.
- Для симметрии с системами взаимодействия, которые предоставляются для других операционных систем, таких как iOS и Android.
- Для использования преимуществ других функций .NET, таких как функции C#, компоновка промежуточного языка (IL) и компиляция перед выполнением.
- Для упрощения базы кода в среде выполнения .NET.

#### <a name="recommended-action"></a>Рекомендованное действие

- Удалите ссылки на [пакет Microsoft.Windows.SDK.Contracts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).  Вместо этого укажите версию API-интерфейсов Windows, доступ к которым требуется получать с помощью свойства `TargetFramework` проекта.  Пример:

  ```xml
  <TargetFramework>net5.0-windows10.0.19041</TargetFramework>
  ```

- Используйте цепочку инструментов [C#/WinRT](/windows/uwp/csharp-winrt/) для создания или настройки API-интерфейсов и типов WinRT в .NET 5.0 и более поздних версий.

#### <a name="category"></a>Категория

Interop

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

-->

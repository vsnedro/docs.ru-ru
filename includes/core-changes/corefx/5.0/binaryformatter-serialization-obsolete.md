---
ms.openlocfilehash: 43bd1481ca6c3d3444afda2e2a2c67e7236b4402
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434921"
---
### <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a>Методы сериализации BinaryFormatter устарели и запрещены в приложениях ASP.NET

Методы `Serialize` и `Deserialize` в <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter> и <xref:System.Runtime.Serialization.IFormatter> теперь считаются устаревшими и приводят к созданию предупреждения. Кроме того, сериализация <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> по умолчанию запрещена для приложений ASP.NET.

#### <a name="change-description"></a>Описание изменений

Из-за [уязвимостей системы безопасности](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) в <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> следующие методы считаются устаревшими и во время компиляции приводят к созданию предупреждения с идентификатором `SYSLIB0011`. Кроме того, в приложениях ASP.NET Core 5.0 и более поздних версий они вызовут исключение <xref:System.NotSupportedException>, если только веб-приложение не включило повторно функциональные возможности <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

Следующие методы сериализации также считаются устаревшими и приводят к созданию предупреждения `SYSLIB0011`, но изменений в их поведении не произошло:

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

#### <a name="reason-for-change"></a>Причина изменения

Эти методы объявлены устаревшими в рамках мер по отказу от использования <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> в экосистеме .NET.

#### <a name="recommended-action"></a>Рекомендованное действие

- Не используйте в коде <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. Рассмотрите возможность использования <xref:System.Text.Json.JsonSerializer> или <xref:System.Xml.Serialization.XmlSerializer> вместо них. Дополнительные сведения см. в статье [Руководство по безопасности BinaryFormatter](../../../../docs/standard/serialization/binaryformatter-security-guide.md).

- Можно временно отключить появляющееся во время компиляции предупреждение об использовании <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> (`SYSLIB0011`). Перед этим мы рекомендуем тщательно оценить риски для кода. Самый простой способ отключить предупреждения — обособить отдельные места вызова директивами `#pragma`.

  ```csharp
  // Now read the purchase order back from disk
  using (var readStream = new FileStream("myfile.bin", FileMode.Open))
  {
      var formatter = new BinaryFormatter();
  #pragma warning disable SYSLIB0011
      return (PurchaseOrder)formatter.Deserialize(readStream);
  #pragma warning restore SYSLIB0011
  }
  ```

  Предупреждение можно также отключить в файле проекта.

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  В этом случае предупреждение будет отключено во всех файлах с кодом в проекте. Подавление `SYSLIB0011` не приводит к отключению предупреждений, вызванных использованием других устаревших API.

- Чтобы продолжить использование <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> в приложениях ASP.NET, можно повторно включить их в файле проекта. Но делать это настоятельно не рекомендуется. Дополнительные сведения см. в статье [Руководство по безопасности BinaryFormatter](../../../../docs/standard/serialization/binaryformatter-security-guide.md).

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

Дополнительные сведения о рекомендуемых действиях см. в статье [Устранение ошибок, связанных с устареванием и отключением BinaryFormatter](https://aka.ms/binaryformatter).

#### <a name="category"></a>Категория

- Библиотеки Core .NET
- ASP.NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->

---
ms.openlocfilehash: 43da6233b70927e7320874772976b9e93a0bd69f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721326"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a>Изменение сигнатуры JsonFactoryConverter.CreateConverter

В целях упрощения формирования классов <xref:System.Text.Json.Serialization.JsonConverterFactory> метод <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> стал общедоступным и получил второй аргумент типа <xref:System.Text.Json.JsonSerializerOptions>.

#### <a name="change-description"></a>Описание изменений

Сигнатура метода `CreateConverter` в .NET Core до версии 3.0 (предварительная версия 8) имела вид:

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

В .NET Core 3.0 (предварительная версия 8) и более поздних версиях она имеет вид:

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

До этого изменения было сложно создать запечатанные фабричные преобразователи, так как не существовало простого способа получить <xref:System.Text.Json.Serialization.JsonConverter%601>. Превращение фабричного метода в открытый, а также передача текущего <xref:System.Text.Json.JsonSerializerOptions> обеспечивают гораздо более гибкое формирование.

#### <a name="version-introduced"></a>Представленная версия

3.0 (предварительная версия 8)

#### <a name="recommended-action"></a>Рекомендованное действие

Производные классы должны быть обновлены и перекомпилированы.

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

#### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->

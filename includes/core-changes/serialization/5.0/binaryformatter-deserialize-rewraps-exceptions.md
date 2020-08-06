---
ms.openlocfilehash: 4aef35502fc93cbf0399e3c8d0932338829d6c07
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517361"
---
### <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a>Метод BinaryFormatter.Deserialize повторно изолирует некоторые исключения в классе SerializationException

Метод <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> теперь заключает некоторые объекты исключений в <xref:System.Runtime.Serialization.SerializationException> перед передачей исключения обратно вызывающему объекту.

#### <a name="change-description"></a>Описание изменений

Ранее метод <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> позволял использовать некоторые произвольные исключения, например <xref:System.ArgumentNullException>, для передачи стека соответствующим вызывающим объектам.

В .NET 5.0 и более поздних версиях метод <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> более агрессивно перехватывает исключения, вызываемые из-за недопустимых операций десериализации, и заключает их в <xref:System.Runtime.Serialization.SerializationException>.

#### <a name="version-introduced"></a>Представленная версия

5.0 Предварительная версия 1

#### <a name="recommended-action"></a>Рекомендованное действие

В большинстве случаев никаких дополнительных действий от вас не требуется. Но если место вызова зависит от конкретного исключения, вы можете исключить его из <xref:System.Runtime.Serialization.SerializationException>, как показано в следующем примере.

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx)
{
    if (serEx.InnerException is MyException myEx)
    {
        // Handle 'myEx' here in case it was wrapped in SerializationException.
    }
    else
    {
        throw;
    }
}
```

#### <a name="category"></a>Категория

Сериализация

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

-->

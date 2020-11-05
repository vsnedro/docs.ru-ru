---
ms.openlocfilehash: 2599e1f65720c25695f1fb5cfa39cabb842efc1d
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888623"
---
### <a name="default-feedbacksize-value-for-instances-created-by-tripledescreate-changed"></a>Изменено значение FeedbackSize по умолчанию для экземпляров, создаваемых методом TripleDES.Create

Значение по умолчанию для свойства <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType> экземпляра <xref:System.Security.Cryptography.TripleDES>, возвращаемого <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>, изменено с 64 на 8, чтобы упростить переход с .NET Framework. Это свойство, если оно не используется непосредственно в коде вызывающего объекта, применяется только в том случае, когда свойство <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> имеет значение <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.

Поддержка режима <xref:System.Security.Cryptography.CipherMode.CFB> появилась в выпуске .NET 5.0 RC1, поэтому это изменение должно влиять только на приложения .NET 5.0 RC1 и .NET 5.0 RC2.

#### <a name="change-description"></a>Описание изменений

В .NET Core и предыдущих предварительных версиях .NET 5.0 `TripleDES.Create().FeedbackSize` имеет значение по умолчанию 64. Начиная с RTM-версии .NET 5.0 `TripleDES.Create().FeedbackSize` имеет значение по умолчанию 8.

#### <a name="reason-for-change"></a>Причина изменения

В .NET Framework в базовом классе <xref:System.Security.Cryptography.TripleDES> свойство <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> имеет значение по умолчанию 64, но класс <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> меняет его на 8. Когда свойство <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> было введено в .NET Core версии 2.0, это поведение сохранилось. Однако в .NET Framework <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> возвращает экземпляр <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>, поэтому значение по умолчанию, возвращаемое фабрикой алгоритмов, равно 8. Для .NET Core и .NET 5 или более поздней версии фабрика алгоритмов возвращает закрытую реализацию, которая ранее имела значение по умолчанию 64.

Изменение значения <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> для реализации класса <xref:System.Security.Cryptography.TripleDES> на 8 позволяет написанным для .NET Framework приложениям, в которых задавался режим шифрования <xref:System.Security.Cryptography.CipherMode.CFB>, но свойство <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> не указывалось явным образом, продолжать работать в .NET 5.

#### <a name="version-introduced"></a>Представленная версия

5.0 RTM

#### <a name="recommended-action"></a>Рекомендованное действие

Приложения, которые шифруют или расшифровывают данные в версии RC1 или RC2 .NET 5.0, делают это с помощью алгоритма CFB64 при выполнении следующих условий:

- экземпляр <xref:System.Security.Cryptography.TripleDES> получен от метода <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>;
- для <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> используется значение по умолчанию;
- свойству <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> присвоено значение <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.

Чтобы сохранить это поведение, присвойте свойству <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> значение `64`.

Не все реализации `TripleDES` используют такое же значение по умолчанию для <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>. При использовании режима шифрования <xref:System.Security.Cryptography.CipherMode.CFB> в экземплярах <xref:System.Security.Cryptography.TripleDES> мы рекомендуем всегда явно задавать значение свойства <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.

```csharp
TripleDES cipher = TripleDES.Create();
cipher.Mode = CipherMode.CFB;
// Explicitly set the FeedbackSize for CFB to control between CFB8 and CFB64.
cipher.FeedbackSize = 8;
```

#### <a name="category"></a>Категория

- Шифрование

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.TripleDES.Create`
- `P:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize`

-->

---
ms.openlocfilehash: 7766a59131fffe2b436c15a5ff58e67001be7941
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065111"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a>CryptoStream.Dispose преобразует окончательный блок только при записи

Метод <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType>, который используется для завершения операций `CryptoStream`, больше не пытается преобразовать окончательный блок при чтении.

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET, если пользователь выполнил неполное чтение при использовании <xref:System.Security.Cryptography.CryptoStream> в режиме <xref:System.Security.Cryptography.CryptoStreamMode.Read>, метод <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> может вызвать исключение (например, при использовании AES с заполнением). Возникло исключение, так как предпринята попытка преобразования последнего блока, но данные были неполными.

В .NET Core 3.0 и более поздних версиях <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> больше не пытается преобразовать окончательный блок при чтении, что позволяет выполнять неполные операции чтения.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение включает неполные операции чтения из потока шифрования при отмене сетевой операции без необходимости перехватывать исключение.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендованное действие

Это изменение не затрагивает большинство приложений.

Если приложение ранее перехватило исключение в случае неполного чтения, этот блок `catch` можно удалить.
Если приложение использовало преобразование окончательного блока в сценариях хэширования, перед уничтожением может потребоваться считать весь поток.

#### <a name="category"></a>Категория

Шифрование

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->

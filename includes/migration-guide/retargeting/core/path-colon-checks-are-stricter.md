---
ms.openlocfilehash: 6af63c0a58a3273aa98fa70f22e3637b481806b4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497307"
---
### <a name="path-colon-checks-are-stricter"></a>Более строгие проверки двоеточий в пути

#### <a name="details"></a>Подробнее

В .NET Framework 4.6.2 выполнен ряд изменений для поддержки ранее не поддерживаемых путей (по длине и формату). Исправлены проверки надлежащего синтаксиса разделителя диска (двоеточие), в результате появился побочный эффект в виде блокировки некоторых путей универсального кода ресурса (URI) в некоторых API-интерфейсах пути, где раньше это допускалось.

#### <a name="suggestion"></a>Предложение

При передаче универсального кода ресурса (URI) в соответствующий API сначала измените строку, чтобы она содержала допустимый путь.

- Удалите схему из URL-адресов вручную (например, удалите `file://` из URL-адресов).

- Передайте универсальный код ресурса (URI) в класс <xref:System.Uri> и используйте <xref:System.Uri.LocalPath>.

Кроме того, вы можете отказаться от новой нормализации путей, установив для переключателя `Switch.System.IO.UseLegacyPathHandling` AppContext значение `true`.

| Имя    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>

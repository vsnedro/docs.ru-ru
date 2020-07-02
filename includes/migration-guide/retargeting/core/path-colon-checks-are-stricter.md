---
ms.openlocfilehash: 3e4a5936bbac4e77efc5f7e68b55ddf49bae5d43
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614717"
---
### <a name="path-colon-checks-are-stricter"></a>Более строгие проверки двоеточий в пути

#### <a name="details"></a>Подробнее

В .NET Framework 4.6.2 выполнен ряд изменений для поддержки ранее не поддерживаемых путей (по длине и формату). Исправлены проверки надлежащего синтаксиса разделителя диска (двоеточие), в результате появился побочный эффект в виде блокировки некоторых путей универсального кода ресурса (URI) в некоторых API-интерфейсах пути, где раньше это допускалось.

#### <a name="suggestion"></a>Предложение

При передаче универсального кода ресурса (URI) в соответствующий API сначала измените строку, чтобы она содержала допустимый путь.<ul><li>Удалите схему из URL-адресов вручную (например, удалите `file://` из URL-адресов)

- Передайте универсальный код ресурса (URI) в класс <xref:System.Uri> и используйте <xref:System.Uri.LocalPath>

Кроме того, вы можете отказаться от новой нормализации путей, установив для переключателя `Switch.System.IO.UseLegacyPathHandling` AppContext значение true.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>

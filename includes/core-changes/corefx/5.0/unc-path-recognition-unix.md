---
ms.openlocfilehash: 0246f325a6274082b7fb0d5590cec7c80687ae85
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720210"
---
### <a name="uri-recognition-of-unc-paths-on-unix"></a>Распознавание URI UNC-путей в UNIX

Класс <xref:System.Uri> теперь распознает строки, начинающиеся с двух косых черт (`//`) как пути в формате UNC в операционных системах UNIX. Это изменение делает поведение для таких строк согласованным на всех платформах.

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET класс <xref:System.Uri> распознавал строки, начинающиеся с двух косых черт, например `//contoso`, как абсолютные пути к файлам в операционных системах UNIX. Однако в Windows такие строки распознаются как UNC-пути.

Начиная с .NET 5.0 класс <xref:System.Uri> распознает строки, начинающиеся с двух косых черт, как UNC-пути на всех платформах, включая UNIX. Кроме того, свойства ведут себя в соответствии с семантикой UNC:

- <xref:System.Uri.IsUnc?displayProperty=nameWithType> возвращает `true`.
- Символы обратной косой черты в пути заменяются прямой косой чертой. Например, `//first\second` преобразуется в `//first/second`.
- <xref:System.Uri.LocalPath?displayProperty=nameWithType> не кодирует символы процентами. Например, `//first/\uFFF0` *не* преобразуется в `//first/%EF%BF%B0`.

#### <a name="version-introduced"></a>Представленная версия

5.0

#### <a name="recommended-action"></a>Рекомендованное действие

От разработчика не требуется никаких действий.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->

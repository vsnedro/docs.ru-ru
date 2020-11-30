---
ms.openlocfilehash: bb264e406c6604c3606e564d99018eda0f9e8d89
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032155"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a>Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла

Многие интерфейсы API, которые возвращают версию в .NET Core, теперь возвращают версию продукта, а не файла.

#### <a name="change-description"></a>Описание изменений

В .NET Core 2.2 и предыдущих версиях такие методы, как <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> и диалоговое окно свойств файла для сборок .NET Core, сообщают версию файла. Начиная с версии .NET Core 3.0, они сообщают версию продукта.

На приведенном ниже рисунке показана разница в сведениях о версии для сборки *System.Runtime.dll* для .NET Core 2.2 (слева) и .NET Core 3.0 (справа), отображаемых в диалоговом окне свойств файла в **проводнике**.

![Разница в сведениях о версии](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендованное действие

Отсутствует. Это изменение должно сделать определение версии интуитивно понятным.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->

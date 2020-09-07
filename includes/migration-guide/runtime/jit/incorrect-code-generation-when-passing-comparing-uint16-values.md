---
ms.openlocfilehash: 018c99d60dc8926cae2682dc9c035e25fba711e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496112"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>Некорректное формирование кода при передаче и сравнении значений UInt16

#### <a name="details"></a>Подробнее

Из-за изменений, представленных в версии .NET Framework 4.7, в некоторых случаях созданный JIT-компилятором код в приложениях на платформе .NET Framework 4.7 некорректно сравнивает значения <code>T:System.UInt16</code>. Дополнительные сведения см. в статье [Проблема № 11508. Некорректное автоматическое формирование кода при передаче и сравнении аргументов ushort](https://github.com/dotnet/coreclr/issues/11508) на веб-сайте GitHub.com.

#### <a name="suggestion"></a>Предложение

Если вы сталкиваетесь с проблемами при сравнении 16-разрядных значений без знака в .NET Framework 4.7, выполните обновление до .NET Framework 4.7.1.

| Имя    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.7|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->

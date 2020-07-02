---
ms.openlocfilehash: c20d5fb3d700ba7649e423a79e4598b327c50a00
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622273"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>Некорректное формирование кода при передаче и сравнении значений UInt16

#### <a name="details"></a>Подробнее

Из-за изменений, представленных в версии .NET Framework 4.7, в некоторых случаях созданный JIT-компилятором код в приложениях на платформе .NET Framework 4.7 некорректно сравнивает значения <code>T:System.UInt16</code>. Дополнительные сведения см. в статье [Проблема № 11508. Некорректное автоматическое формирование кода при передаче и сравнении аргументов ushort](https://github.com/dotnet/coreclr/issues/11508) на веб-сайте GitHub.com.

#### <a name="suggestion"></a>Предложение

Если вы сталкиваетесь с проблемами при сравнении 16-разрядных значений без знака в .NET Framework 4.7, выполните обновление до .NET Framework 4.7.1.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.7|
|Type|Среда выполнения|

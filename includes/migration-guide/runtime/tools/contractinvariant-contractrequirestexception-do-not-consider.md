---
ms.openlocfilehash: 17fde81f9734966692c9f41d2213f8682dedea46
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497319"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a>Contract.Invariant или Contract.Requires\<TException> не учитывает необходимость чистоты String.IsNullOrEmpty

#### <a name="details"></a>Подробнее

В приложениях, предназначенных для .NET Framework 4.6.1, если контракт инвариантности для <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> или контракт предусловия для <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> вызывает метод <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType>, средство перезаписи выдает предупреждение компилятора CC1036: &quot;обнаружен вызов метода "System.String.IsNullOrWhteSpace(System.String)" без [Pure] в методе.&quot; Это предупреждение, а не ошибка компилятора.

#### <a name="suggestion"></a>Предложение

Проблема была устранена в [билете 339 на сайте GitHub](https://github.com/Microsoft/CodeContracts/issues/339). Чтобы устранить это предупреждение, можно скачать и скомпилировать обновленную версию исходного кода для инструментов контрактов кода с сайта [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md). Сведения о скачивании находятся в нижней части страницы.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6.1|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)`
- `M:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)`

-->

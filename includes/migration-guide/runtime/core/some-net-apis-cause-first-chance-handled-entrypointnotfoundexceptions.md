---
ms.openlocfilehash: 6431f3b4d0983c44629e4fe760c75adcc277ddd4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497158"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>Некоторые интерфейсы API .NET создают первый экземпляр (обрабатываемый) EntryPointNotFoundExceptions

#### <a name="details"></a>Подробнее

В .NET Framework 4.5 несколько методов .NET начали создавать первый экземпляр <xref:System.EntryPointNotFoundException?displayProperty=fullName>. Эти исключения обрабатывались в .NET Framework, но могли нарушать работу службы автоматизации тестирования, которая не ожидала первых экземпляров исключений. Те же интерфейсы API препятствуют работе некоторых сценариев ApiVerifier, если включен тест HighVersionLie.

#### <a name="suggestion"></a>Предложение

Этой ошибки можно избежать путем обновления до .NET Framework 4.5.1. Кроме того, службу автоматизации тестирования можно обновить, чтобы она не прерывала свое выполнение при создании первого экземпляра <xref:System.EntryPointNotFoundException?displayProperty=fullName>.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)>

<!--

#### Affected APIs

- `M:System.Diagnostics.Debug.Assert(System.Boolean)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])`
- `M:System.Xml.Serialization.XmlSerializer.#ctor(System.Type)`

-->

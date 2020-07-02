---
ms.openlocfilehash: ed526095459a48aa37b585dfed79cc12b9fb9e56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622140"
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

-<xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)></li></ul>|

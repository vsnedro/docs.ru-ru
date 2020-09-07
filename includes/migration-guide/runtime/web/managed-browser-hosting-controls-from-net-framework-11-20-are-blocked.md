---
ms.openlocfilehash: 26539011f0650c7a3bac9e1c41847561905fff58
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496612"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a>Элементы управления Managed Browser в .NET Framework 1.1 и 2.0 заблокированы

#### <a name="details"></a>Подробнее

Размещение этих элементов управления в Internet Explorer блокируется.

#### <a name="suggestion"></a>Предложение

Internet Explorer не сможет запустить приложение, в котором используются управляемые элементы управления, размещенные в браузере. Прежнее поведение можно восстановить путем установки параметру EnableIEHosting подраздела реестра <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> значения <code>1</code> для систем x86 и для 32-разрядных процессов в системах x64, а также путем установки параметру <code>EnableIEHosting</code> подраздела реестра <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> значения <code>1</code> для 64-разрядных процессов в системах x64.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->

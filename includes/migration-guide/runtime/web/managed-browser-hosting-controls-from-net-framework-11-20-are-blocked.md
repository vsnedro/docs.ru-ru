---
ms.openlocfilehash: 83d3f24680531d1e447f047151a28c98ce0da04b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620672"
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

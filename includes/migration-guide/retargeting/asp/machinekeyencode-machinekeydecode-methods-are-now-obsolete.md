---
ms.openlocfilehash: e9d34465970287ed94c0f0373ee4ae94d55aa1ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617265"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>Методы MachineKey.Encode и MachineKey.Decode устарели

#### <a name="details"></a>Подробнее

В настоящее время эти методы считаются устаревшими. При компиляции кода, который вызывает эти методы, создается предупреждение компилятора.

#### <a name="suggestion"></a>Предложение

Взамен рекомендуется использовать <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> и <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>. Кроме того, можно подавить предупреждения сборки или избежать их вывода с помощью более старой версии компилятора. Интерфейсы API по-прежнему поддерживаются.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.5         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
- <xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>

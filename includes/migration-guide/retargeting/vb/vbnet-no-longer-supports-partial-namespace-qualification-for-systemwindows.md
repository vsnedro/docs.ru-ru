---
ms.openlocfilehash: cef8096c971da8ae245ff974697022f350cb9195
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616073"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>VB.NET больше не поддерживает частичные квалификации пространства имен для API-интерфейсов System.Windows

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.5.2 в проектах VB.NET невозможно задать API-интерфейсы System.Windows с частично указанными пространствами имен. Например, ссылка на `Windows.Forms.DialogResult` завершится ошибкой. Вместо этого код должен ссылаться на полное доменное имя (<xref:System.Windows.Forms.DialogResult>) или импортировать конкретное пространство имен и сослаться просто на <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Следует обновить код для ссылки на API `System.Windows` либо с простыми именами (и импортом соответствующего пространства имен), либо с полными доменными именами.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.5.2       |
| Type    | Изменение целевой платформы |

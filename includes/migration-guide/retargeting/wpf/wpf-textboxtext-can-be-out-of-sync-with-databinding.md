---
ms.openlocfilehash: d0de1a262d57c67dd4dfb258d5ac013af5d8783d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617292"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>WPF TextBox.Text может быть не синхронизирован с привязкой данных

#### <a name="details"></a>Подробнее

В некоторых случаях свойство <xref:System.Windows.Controls.TextBox.Text> отражает предыдущее значение привязанного к данным свойства, если свойство изменяется во время операции записи с привязкой к данным.

#### <a name="suggestion"></a>Предложение

Это не должно иметь отрицательных последствий. Однако можно восстановить прежнее поведение, установив свойству <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> значение `false`.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.5         |
|Type|Изменение целевой платформы

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType>

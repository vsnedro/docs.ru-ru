---
ms.openlocfilehash: 9c84c9f844a2a7efb9633c11634b069ef6b6033b
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804870"
---
### <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a>Элемент DataGridView больше не сбрасывает шрифты для настраиваемых стилей ячеек

При изменении шрифта окружения <xref:System.Windows.Forms.DataGridViewElement.DataGridView> больше не выполняет сброс шрифтов стиля ячейки по умолчанию, чтобы они совпадали со шрифтом окружения, если шрифт стиля ячейки был настроен.

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET при изменении шрифта окружения <xref:System.Windows.Forms.DataGridViewElement.DataGridView> сбрасывал и переопределял пользовательские шрифты в свойствах <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle>.

Начиная с .NET 5.0 при настройке параметров шрифтов в свойствах <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> эти параметры сохраняются даже при изменении шрифта окружения. Для всех свойств, для которых шрифт не был настроен, шрифт изменится в соответствии с параметрами шрифта окружения.

#### <a name="reason-for-change"></a>Причина изменения

При [изменении шрифта по умолчанию в .NET Core 3.0](../../../../docs/core/compatibility/winforms.md#default-control-font-changed-to-segoe-ui-9-pt) параметры шрифтов по умолчанию для различных стилей ячеек также изменяются. Такое поведение нежелательно для приложений, которые используют пользовательский стиль в своих элементах управления <xref:System.Windows.Forms.DataGridViewElement.DataGridView>, и затрудняет их перенос с .NET Framework на .NET 5.0.

#### <a name="version-introduced"></a>Представленная версия

.NET 5.0 RC2

#### <a name="recommended-action"></a>Рекомендованное действие

Никаких действий выполнять не требуется. Однако если вы настроили шрифт в свойствах <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> и хотите, чтобы шрифт совпадал со шрифтом окружения, установите параметр <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> в значение `null` для каждого свойства.

#### <a name="category"></a>Категория

- Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Windows.Forms.DataGridView.DefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle`

-->

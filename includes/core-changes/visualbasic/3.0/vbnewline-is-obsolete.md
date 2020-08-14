---
ms.openlocfilehash: 072ed716910e2e1f1f98dbddc56d5bd097b75acc
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555918"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine устарела

Начиная с .NET Core 3.0, константа <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> помечена как [\[устаревшая\]](xref:System.ObsoleteAttribute).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Core 3.0, к константе <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> применяется атрибут [Obsolete](xref:System.ObsoleteAttribute). При использовании константы выдается предупреждение компилятора. В .NET Framework и предыдущих версиях .NET Core она не была помечена как устаревшая.

Это изменение было внесено для поддержки Visual Basic в качестве языка для разработки на нескольких платформах. Константа <xref:Microsoft.VisualBasic.Constants.vbNewLine> эквивалентна `\r\n`, последовательности символов новой строки в Windows. В системах на основе Unix символ новой строки — `\n`.

#### <a name="recommended-action"></a>Рекомендованное действие

Сообщение атрибута [Obsolete](xref:System.ObsoleteAttribute) для <xref:Microsoft.VisualBasic.Constants.vbNewLine> включает следующие рекомендации:

Для возврата каретки и перевода строки используйте <xref:Microsoft.VisualBasic.Constants.vbCrLf>. Для новой строки на текущей платформе используйте <xref:System.Environment.NewLine?displayProperty=nameWithType>.

#### <a name="category"></a>Категория

Visual Basic

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

#### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->

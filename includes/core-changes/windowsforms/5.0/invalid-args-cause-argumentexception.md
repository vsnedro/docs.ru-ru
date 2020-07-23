---
ms.openlocfilehash: 9f6703c77e17ac9376aee944b891f4635dc7632e
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309165"
---
### <a name="winforms-methods-now-throw-argumentexception"></a>Теперь методы WinForms вызывают исключение ArgumentException

Некоторые методы Windows Forms теперь вызывают <xref:System.ArgumentException> для недопустимых аргументов в ситуациях, где ранее не делали этого.

#### <a name="change-description"></a>Описание изменений

Ранее передача аргументов непредвиденного или неверного типа в определенные методы Windows Forms приводила к неопределенному состоянию. Начиная с .NET 5.0 эти методы теперь вызывают <xref:System.ArgumentException> при передаче недопустимых аргументов.

Вызов <xref:System.ArgumentException> соответствует поведению среды выполнения .NET. Это также улучшает процесс отладки, четко указывая, какой аргумент недопустим.

#### <a name="version-introduced"></a>Представленная версия

.NET 5.0

#### <a name="recommended-action"></a>Рекомендованное действие

- Измените код, чтобы предотвратить передачу недопустимых аргументов.
- При необходимости обработайте <xref:System.ArgumentException> при вызове метода.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

В следующей таблице перечислены затронутые методы и параметры:

| Метод | Имя параметра | Условие | Добавлено в версии |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | Аргумент не является аргументом типа <xref:System.Windows.Forms.TabPage>. | Предварительная версия 1 |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | Аргумент содержит `null`, <xref:System.String.Empty?displayProperty=nameWithType> или пробел. | Предварительная версия 5 |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | Не удается извлечь `InputLanguage` для заданных языка и региональных параметров. | Предварительная версия 7 |

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

-->

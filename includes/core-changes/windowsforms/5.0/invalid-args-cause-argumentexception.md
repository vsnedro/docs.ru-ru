---
ms.openlocfilehash: f1fc70075ef09a4f036c69788342c07ee51d72ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702487"
---
### <a name="winforms-methods-now-throw-argumentexception"></a>Теперь методы WinForms вызывают исключение ArgumentException

Некоторые методы Windows Forms теперь вызывают <xref:System.ArgumentException> для недопустимых аргументов в ситуациях, где ранее не делали этого.

#### <a name="change-description"></a>Описание изменений

Ранее передача аргументов непредвиденного или неверного типа в определенные методы Windows Forms приводила к неопределенному состоянию. Начиная с .NET 5.0 эти методы теперь вызывают <xref:System.ArgumentException> при передаче недопустимых аргументов.

Вызов <xref:System.ArgumentException> соответствует поведению среды выполнения .NET. Это также улучшает процесс отладки, четко указывая, какой аргумент недопустим.

В следующей таблице перечислены затронутые методы и параметры:

| Метод | Имя параметра | Условие | Добавлено в версии |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | Аргумент не является аргументом типа <xref:System.Windows.Forms.TabPage>. | 5.0 Предварительная версия 1 |

#### <a name="version-introduced"></a>Представленная версия

Предварительная версия 1 .NET 5.0

#### <a name="recommended-action"></a>Рекомендованное действие

- Измените код, чтобы предотвратить передачу недопустимых аргументов.
- При необходимости обработайте <xref:System.ArgumentException> при вызове метода.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->

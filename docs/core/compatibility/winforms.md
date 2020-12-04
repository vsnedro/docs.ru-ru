---
title: Критические изменения в Windows Forms
description: Список критических изменений в Windows Forms для .NET Core 3.0 и 3.1.
ms.date: 09/08/2020
ms.openlocfilehash: b944f7eea89b61f41feb8eef99e949c2d6017960
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726435"
---
# <a name="breaking-changes-in-windows-forms-for-net-core-30-and-31"></a>Критические изменения в Windows Forms для .NET Core 3.0 и 3.1

Поддержка Windows Forms была добавлена в .NET Core в версии 3.0. В этой статье перечислены критические изменения для Windows Forms, сгруппированные по версии .NET, в которой они появились. Если вы обновляете приложение Windows Forms с .NET Framework или с предыдущей версии .NET Core (3.0 или более поздней), эта статья для вас актуальна.

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленная версия |
| - | :-: |
| [Удаленные элементы управления](#removed-controls) | 3.1 |
| [При отображении подсказки не возникает событие CellFormatting](#cellformatting-event-not-raised-if-tooltip-is-shown) | 3.1 |
| [Шрифт Control.DefaultFont изменен на Segoe UI 9 пт](#default-control-font-changed-to-segoe-ui-9-pt) | 3.0 |
| [Модернизация FolderBrowserDialog](#modernization-of-the-folderbrowserdialog) | 3.0 |
| [Из некоторых типов Windows Forms удален атрибут SerializableAttribute](#serializableattribute-removed-from-some-windows-forms-types) | 3.0 |
| [Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | 3.0 |
| [Параметр совместимости DomainUpDown.UseLegacyScrolling не поддерживается](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | 3.0 |
| [Параметр совместимости DoNotLoadLatestRichEditControl не поддерживается](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | 3.0 |
| [Параметр совместимости DoNotSupportSelectAllShortcutInMultilineTextBox не поддерживается](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | 3.0 |
| [Параметр совместимости DontSupportReentrantFilterMessage не поддерживается](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | 3.0 |
| [Параметр совместимости EnableVisualStyleValidation не поддерживается](#enablevisualstylevalidation-compatibility-switch-not-supported) | 3.0 |
| [Параметр совместимости UseLegacyContextMenuStripSourceControlValue не поддерживается](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | 3.0 |
| [Параметр совместимости UseLegacyImages не поддерживается](#uselegacyimages-compatibility-switch-not-supported) | 3.0 |

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

**_

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

_*_

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

_*_

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

_**

## <a name="see-also"></a>См. также

- [Перенос приложения Windows Forms в .NET Core](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)

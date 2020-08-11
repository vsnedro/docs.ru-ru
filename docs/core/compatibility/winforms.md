---
title: Критические изменения в Windows Forms
description: Список критических изменений в Windows Forms для .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: beb9a42e4b5007f03480cd74f57bbfbbfc3f48b1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556254"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="b3f7d-103">Критические изменения в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3f7d-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="b3f7d-104">Поддержка Windows Forms была добавлена в .NET Core в версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="b3f7d-105">В этой статье перечислены критические изменения для Windows Forms, сгруппированные по версии .NET Core, в которой они появились.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="b3f7d-106">Если вы обновляете приложение Windows Forms с .NET Framework или с предыдущей версии .NET Core (3.0 или более поздней), эта статья для вас актуальна.</span><span class="sxs-lookup"><span data-stu-id="b3f7d-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="b3f7d-107">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="b3f7d-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="b3f7d-108">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="b3f7d-108">Breaking change</span></span> | <span data-ttu-id="b3f7d-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="b3f7d-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="b3f7d-110">Удалены элементы управления строкой состояния</span><span class="sxs-lookup"><span data-stu-id="b3f7d-110">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="b3f7d-111">5.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-111">5.0</span></span> |
| [<span data-ttu-id="b3f7d-112">Теперь методы WinForms вызывают исключение ArgumentException</span><span class="sxs-lookup"><span data-stu-id="b3f7d-112">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="b3f7d-113">5.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-113">5.0</span></span> |
| [<span data-ttu-id="b3f7d-114">Теперь методы WinForms вызывают исключение ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="b3f7d-114">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="b3f7d-115">5.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-115">5.0</span></span> |
| [<span data-ttu-id="b3f7d-116">Теперь свойства WinForms вызывают исключение ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="b3f7d-116">WinForms properties now throw ArgumentOutOfRangeException</span></span>](#winforms-properties-now-throw-argumentoutofrangeexception) | <span data-ttu-id="b3f7d-117">5.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-117">5.0</span></span> |
| [<span data-ttu-id="b3f7d-118">Удаленные элементы управления</span><span class="sxs-lookup"><span data-stu-id="b3f7d-118">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="b3f7d-119">3.1</span><span class="sxs-lookup"><span data-stu-id="b3f7d-119">3.1</span></span> |
| [<span data-ttu-id="b3f7d-120">При отображении подсказки не возникает событие CellFormatting</span><span class="sxs-lookup"><span data-stu-id="b3f7d-120">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="b3f7d-121">3.1</span><span class="sxs-lookup"><span data-stu-id="b3f7d-121">3.1</span></span> |
| [<span data-ttu-id="b3f7d-122">Шрифт Control.DefaultFont изменен на Segoe UI 9 пт</span><span class="sxs-lookup"><span data-stu-id="b3f7d-122">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="b3f7d-123">3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-123">3.0</span></span> |
| [<span data-ttu-id="b3f7d-124">Модернизация FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="b3f7d-124">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="b3f7d-125">3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-125">3.0</span></span> |
| [<span data-ttu-id="b3f7d-126">Из некоторых типов Windows Forms удален атрибут SerializableAttribute</span><span class="sxs-lookup"><span data-stu-id="b3f7d-126">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="b3f7d-127">3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-127">3.0</span></span> |
| [<span data-ttu-id="b3f7d-128">Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается</span><span class="sxs-lookup"><span data-stu-id="b3f7d-128">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="b3f7d-129">3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-129">3.0</span></span> |
| [<span data-ttu-id="b3f7d-130">Параметр совместимости DomainUpDown.UseLegacyScrolling не поддерживается</span><span class="sxs-lookup"><span data-stu-id="b3f7d-130">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="b3f7d-131">3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-131">3.0</span></span> |
| [<span data-ttu-id="b3f7d-132">Параметр совместимости DoNotLoadLatestRichEditControl не поддерживается</span><span class="sxs-lookup"><span data-stu-id="b3f7d-132">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="b3f7d-133">3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-133">3.0</span></span> |
| [<span data-ttu-id="b3f7d-134">Параметр совместимости DoNotSupportSelectAllShortcutInMultilineTextBox не поддерживается</span><span class="sxs-lookup"><span data-stu-id="b3f7d-134">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="b3f7d-135">3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-135">3.0</span></span> |
| [<span data-ttu-id="b3f7d-136">Параметр совместимости DontSupportReentrantFilterMessage не поддерживается</span><span class="sxs-lookup"><span data-stu-id="b3f7d-136">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="b3f7d-137">3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-137">3.0</span></span> |
| [<span data-ttu-id="b3f7d-138">Параметр совместимости EnableVisualStyleValidation не поддерживается</span><span class="sxs-lookup"><span data-stu-id="b3f7d-138">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="b3f7d-139">3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-139">3.0</span></span> |
| [<span data-ttu-id="b3f7d-140">Параметр совместимости UseLegacyContextMenuStripSourceControlValue не поддерживается</span><span class="sxs-lookup"><span data-stu-id="b3f7d-140">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="b3f7d-141">3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-141">3.0</span></span> |
| [<span data-ttu-id="b3f7d-142">Параметр совместимости UseLegacyImages не поддерживается</span><span class="sxs-lookup"><span data-stu-id="b3f7d-142">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="b3f7d-143">3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-143">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="b3f7d-144">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-144">.NET 5.0</span></span>

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="b3f7d-145">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="b3f7d-145">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="b3f7d-146">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b3f7d-146">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

## <a name="see-also"></a><span data-ttu-id="b3f7d-147">См. также</span><span class="sxs-lookup"><span data-stu-id="b3f7d-147">See also</span></span>

- [<span data-ttu-id="b3f7d-148">Перенос приложения Windows Forms в .NET Core</span><span class="sxs-lookup"><span data-stu-id="b3f7d-148">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)

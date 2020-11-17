---
title: Критические изменения в Windows Forms
description: Список критических изменений в Windows Forms для .NET Core и .NET 5.
ms.date: 09/08/2020
ms.openlocfilehash: c79fd28b5c3b81ae7ddf1ef3f470601108b87705
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440794"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="cb938-103">Критические изменения в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb938-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="cb938-104">Поддержка Windows Forms была добавлена в .NET Core в версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="cb938-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="cb938-105">В этой статье перечислены критические изменения для Windows Forms, сгруппированные по версии .NET, в которой они появились.</span><span class="sxs-lookup"><span data-stu-id="cb938-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="cb938-106">Если вы обновляете приложение Windows Forms с .NET Framework или с предыдущей версии .NET Core (3.0 или более поздней), эта статья для вас актуальна.</span><span class="sxs-lookup"><span data-stu-id="cb938-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="cb938-107">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="cb938-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="cb938-108">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="cb938-108">Breaking change</span></span> | <span data-ttu-id="cb938-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="cb938-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="cb938-110">Флаг TextFormatFlags.ModifyString является устаревшим</span><span class="sxs-lookup"><span data-stu-id="cb938-110">TextFormatFlags.ModifyString is obsolete</span></span>](#textformatflagsmodifystring-is-obsolete) | <span data-ttu-id="cb938-111">5.0</span><span class="sxs-lookup"><span data-stu-id="cb938-111">5.0</span></span> |
| [<span data-ttu-id="cb938-112">Элемент DataGridView больше не сбрасывает шрифты для настраиваемых стилей ячеек</span><span class="sxs-lookup"><span data-stu-id="cb938-112">DataGridView no longer resets fonts for customized cell styles</span></span>](#datagridview-no-longer-resets-fonts-for-customized-cell-styles) | <span data-ttu-id="cb938-113">5.0</span><span class="sxs-lookup"><span data-stu-id="cb938-113">5.0</span></span> |
| [<span data-ttu-id="cb938-114">Свойству OutputType задано значение WinExe для приложений WPF и WinForms</span><span class="sxs-lookup"><span data-stu-id="cb938-114">OutputType set to WinExe for WPF and WinForms apps</span></span>](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | <span data-ttu-id="cb938-115">5.0</span><span class="sxs-lookup"><span data-stu-id="cb938-115">5.0</span></span> |
| [<span data-ttu-id="cb938-116">API, связанные с DataGridView, теперь вызывают исключение InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="cb938-116">DataGridView-related APIs now throw InvalidOperationException</span></span>](#datagridview-related-apis-now-throw-invalidoperationexception) | <span data-ttu-id="cb938-117">5.0</span><span class="sxs-lookup"><span data-stu-id="cb938-117">5.0</span></span> |
| [<span data-ttu-id="cb938-118">В приложениях WinForms и WPF используется Microsoft.NET.Sdk</span><span class="sxs-lookup"><span data-stu-id="cb938-118">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>](#winforms-and-wpf-apps-use-microsoftnetsdk) | <span data-ttu-id="cb938-119">5.0</span><span class="sxs-lookup"><span data-stu-id="cb938-119">5.0</span></span> |
| [<span data-ttu-id="cb938-120">Удалены элементы управления строкой состояния</span><span class="sxs-lookup"><span data-stu-id="cb938-120">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="cb938-121">5.0</span><span class="sxs-lookup"><span data-stu-id="cb938-121">5.0</span></span> |
| [<span data-ttu-id="cb938-122">Теперь методы WinForms вызывают исключение ArgumentException</span><span class="sxs-lookup"><span data-stu-id="cb938-122">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="cb938-123">5.0</span><span class="sxs-lookup"><span data-stu-id="cb938-123">5.0</span></span> |
| [<span data-ttu-id="cb938-124">Теперь методы WinForms вызывают исключение ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="cb938-124">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="cb938-125">5.0</span><span class="sxs-lookup"><span data-stu-id="cb938-125">5.0</span></span> |
| [<span data-ttu-id="cb938-126">Теперь свойства WinForms вызывают исключение ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="cb938-126">WinForms properties now throw ArgumentOutOfRangeException</span></span>](#winforms-properties-now-throw-argumentoutofrangeexception) | <span data-ttu-id="cb938-127">5.0</span><span class="sxs-lookup"><span data-stu-id="cb938-127">5.0</span></span> |
| [<span data-ttu-id="cb938-128">Удаленные элементы управления</span><span class="sxs-lookup"><span data-stu-id="cb938-128">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="cb938-129">3.1</span><span class="sxs-lookup"><span data-stu-id="cb938-129">3.1</span></span> |
| [<span data-ttu-id="cb938-130">При отображении подсказки не возникает событие CellFormatting</span><span class="sxs-lookup"><span data-stu-id="cb938-130">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="cb938-131">3.1</span><span class="sxs-lookup"><span data-stu-id="cb938-131">3.1</span></span> |
| [<span data-ttu-id="cb938-132">Шрифт Control.DefaultFont изменен на Segoe UI 9 пт</span><span class="sxs-lookup"><span data-stu-id="cb938-132">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="cb938-133">3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-133">3.0</span></span> |
| [<span data-ttu-id="cb938-134">Модернизация FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="cb938-134">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="cb938-135">3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-135">3.0</span></span> |
| [<span data-ttu-id="cb938-136">Из некоторых типов Windows Forms удален атрибут SerializableAttribute</span><span class="sxs-lookup"><span data-stu-id="cb938-136">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="cb938-137">3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-137">3.0</span></span> |
| [<span data-ttu-id="cb938-138">Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cb938-138">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="cb938-139">3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-139">3.0</span></span> |
| [<span data-ttu-id="cb938-140">Параметр совместимости DomainUpDown.UseLegacyScrolling не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cb938-140">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="cb938-141">3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-141">3.0</span></span> |
| [<span data-ttu-id="cb938-142">Параметр совместимости DoNotLoadLatestRichEditControl не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cb938-142">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="cb938-143">3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-143">3.0</span></span> |
| [<span data-ttu-id="cb938-144">Параметр совместимости DoNotSupportSelectAllShortcutInMultilineTextBox не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cb938-144">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="cb938-145">3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-145">3.0</span></span> |
| [<span data-ttu-id="cb938-146">Параметр совместимости DontSupportReentrantFilterMessage не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cb938-146">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="cb938-147">3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-147">3.0</span></span> |
| [<span data-ttu-id="cb938-148">Параметр совместимости EnableVisualStyleValidation не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cb938-148">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="cb938-149">3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-149">3.0</span></span> |
| [<span data-ttu-id="cb938-150">Параметр совместимости UseLegacyContextMenuStripSourceControlValue не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cb938-150">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="cb938-151">3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-151">3.0</span></span> |
| [<span data-ttu-id="cb938-152">Параметр совместимости UseLegacyImages не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cb938-152">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="cb938-153">3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-153">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="cb938-154">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="cb938-154">.NET 5.0</span></span>

[!INCLUDE [modifystring-field-of-textformatflags-obsolete](../../../includes/core-changes/windowsforms/5.0/modifystring-field-of-textformatflags-obsolete.md)]

***

[!INCLUDE [datagridview-doesnt-reset-custom-font-settings](../../../includes/core-changes/windowsforms/5.0/datagridview-doesnt-reset-custom-font-settings.md)]

<span data-ttu-id="cb938-155">\*\*_</span><span class="sxs-lookup"><span data-stu-id="cb938-155">\*\*_</span></span>

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

_*_

[!INCLUDE [null-owner-causes-invalidoperationexception](../../../includes/core-changes/windowsforms/5.0/null-owner-causes-invalidoperationexception.md)]

_*_

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

_*_

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

_*_

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

_*_

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

_*_

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

_*_

## <a name="net-core-31"></a><span data-ttu-id="cb938-156">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="cb938-156">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

_*_

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

_*_

## <a name="net-core-30"></a><span data-ttu-id="cb938-157">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="cb938-157">.NET Core 3.0</span></span>

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

<span data-ttu-id="cb938-158">_\*\*</span><span class="sxs-lookup"><span data-stu-id="cb938-158">_\*\*</span></span>

## <a name="see-also"></a><span data-ttu-id="cb938-159">См. также</span><span class="sxs-lookup"><span data-stu-id="cb938-159">See also</span></span>

- [<span data-ttu-id="cb938-160">Перенос приложения Windows Forms в .NET Core</span><span class="sxs-lookup"><span data-stu-id="cb938-160">Port a Windows Forms app to .NET Core</span></span>](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)

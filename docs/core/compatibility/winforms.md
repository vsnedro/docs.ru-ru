---
title: Критические изменения в Windows Forms
description: Список критических изменений в Windows Forms для .NET Core и .NET 5.
ms.date: 09/08/2020
ms.openlocfilehash: 3e7d077d07203d9c231ae4a7805e593c5432c135
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679008"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="842ac-103">Критические изменения в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="842ac-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="842ac-104">Поддержка Windows Forms была добавлена в .NET Core в версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="842ac-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="842ac-105">В этой статье перечислены критические изменения для Windows Forms, сгруппированные по версии .NET, в которой они появились.</span><span class="sxs-lookup"><span data-stu-id="842ac-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="842ac-106">Если вы обновляете приложение Windows Forms с .NET Framework или с предыдущей версии .NET Core (3.0 или более поздней), эта статья для вас актуальна.</span><span class="sxs-lookup"><span data-stu-id="842ac-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="842ac-107">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="842ac-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="842ac-108">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="842ac-108">Breaking change</span></span> | <span data-ttu-id="842ac-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="842ac-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="842ac-110">Свойству OutputType задано значение WinExe для приложений WPF и WinForms</span><span class="sxs-lookup"><span data-stu-id="842ac-110">OutputType set to WinExe for WPF and WinForms apps</span></span>](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | <span data-ttu-id="842ac-111">5.0</span><span class="sxs-lookup"><span data-stu-id="842ac-111">5.0</span></span> |
| [<span data-ttu-id="842ac-112">API, связанные с DataGridView, теперь вызывают исключение InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="842ac-112">DataGridView-related APIs now throw InvalidOperationException</span></span>](#datagridview-related-apis-now-throw-invalidoperationexception) | <span data-ttu-id="842ac-113">5.0</span><span class="sxs-lookup"><span data-stu-id="842ac-113">5.0</span></span> |
| [<span data-ttu-id="842ac-114">В приложениях WinForms и WPF используется Microsoft.NET.Sdk</span><span class="sxs-lookup"><span data-stu-id="842ac-114">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>](#winforms-and-wpf-apps-use-microsoftnetsdk) | <span data-ttu-id="842ac-115">5.0</span><span class="sxs-lookup"><span data-stu-id="842ac-115">5.0</span></span> |
| [<span data-ttu-id="842ac-116">Удалены элементы управления строкой состояния</span><span class="sxs-lookup"><span data-stu-id="842ac-116">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="842ac-117">5.0</span><span class="sxs-lookup"><span data-stu-id="842ac-117">5.0</span></span> |
| [<span data-ttu-id="842ac-118">Теперь методы WinForms вызывают исключение ArgumentException</span><span class="sxs-lookup"><span data-stu-id="842ac-118">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="842ac-119">5.0</span><span class="sxs-lookup"><span data-stu-id="842ac-119">5.0</span></span> |
| [<span data-ttu-id="842ac-120">Теперь методы WinForms вызывают исключение ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="842ac-120">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="842ac-121">5.0</span><span class="sxs-lookup"><span data-stu-id="842ac-121">5.0</span></span> |
| [<span data-ttu-id="842ac-122">Теперь свойства WinForms вызывают исключение ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="842ac-122">WinForms properties now throw ArgumentOutOfRangeException</span></span>](#winforms-properties-now-throw-argumentoutofrangeexception) | <span data-ttu-id="842ac-123">5.0</span><span class="sxs-lookup"><span data-stu-id="842ac-123">5.0</span></span> |
| [<span data-ttu-id="842ac-124">Удаленные элементы управления</span><span class="sxs-lookup"><span data-stu-id="842ac-124">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="842ac-125">3.1</span><span class="sxs-lookup"><span data-stu-id="842ac-125">3.1</span></span> |
| [<span data-ttu-id="842ac-126">При отображении подсказки не возникает событие CellFormatting</span><span class="sxs-lookup"><span data-stu-id="842ac-126">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="842ac-127">3.1</span><span class="sxs-lookup"><span data-stu-id="842ac-127">3.1</span></span> |
| [<span data-ttu-id="842ac-128">Шрифт Control.DefaultFont изменен на Segoe UI 9 пт</span><span class="sxs-lookup"><span data-stu-id="842ac-128">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="842ac-129">3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-129">3.0</span></span> |
| [<span data-ttu-id="842ac-130">Модернизация FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="842ac-130">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="842ac-131">3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-131">3.0</span></span> |
| [<span data-ttu-id="842ac-132">Из некоторых типов Windows Forms удален атрибут SerializableAttribute</span><span class="sxs-lookup"><span data-stu-id="842ac-132">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="842ac-133">3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-133">3.0</span></span> |
| [<span data-ttu-id="842ac-134">Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается</span><span class="sxs-lookup"><span data-stu-id="842ac-134">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="842ac-135">3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-135">3.0</span></span> |
| [<span data-ttu-id="842ac-136">Параметр совместимости DomainUpDown.UseLegacyScrolling не поддерживается</span><span class="sxs-lookup"><span data-stu-id="842ac-136">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="842ac-137">3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-137">3.0</span></span> |
| [<span data-ttu-id="842ac-138">Параметр совместимости DoNotLoadLatestRichEditControl не поддерживается</span><span class="sxs-lookup"><span data-stu-id="842ac-138">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="842ac-139">3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-139">3.0</span></span> |
| [<span data-ttu-id="842ac-140">Параметр совместимости DoNotSupportSelectAllShortcutInMultilineTextBox не поддерживается</span><span class="sxs-lookup"><span data-stu-id="842ac-140">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="842ac-141">3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-141">3.0</span></span> |
| [<span data-ttu-id="842ac-142">Параметр совместимости DontSupportReentrantFilterMessage не поддерживается</span><span class="sxs-lookup"><span data-stu-id="842ac-142">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="842ac-143">3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-143">3.0</span></span> |
| [<span data-ttu-id="842ac-144">Параметр совместимости EnableVisualStyleValidation не поддерживается</span><span class="sxs-lookup"><span data-stu-id="842ac-144">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="842ac-145">3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-145">3.0</span></span> |
| [<span data-ttu-id="842ac-146">Параметр совместимости UseLegacyContextMenuStripSourceControlValue не поддерживается</span><span class="sxs-lookup"><span data-stu-id="842ac-146">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="842ac-147">3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-147">3.0</span></span> |
| [<span data-ttu-id="842ac-148">Параметр совместимости UseLegacyImages не поддерживается</span><span class="sxs-lookup"><span data-stu-id="842ac-148">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="842ac-149">3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-149">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="842ac-150">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="842ac-150">.NET 5.0</span></span>

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

***

[!INCLUDE [null-owner-causes-invalidoperationexception](../../../includes/core-changes/windowsforms/5.0/null-owner-causes-invalidoperationexception.md)]

***

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

***

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="842ac-151">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="842ac-151">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="842ac-152">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="842ac-152">.NET Core 3.0</span></span>

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

## <a name="see-also"></a><span data-ttu-id="842ac-153">См. также</span><span class="sxs-lookup"><span data-stu-id="842ac-153">See also</span></span>

- [<span data-ttu-id="842ac-154">Перенос приложения Windows Forms в .NET Core</span><span class="sxs-lookup"><span data-stu-id="842ac-154">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)

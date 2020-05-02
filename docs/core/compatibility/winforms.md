---
title: Критические изменения в Windows Forms
description: Список критических изменений в Windows Forms для .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: 75d369c7fb999da81a50fe46716e125c3840eb7a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158441"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="376e5-103">Критические изменения в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="376e5-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="376e5-104">Поддержка Windows Forms была добавлена в .NET Core в версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="376e5-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="376e5-105">В этой статье перечислены критические изменения для Windows Forms, сгруппированные по версии .NET Core, в которой они появились.</span><span class="sxs-lookup"><span data-stu-id="376e5-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="376e5-106">Если вы обновляете приложение Windows Forms с .NET Framework или с предыдущей версии .NET Core (3.0 или более поздней), эта статья для вас актуальна.</span><span class="sxs-lookup"><span data-stu-id="376e5-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="376e5-107">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="376e5-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="376e5-108">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="376e5-108">Breaking change</span></span> | <span data-ttu-id="376e5-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="376e5-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="376e5-110">Удалены элементы управления строкой состояния</span><span class="sxs-lookup"><span data-stu-id="376e5-110">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="376e5-111">5.0</span><span class="sxs-lookup"><span data-stu-id="376e5-111">5.0</span></span> |
| [<span data-ttu-id="376e5-112">Теперь методы WinForms вызывают исключение ArgumentException</span><span class="sxs-lookup"><span data-stu-id="376e5-112">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="376e5-113">5.0</span><span class="sxs-lookup"><span data-stu-id="376e5-113">5.0</span></span> |
| [<span data-ttu-id="376e5-114">Теперь методы WinForms вызывают исключение ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="376e5-114">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="376e5-115">5.0</span><span class="sxs-lookup"><span data-stu-id="376e5-115">5.0</span></span> |
| [<span data-ttu-id="376e5-116">Удаленные элементы управления</span><span class="sxs-lookup"><span data-stu-id="376e5-116">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="376e5-117">3.1</span><span class="sxs-lookup"><span data-stu-id="376e5-117">3.1</span></span> |
| [<span data-ttu-id="376e5-118">При отображении подсказки не возникает событие CellFormatting</span><span class="sxs-lookup"><span data-stu-id="376e5-118">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="376e5-119">3.1</span><span class="sxs-lookup"><span data-stu-id="376e5-119">3.1</span></span> |
| [<span data-ttu-id="376e5-120">Шрифт Control.DefaultFont изменен на Segoe UI 9 пт</span><span class="sxs-lookup"><span data-stu-id="376e5-120">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="376e5-121">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-121">3.0</span></span> |
| [<span data-ttu-id="376e5-122">Модернизация FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="376e5-122">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="376e5-123">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-123">3.0</span></span> |
| [<span data-ttu-id="376e5-124">Из некоторых типов Windows Forms удален атрибут SerializableAttribute</span><span class="sxs-lookup"><span data-stu-id="376e5-124">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="376e5-125">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-125">3.0</span></span> |
| [<span data-ttu-id="376e5-126">Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается</span><span class="sxs-lookup"><span data-stu-id="376e5-126">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="376e5-127">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-127">3.0</span></span> |
| [<span data-ttu-id="376e5-128">Параметр совместимости DomainUpDown.UseLegacyScrolling не поддерживается</span><span class="sxs-lookup"><span data-stu-id="376e5-128">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="376e5-129">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-129">3.0</span></span> |
| [<span data-ttu-id="376e5-130">Параметр совместимости DoNotLoadLatestRichEditControl не поддерживается</span><span class="sxs-lookup"><span data-stu-id="376e5-130">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="376e5-131">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-131">3.0</span></span> |
| [<span data-ttu-id="376e5-132">Параметр совместимости DoNotSupportSelectAllShortcutInMultilineTextBox не поддерживается</span><span class="sxs-lookup"><span data-stu-id="376e5-132">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="376e5-133">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-133">3.0</span></span> |
| [<span data-ttu-id="376e5-134">Параметр совместимости DontSupportReentrantFilterMessage не поддерживается</span><span class="sxs-lookup"><span data-stu-id="376e5-134">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="376e5-135">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-135">3.0</span></span> |
| [<span data-ttu-id="376e5-136">Параметр совместимости EnableVisualStyleValidation не поддерживается</span><span class="sxs-lookup"><span data-stu-id="376e5-136">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="376e5-137">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-137">3.0</span></span> |
| [<span data-ttu-id="376e5-138">Параметр совместимости UseLegacyContextMenuStripSourceControlValue не поддерживается</span><span class="sxs-lookup"><span data-stu-id="376e5-138">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="376e5-139">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-139">3.0</span></span> |
| [<span data-ttu-id="376e5-140">Параметр совместимости UseLegacyImages не поддерживается</span><span class="sxs-lookup"><span data-stu-id="376e5-140">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="376e5-141">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-141">3.0</span></span> |
| [<span data-ttu-id="376e5-142">Изменение доступа для AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="376e5-142">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem) | <span data-ttu-id="376e5-143">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-143">3.0</span></span> |
| [<span data-ttu-id="376e5-144">Из Windows Forms удалены дублирующиеся API</span><span class="sxs-lookup"><span data-stu-id="376e5-144">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms) | <span data-ttu-id="376e5-145">3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-145">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="376e5-146">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="376e5-146">.NET 5.0</span></span>

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="376e5-147">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="376e5-147">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="376e5-148">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="376e5-148">.NET Core 3.0</span></span>

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

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a><span data-ttu-id="376e5-149">См. также</span><span class="sxs-lookup"><span data-stu-id="376e5-149">See also</span></span>

- [<span data-ttu-id="376e5-150">Перенос приложения Windows Forms в .NET Core</span><span class="sxs-lookup"><span data-stu-id="376e5-150">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)

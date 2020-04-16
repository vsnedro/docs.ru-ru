---
title: Критические изменения в Windows Forms
description: Список критических изменений в Windows Forms для .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: 25c568a8a0092a9c4874419c64c7dcebea4dce9e
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888146"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="ee903-103">Критические изменения в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee903-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="ee903-104">Поддержка Windows Forms была добавлена в .NET Core в версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="ee903-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="ee903-105">В этой статье перечислены критические изменения для Windows Forms, сгруппированные по версии .NET Core, в которой они появились.</span><span class="sxs-lookup"><span data-stu-id="ee903-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="ee903-106">Если вы обновляете приложение Windows Forms с .NET Framework или с предыдущей версии .NET Core (3.0 или более поздней), эта статья для вас актуальна.</span><span class="sxs-lookup"><span data-stu-id="ee903-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="ee903-107">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="ee903-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="ee903-108">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="ee903-108">Breaking change</span></span> | <span data-ttu-id="ee903-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="ee903-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="ee903-110">Теперь API WinForms выдают исключение ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="ee903-110">WinForms APIs now throw ArgumentNullException</span></span>](#winforms-apis-now-throw-argumentnullexception) | <span data-ttu-id="ee903-111">5.0</span><span class="sxs-lookup"><span data-stu-id="ee903-111">5.0</span></span> |
| [<span data-ttu-id="ee903-112">Удаленные элементы управления</span><span class="sxs-lookup"><span data-stu-id="ee903-112">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="ee903-113">3.1</span><span class="sxs-lookup"><span data-stu-id="ee903-113">3.1</span></span> |
| [<span data-ttu-id="ee903-114">При отображении подсказки не возникает событие CellFormatting</span><span class="sxs-lookup"><span data-stu-id="ee903-114">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="ee903-115">3.1</span><span class="sxs-lookup"><span data-stu-id="ee903-115">3.1</span></span> |
| [<span data-ttu-id="ee903-116">Шрифт Control.DefaultFont изменен на Segoe UI 9 пт</span><span class="sxs-lookup"><span data-stu-id="ee903-116">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="ee903-117">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-117">3.0</span></span> |
| [<span data-ttu-id="ee903-118">Модернизация FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="ee903-118">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="ee903-119">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-119">3.0</span></span> |
| [<span data-ttu-id="ee903-120">Из некоторых типов Windows Forms удален атрибут SerializableAttribute</span><span class="sxs-lookup"><span data-stu-id="ee903-120">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="ee903-121">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-121">3.0</span></span> |
| [<span data-ttu-id="ee903-122">Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается</span><span class="sxs-lookup"><span data-stu-id="ee903-122">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="ee903-123">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-123">3.0</span></span> |
| [<span data-ttu-id="ee903-124">Параметр совместимости DomainUpDown.UseLegacyScrolling не поддерживается</span><span class="sxs-lookup"><span data-stu-id="ee903-124">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="ee903-125">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-125">3.0</span></span> |
| [<span data-ttu-id="ee903-126">Параметр совместимости DoNotLoadLatestRichEditControl не поддерживается</span><span class="sxs-lookup"><span data-stu-id="ee903-126">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="ee903-127">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-127">3.0</span></span> |
| [<span data-ttu-id="ee903-128">Параметр совместимости DoNotSupportSelectAllShortcutInMultilineTextBox не поддерживается</span><span class="sxs-lookup"><span data-stu-id="ee903-128">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="ee903-129">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-129">3.0</span></span> |
| [<span data-ttu-id="ee903-130">Параметр совместимости DontSupportReentrantFilterMessage не поддерживается</span><span class="sxs-lookup"><span data-stu-id="ee903-130">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="ee903-131">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-131">3.0</span></span> |
| [<span data-ttu-id="ee903-132">Параметр совместимости EnableVisualStyleValidation не поддерживается</span><span class="sxs-lookup"><span data-stu-id="ee903-132">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="ee903-133">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-133">3.0</span></span> |
| [<span data-ttu-id="ee903-134">Параметр совместимости UseLegacyContextMenuStripSourceControlValue не поддерживается</span><span class="sxs-lookup"><span data-stu-id="ee903-134">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="ee903-135">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-135">3.0</span></span> |
| [<span data-ttu-id="ee903-136">Параметр совместимости UseLegacyImages не поддерживается</span><span class="sxs-lookup"><span data-stu-id="ee903-136">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="ee903-137">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-137">3.0</span></span> |
| [<span data-ttu-id="ee903-138">Изменение доступа для AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="ee903-138">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem) | <span data-ttu-id="ee903-139">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-139">3.0</span></span> |
| [<span data-ttu-id="ee903-140">Из Windows Forms удалены дублирующиеся API</span><span class="sxs-lookup"><span data-stu-id="ee903-140">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms) | <span data-ttu-id="ee903-141">3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-141">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="ee903-142">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ee903-142">.NET 5.0</span></span>

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="ee903-143">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="ee903-143">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="ee903-144">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ee903-144">.NET Core 3.0</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ee903-145">См. также</span><span class="sxs-lookup"><span data-stu-id="ee903-145">See also</span></span>

- [<span data-ttu-id="ee903-146">Перенос приложения Windows Forms в .NET Core</span><span class="sxs-lookup"><span data-stu-id="ee903-146">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)

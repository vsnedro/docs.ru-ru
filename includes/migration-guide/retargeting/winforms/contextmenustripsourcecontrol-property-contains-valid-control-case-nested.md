---
ms.openlocfilehash: 97299ddb9bee89c792ddb3d2b9c37516180996f7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614881"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a><span data-ttu-id="58db3-101">Свойство ContextMenuStrip.SourceControl содержит допустимый элемент управления при наличии вложенных объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="58db3-101">ContextMenuStrip.SourceControl property contains a valid control in the case of nested ToolStripMenuItems</span></span>

#### <a name="details"></a><span data-ttu-id="58db3-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="58db3-102">Details</span></span>

<span data-ttu-id="58db3-103">В .NET Framework 4.7.1 и предыдущих версиях свойство <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> некорректно возвращает значение null, когда пользователь открывает меню из вложенных элементов управления <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="58db3-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property incorrectly returns null when the user opens the menu from nested <xref:System.Windows.Forms.ToolStripMenuItem> controls.</span></span> <span data-ttu-id="58db3-104">В платформе .NET Framework 4.7.2 и более поздних версий для свойства <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> всегда задана фактическая система управления версиями.</span><span class="sxs-lookup"><span data-stu-id="58db3-104">In the .NET Framework 4.7.2 and later, <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> property is always set to the actual source control.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="58db3-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="58db3-105">Suggestion</span></span>

<span data-ttu-id="58db3-106">**Как принять или отклонить изменения** Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.2 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="58db3-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="58db3-107">В приложении эти изменения можно использовать одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="58db3-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="58db3-108">Приложение предназначено для платформы .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="58db3-108">It targets the .NET Framework 4.7.2.</span></span> <span data-ttu-id="58db3-109">Это изменение включено по умолчанию для приложений Windows Forms, нацеленных на .NET Framework 4.7.2 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="58db3-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="58db3-110">Оно нацелено на .NET Framework 4.7.1 и более ранние версии платформы и позволяет отказаться от функций специальных возможностей предыдущих версий путем добавления [переключателя AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) в раздел `<runtime>` файла конфигурации приложения и получения значения `false`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="58db3-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

<span data-ttu-id="58db3-111">В приложениях, предназначенных для .NET Framework 4.7.2 или более поздней версии, где требуется сохранить предыдущие функции, можно выбрать использование прежнего значения системы управления версиями, явно установив этот переключатель AppContext в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="58db3-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to the use of the legacy source control value by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="58db3-112">name</span><span class="sxs-lookup"><span data-stu-id="58db3-112">Name</span></span>    | <span data-ttu-id="58db3-113">Значение</span><span class="sxs-lookup"><span data-stu-id="58db3-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="58db3-114">Область</span><span class="sxs-lookup"><span data-stu-id="58db3-114">Scope</span></span>   | <span data-ttu-id="58db3-115">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="58db3-115">Edge</span></span>        |
| <span data-ttu-id="58db3-116">Version</span><span class="sxs-lookup"><span data-stu-id="58db3-116">Version</span></span> | <span data-ttu-id="58db3-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="58db3-117">4.7.2</span></span>       |
| <span data-ttu-id="58db3-118">Type</span><span class="sxs-lookup"><span data-stu-id="58db3-118">Type</span></span>    | <span data-ttu-id="58db3-119">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="58db3-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="58db3-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="58db3-120">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

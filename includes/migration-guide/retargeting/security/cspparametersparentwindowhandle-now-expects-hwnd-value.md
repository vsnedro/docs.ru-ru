---
ms.openlocfilehash: 4b5c886ad35afbbf0a68e03b3174ab9ea1f5524f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614765"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a><span data-ttu-id="71e1e-101">CspParameters.ParentWindowHandle теперь ожидает значение HWND</span><span class="sxs-lookup"><span data-stu-id="71e1e-101">CspParameters.ParentWindowHandle now expects HWND value</span></span>

#### <a name="details"></a><span data-ttu-id="71e1e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="71e1e-102">Details</span></span>

<span data-ttu-id="71e1e-103">Значение <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>, которое появилось в .NET Framework 2.0, позволяет приложению зарегистрировать значение дескриптора родительского окна таким образом, что любой пользовательский интерфейс, необходимый для доступа к ключу (например, запрос ПИН-кода или окно согласия), будет открываться в режиме модального дочернего окна для указанного окна. Начиная с приложений, предназначенных для .NET Framework 4.7, приложение Windows Forms может задавать свойство <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> с кодом, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="71e1e-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> value, introduced in .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or consent dialog) opens as a modal child to the specified window.Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="71e1e-104">В предыдущих версиях платформы .NET Framework ожидалось значение <xref:System.IntPtr?displayProperty=fullName>, указывающее расположение в памяти, где находится значение [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND).</span><span class="sxs-lookup"><span data-stu-id="71e1e-104">In previous versions of the .NET Framework, the value was expected to be an <xref:System.IntPtr?displayProperty=fullName> representing a location in memory where the [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND) value resided.</span></span> <span data-ttu-id="71e1e-105">В Windows 7 и более ранних версиях задание свойству значения form.Handle ни на что не влияло, но в Windows 8 и более поздних версиях оно приводит к исключению &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> с сообщением "Неверный параметр".&quot;</span><span class="sxs-lookup"><span data-stu-id="71e1e-105">Setting the property to form.Handle on Windows 7 and earlier versions had no effect, but on Windows 8 and later versions, it results in a &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: The parameter is incorrect.&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="71e1e-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="71e1e-106">Suggestion</span></span>

<span data-ttu-id="71e1e-107">В приложениях, предназначенных для .NET Framework 4.7 или более поздней версии, в которых нужно зарегистрировать связь с родительским окном, рекомендуется использовать упрощенную форму:</span><span class="sxs-lookup"><span data-stu-id="71e1e-107">Applications targeting .NET Framework 4.7 or higher wishing to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="71e1e-108">Пользователи, которые определили, что правильным значением для передачи был адрес области памяти, в которой содержалось значение `form.Handle`, могут отказаться от этого изменения в поведении, установив для параметра AppContext `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` значение `true`:</span><span class="sxs-lookup"><span data-stu-id="71e1e-108">Users who had identified that the correct value to pass was the address of a memory location which held the value `form.Handle` can opt out of the behavior change by setting the AppContext switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="71e1e-109">Путем программной установки параметров совместимости в AppContext, как описано [здесь](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span><span class="sxs-lookup"><span data-stu-id="71e1e-109">By programmatically setting compat switches on the AppContext, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="71e1e-110">путем добавления следующей строки в раздел `<runtime>` файла app.config:</span><span class="sxs-lookup"><span data-stu-id="71e1e-110">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<runtime>
 <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
</runtime>
```

<span data-ttu-id="71e1e-111">Пользователи, которые хотят использовать новое поведение в среде выполнения .NET Framework 4.7, когда приложения загружаются в более ранних версиях платформы .NET Framework, могут задать переключателю AppContext значение `false`.</span><span class="sxs-lookup"><span data-stu-id="71e1e-111">Conversely, users who wish to opt in to the new behavior on the .NET Framework 4.7 runtime when the application loads under older .NET Framework versions can set the AppContext switch to `false`.</span></span>

| <span data-ttu-id="71e1e-112">name</span><span class="sxs-lookup"><span data-stu-id="71e1e-112">Name</span></span>    | <span data-ttu-id="71e1e-113">Значение</span><span class="sxs-lookup"><span data-stu-id="71e1e-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="71e1e-114">Область</span><span class="sxs-lookup"><span data-stu-id="71e1e-114">Scope</span></span>   | <span data-ttu-id="71e1e-115">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="71e1e-115">Minor</span></span>       |
| <span data-ttu-id="71e1e-116">Version</span><span class="sxs-lookup"><span data-stu-id="71e1e-116">Version</span></span> | <span data-ttu-id="71e1e-117">4.7</span><span class="sxs-lookup"><span data-stu-id="71e1e-117">4.7</span></span>         |
| <span data-ttu-id="71e1e-118">Type</span><span class="sxs-lookup"><span data-stu-id="71e1e-118">Type</span></span>    | <span data-ttu-id="71e1e-119">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="71e1e-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="71e1e-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="71e1e-120">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType>

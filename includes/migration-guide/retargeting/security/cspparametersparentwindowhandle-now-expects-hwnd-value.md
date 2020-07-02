---
ms.openlocfilehash: 4b5c886ad35afbbf0a68e03b3174ab9ea1f5524f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614765"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a>CspParameters.ParentWindowHandle теперь ожидает значение HWND

#### <a name="details"></a>Подробнее

Значение <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>, которое появилось в .NET Framework 2.0, позволяет приложению зарегистрировать значение дескриптора родительского окна таким образом, что любой пользовательский интерфейс, необходимый для доступа к ключу (например, запрос ПИН-кода или окно согласия), будет открываться в режиме модального дочернего окна для указанного окна. Начиная с приложений, предназначенных для .NET Framework 4.7, приложение Windows Forms может задавать свойство <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> с кодом, как в следующем примере:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

В предыдущих версиях платформы .NET Framework ожидалось значение <xref:System.IntPtr?displayProperty=fullName>, указывающее расположение в памяти, где находится значение [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND). В Windows 7 и более ранних версиях задание свойству значения form.Handle ни на что не влияло, но в Windows 8 и более поздних версиях оно приводит к исключению &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> с сообщением "Неверный параметр".&quot;

#### <a name="suggestion"></a>Предложение

В приложениях, предназначенных для .NET Framework 4.7 или более поздней версии, в которых нужно зарегистрировать связь с родительским окном, рекомендуется использовать упрощенную форму:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

Пользователи, которые определили, что правильным значением для передачи был адрес области памяти, в которой содержалось значение `form.Handle`, могут отказаться от этого изменения в поведении, установив для параметра AppContext `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` значение `true`:

- Путем программной установки параметров совместимости в AppContext, как описано [здесь](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).
- путем добавления следующей строки в раздел `<runtime>` файла app.config:

```xml
<runtime>
 <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
</runtime>
```

Пользователи, которые хотят использовать новое поведение в среде выполнения .NET Framework 4.7, когда приложения загружаются в более ранних версиях платформы .NET Framework, могут задать переключателю AppContext значение `false`.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.7         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType>

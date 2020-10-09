---
ms.openlocfilehash: 8693c1fdef5fa194b16127d4f1dd87e23ad68f2d
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438031"
---
### <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a>Приведение вызываемой оболочки времени выполнения к интерфейсу `InterfaceIsIInspectable` вызывает исключение PlatformNotSupportedException

Приведение вызываемой оболочки времени выполнения (RCW) к интерфейсу, помеченному как <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, теперь вызывает исключение <xref:System.PlatformNotSupportedException>. Это изменение соответствует [удалению поддержки WinRT из .NET](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).

#### <a name="version-introduced"></a>Представленная версия

5.0 RC2

#### <a name="change-description"></a>Описание изменений

В версиях .NET до .NET 5.0 (предварительная версия 6) приведение RCW к интерфейсу, помеченному как <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, работает должным образом. В версиях .NET 5.0 (предварительные версии 6–8 и RC1) можно успешно привести RCW к интерфейсу <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>. Однако при выполнении методов в интерфейсе могут возникнуть нарушения прав доступа, так как базовая поддержка в среде выполнения [была удалена в .NET 5.0 (предварительная версия 6)](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net).

В .NET 5.0 RC2 и более поздних версиях приведение RCW к интерфейсу, помеченному как <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, вызывает исключение <xref:System.PlatformNotSupportedException> во время приведения.

#### <a name="reason-for-change"></a>Причина изменения

Поддержка <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> была [удалена в предыдущей предварительной версии .NET 5.0](../../../../docs/core/compatibility/interop.md#built-in-support-for-winrt-is-removed-from-net). Однако приведение к интерфейсу <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> было пропущено по ошибке. Поскольку базовая поддержка в среде выполнения больше не существует, выдача исключения <xref:System.PlatformNotSupportedException> обеспечивает корректную обработку сбоя. Создание исключения также позволяет легче обнаружить, что эта функция больше не поддерживается.

#### <a name="recommended-action"></a>Рекомендованное действие

- Если вы можете определить интерфейс в файле метаданных среды выполнения Windows (WinMD), используйте вместо этого средство C#/WinRT.

- В противном случае пометьте интерфейс как <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> вместо <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> и добавьте три фиктивные записи в начало интерфейса для методов <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>. Фрагмент кода приведен ниже.

  ```csharp
  [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
  interface IMine
  {
      // Do not call these three methods.
      // They're exclusively to fill in the slots in the vtable.
      void GetIIdsSlot();
      void GetRuntimeClassNameSlot();
      void GetTrustLevelSlot();

      // The original members of the IMine interface go here.
      ...
  }
  ```

#### <a name="category"></a>Категория

Interop

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

-->

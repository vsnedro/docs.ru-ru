---
ms.openlocfilehash: 1ea2d70a7cfe04cc4c4b9b58ea6bb6fa0226b245
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721749"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a>Изменение доступа для AccessibleObject.RuntimeIDFirstItem

Начиная с .NET Core 3.0 RC1 (релиз-кандидат 1) специальные возможности `AccessibleObject.RuntimeIDFirstItem` изменились с `protected` на `internal`.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Core 3.0 (предварительная версия 4) поле `AccessibleObject.RuntimeIDFirstItem` было `protected`. Начиная с версии .NET Core 3.0 RC1 (релиз-кандидат 1) оно изменилось с `protected` на `internal` в соответствии со специальными возможностями этого поля в .NET Framework.

#### <a name="version-introduced"></a>Представленная версия

3.0 RC1 (релиз-кандидат 1)

#### <a name="recommended-action"></a>Рекомендованное действие

Это изменение может повлиять на вас, если вы разработали приложение .NET Core с типом, который является производным от <xref:System.Windows.Forms.AccessibleObject> и обращается к полю `RuntimeIDFirstItem`. В этом случае локальную константу можно определить следующим образом:

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- Невозможно обнаружить с помощью анализа API.

<!-- 

#### Affected APIs

- Not detectable via API analysis.

-->

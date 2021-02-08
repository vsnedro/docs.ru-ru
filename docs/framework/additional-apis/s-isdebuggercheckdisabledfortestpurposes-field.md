---
description: 'Дополнительные сведения о: s_isDebuggerCheckDisabledForTestPurposes поле'
title: s_isDebuggerCheckDisabledForTestPurposes поле
ms.date: 03/30/2017
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: a71235c13a7a35872bcf5374be8077bafad5ff9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802662"
---
# <a name="s_isdebuggercheckdisabledfortestpurposes-field"></a>s_isDebuggerCheckDisabledForTestPurposes поле

Это частное поле в `System.Windows.Diagnostics.VisualDiagnostics` классе используется в Visual Studio для определения, будет ли выполняться внутренняя проверка активного отладчика.

## <a name="syntax"></a>Синтаксис

```csharp
private static bool s_isDebuggerCheckDisabledForTestPurposes
```

> [!WARNING]
> API-интерфейсы в `System.Windows.Diagnostics.VisualDiagnostics` классе доступны только в том случае, если приложение выполняется в отладчике. Задайте для значение, чтобы `s_isDebuggerCheckDisabledForTestPurposes` `true` получить доступ к API за пределами отладчика.
>
> Корпорация Майкрософт не поддерживает использование этого поля в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Windows.Diagnostics>

**Сборка:** PresentationCore (в PresentationCore.dll)

**Платформа .NET Framework версии:** Доступно с 4,6.

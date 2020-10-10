---
title: Метод Финдхеадербиколумн (System. Windows. Controls. Гридвиевхеадерровпресентер)
description: Сведения о закрытом методе WPF с именем Финдхеадербиколумн.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.FindHeaderByColumn
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 88ed2928f86602d1078488354de6d5267c0311f5
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877801"
---
# <a name="findheaderbycolumn-method"></a>Метод Финдхеадербиколумн

Находит заголовок столбца для указанного столбца в визуальном дереве.

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> Этот метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="parameters"></a>Параметры

`column` <xref:System.Windows.Controls.GridViewColumn>\
Столбец, заголовок которого должен быть найден и возвращен.

## <a name="return-value"></a>Возвращаемое значение

<xref:System.Windows.Controls.GridViewColumnHeader>\
Заголовок указанного столбца или `null` значение, если указанный столбец не существует.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Windows.Controls>

**Сборка:** PresentationFramework.dll

## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>

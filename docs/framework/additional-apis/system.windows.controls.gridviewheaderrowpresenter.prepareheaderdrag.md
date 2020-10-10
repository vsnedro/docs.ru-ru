---
title: Метод Препарехеадердраг (System. Windows. Controls. Гридвиевхеадерровпресентер)
description: Сведения о закрытом методе WPF с именем Препарехеадердраг.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.PrepareHeaderDrag
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 6d806b8a50de3234cd04198f4ab86621dcd6ede1
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877792"
---
# <a name="prepareheaderdrag-method"></a>Метод Препарехеадердраг

Подготавливает указанный заголовок столбца для изменения порядка.

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> Этот метод является закрытым и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="parameters"></a>Параметры

`header` <xref:System.Windows.Controls.GridViewColumnHeader>\
Заголовок столбца для подготовки к переупорядочению.

`pos` <xref:System.Windows.Point>\
Позицию относительно <xref:System.Windows.Controls.GridViewHeaderRowPresenter> , где начинается перетаскивание.

`relativePos` <xref:System.Windows.Point>\
Позицию относительно `header` , где начинается перетаскивание.

`cancelInvoke` <xref:System.Boolean>\
`true` значение для отмены изменения порядка; в противном случае — `false` .

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Windows.Controls>

**Сборка:** PresentationFramework.dll

## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>

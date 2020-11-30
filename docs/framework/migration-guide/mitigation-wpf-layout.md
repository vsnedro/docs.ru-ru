---
title: Устранение рисков. Макет WPF
description: Узнайте, как устранить проблемы, возникающие в результате изменений в макете элементов управления WPF, таких как размещение объекта, перемещаемого на один пиксель.
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: caed758f6e86a1e2bee255c2f29ca3160b327e17
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244084"
---
# <a name="mitigation-wpf-layout"></a>Устранение рисков. Макет WPF

Макет элементов управления WPF может немного изменяться.  
  
## <a name="impact"></a>Последствия  

 В результате этого изменения:  
  
- ширина или высота элементов может увеличиться или уменьшиться максимум на один пиксель;  
  
- расположение объекта может измениться максимум на один пиксель;  
  
- выровненные по центру элементы могут сместиться по вертикали или горизонтали максимум на один пиксель.  
  
 По умолчанию новый макет включен только для приложений, предназначенных для .NET Framework 4.6.  
  
## <a name="mitigation"></a>Устранение рисков  

 Поскольку это изменение, как правило, приводит к устранению обрезки правых или нижних элементов управления WPF при высоком разрешении, для приложений, предназначенных для более ранних версий .NET Framework, но выполняющихся в .NET Framework 4.6, можно выбрать это новое поведение, добавив следующую строку в раздел `<runtime>` файла app.config.  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 Для приложений, предназначенных для .NET Framework 4.6, для которых требуется задать отрисовку элементов управления WPF с помощью прежнего алгоритма макета, можно добавить следующую строку в раздел `<runtime>` файла app.config.  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a>См. также

- [Совместимость приложений](application-compatibility.md)

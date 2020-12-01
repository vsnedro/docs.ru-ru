---
title: Устранение рисков. Проверки двоеточий в путях
description: Узнайте об изменениях, внесенных в .NET Framework 4.6.2, для поддержки проверки правильности синтаксиса разделителя дисков (двоеточия).
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: 03f1c7249549aae7e3bef986c97fb5f320fbeb2f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283462"
---
# <a name="mitigation-path-colon-checks"></a>Устранение рисков. Проверки двоеточий в путях

Начиная с приложений, ориентированных на .NET Framework 4.6.2, выполнен ряд изменений для поддержки ранее не поддерживаемых путей (с точки зрения и длины, и формата). В частности, усовершенствованы проверки правильности синтаксиса разделителя диска (двоеточия).  
  
## <a name="impact"></a>Последствия  

 Эти изменения блокируют некоторые пути URI, которые ранее поддерживались методами <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>.  
  
## <a name="mitigation"></a>Устранение рисков  

 Чтобы обойти проблему с ранее допустимым путем, который больше не поддерживается методами <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, можно сделать следующее:  
  
- Вручную удалить схему из URL-адреса. Например, удалить `file://` из URL-адреса.  
  
- передать код URI в конструктор <xref:System.Uri> и получить значение свойства <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>;  
  
- отказаться от новой нормализации путей, установив для параметра `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> значение `true`.  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
    </runtime>  
    ```  
  
## <a name="see-also"></a>См. также

- [Совместимость приложений](application-compatibility.md)

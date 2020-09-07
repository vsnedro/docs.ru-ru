---
ms.openlocfilehash: 086dac69d085d070511fcfd5820bd2644ee4598e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497021"
---
### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>Перегрузки Marshal.SizeOf и Marshal.PtrToStructure нарушают работу динамического кода

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.5.1 динамическая привязка к методам <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)> или <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> (с помощью Windows PowerShell, IronPython или ключевого слова dynamic в C#) может привести к исключению <code>MethodInvocationExceptions</code>, так как были добавлены новые перегрузки этих методов, которые могут быть неоднозначными для обработчиков скриптов.

#### <a name="suggestion"></a>Предложение

Обновите скрипты для четкого указания используемой перегрузки. Обычно нужно явным образом привести параметры типа метода как <xref:System.Type>. Дополнительные сведения и возможные решения этой проблемы см. по [этой ссылке](https://support.microsoft.com/kb/2909958/).

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5.1|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->

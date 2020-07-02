---
ms.openlocfilehash: 5d5423d18091545ad9d50325900f5a9a4fff6dd9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622115"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a>Исправлено зависание, если ListBox содержит повторяющиеся типы значений

#### <a name="details"></a>Подробнее

Устранена проблема, при которой виртуализация <xref:System.Windows.Controls.ItemsControl> приводила к зависанию при прокрутке, когда коллекция элементов содержит повторяющиеся объекты типов значений.

| name    | Значение       |
|:--------|:------------|
| Область   |Значительно|
|Version|4.8|
|Type|Среда выполнения|

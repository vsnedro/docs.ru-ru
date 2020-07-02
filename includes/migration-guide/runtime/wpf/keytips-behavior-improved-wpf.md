---
ms.openlocfilehash: 9659068304eb208fd6a0a753273453bc669fbc56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621403"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Улучшенные подсказки клавиш в WPF

#### <a name="details"></a>Подробнее

Поведение подсказок клавиш было изменено и теперь совпадает с поведением в проводнике и Microsoft Word. WPF проверяет, включено ли состояние подсказки клавиш в случае, если нажата <xref:System.Windows.Input.KeyEventArgs.SystemKey> (в частности, <xref:System.Windows.Input.Key> или <xref:System.Windows.Input.Key.F11>), и обрабатывает клавиши подсказок соответствующим образом. Подсказки клавиш теперь закрывают меню, даже если оно открыто с помощью мыши.

#### <a name="suggestion"></a>Предложение

Н/Д

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.7.2|
|Type|Среда выполнения|

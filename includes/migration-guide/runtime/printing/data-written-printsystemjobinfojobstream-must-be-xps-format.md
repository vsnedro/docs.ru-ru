---
ms.openlocfilehash: a007022bf32ffe76861f6f9016a7edace17b0f61
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620643"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a>Данные, записанные в PrintSystemJobInfo.JobStream, должны иметь формат XPS

#### <a name="details"></a>Подробнее

Свойство <xref:System.Printing.PrintSystemJobInfo.JobStream> предоставляет поток задания печати. Пользователь может отправить необработанные данные в компоненты печати базовой операционной системы путем записи в этот поток. Начиная с .NET Framework 4.5 в Windows 8 и более поздних версиях операционной системы Windows данные, которые записываются в этот поток, должны быть в формате XPS, как поток пакета.

#### <a name="suggestion"></a>Предложение

Для вывода содержимого печати выполните одно из следующих действий.<ul><li>Используйте класс <xref:System.Windows.Xps.XpsDocumentWriter> класса для вывода содержимого печати. Это рекомендуемый вариант.</li><li>Убедитесь, что данные, отправляемые в поток, возвращенный свойством <xref:System.Printing.PrintSystemJobInfo.JobStream>, находятся в формате XPS, как поток пакета.</li></ul>

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType></li></ul>|

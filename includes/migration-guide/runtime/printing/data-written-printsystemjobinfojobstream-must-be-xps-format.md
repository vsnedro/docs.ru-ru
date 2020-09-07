---
ms.openlocfilehash: 19be8a7755d9b238ab6507eaa73319bddf39faa3
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496924"
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
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Printing.PrintSystemJobInfo.JobStream`

-->

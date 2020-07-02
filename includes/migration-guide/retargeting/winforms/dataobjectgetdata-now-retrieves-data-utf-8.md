---
ms.openlocfilehash: 3f330d5e601d599231ef0336b785e677fe1d114e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616082"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a>DataObject.GetData теперь получает данные в кодировке UTF-8

#### <a name="details"></a>Подробнее

В приложениях, предназначенных для .NET Framework 4 или выполняющихся в .NET Framework 4.5.1 или более ранних версий, `DataObject.GetData` получает HTML-данные в виде строки ASCII. В результате символы, не относящиеся к ASCII (т. е. символы с кодами ASCII больше 0x7F), представляются двумя случайными символами.<p/>Для приложений, предназначенных для NET Framework 4.5 и более поздней версии и выполняемых в .NET Framework 4.5.2, `DataObject.GetData` получает HTML-данные в формате UTF-8, который правильно представляет символы с кодами более 0x7F.

#### <a name="suggestion"></a>Предложение

Если реализован обходной путь для проблемы с кодировкой HTML-строк (например, явная кодировка HTML-строки, полученной из буфера обмена, путем ее передачи в метод <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>), и выполняется изменение целевой платформы приложения с версии 4 на версию 4.5, этот обходной путь необходимо удалить. Если по какой-либо причине требуется старое поведение, для приложения можно выбрать целевую платформу .NET Framework 4.0.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.5.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType>

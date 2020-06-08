---
title: Преобразование типов .NET Framework в строки
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: d232fb0e3ea4cf3189294d6e6f43ae9270417407
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287822"
---
# <a name="converting-net-framework-types-to-strings"></a>Преобразование типов .NET Framework в строки
Чтобы преобразовать тип .NET Framework в строку, используйте метод **ToString**. Метод **ToString** возвращает символьное представление переданного типа. В следующей таблице приведен список типов платформы .NET Framework, которые возвращают строку в формате, сопоставленном со спецификациями XSD.  
  
|Тип платформы .NET Framework|Возвращаемое строковое значение|  
|-------------------------|--------------------------|  
|логический|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|Используется формат гггг-ММ-ддТЧЧ:мм:ссzzzzzz и его подмножества.|  
|Временной диапазон|Используется формат PnYnMnTnHnMnS. Например, значение `P2Y10M15DT10H30M20S` соответствует длительности в 2 года, 10 месяцев, 15 дней, 10 часов, 30 минут и 20 секунд.|  
  
## <a name="see-also"></a>См. также

- [Преобразование типов XML-данных](conversion-of-xml-data-types.md)
- [Преобразование строк в типы данных .NET Framework](converting-strings-to-dotnet-data-types.md)

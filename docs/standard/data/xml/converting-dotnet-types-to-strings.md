---
title: Преобразование типов .NET в строки
ms.date: 03/30/2017
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: 9744224b4346b865a112b0eb6957f12553e1ec5f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830991"
---
# <a name="convert-net-types-to-strings"></a>Преобразование типов .NET в строки

Чтобы преобразовать тип .NET в строку, используйте метод **ToString**. Метод **ToString** возвращает символьное представление переданного типа. В таблице ниже приведен список типов .NET, которые возвращают строку в формате, соответствующем спецификациям XSD.  
  
|Тип .NET|Возвращаемое строковое значение|  
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
- [Преобразование строк в типы данных .NET](converting-strings-to-dotnet-data-types.md)

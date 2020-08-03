---
title: Практическое руководство. Получение сведений о типах и членах с помощью отражения
description: Узнайте, как использовать пространство имен System.Reflection для получения сведений о типах и членах с помощью отражения.
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: fa7af39c0addb328944a03236c26982301caf722
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865324"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a>Практическое руководство. Получение сведений о типах и членах с помощью отражения
Пространство имен <xref:System.Reflection> содержит много методов для получения сведений о типах и их членах. В этой статье демонстрируется один из этих методов — <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Общие сведения об отражении](reflection.md).
  
## <a name="example"></a>Пример

В следующем примере демонстрируется получение сведений о типах и членах с помощью отражения:

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a>См. также

- [Программирование с использованием доменов приложений](../app-domains/application-domains.md#programming-with-application-domains)
- [Отражение](reflection.md)
- [Использование доменов приложений](../app-domains/use.md)

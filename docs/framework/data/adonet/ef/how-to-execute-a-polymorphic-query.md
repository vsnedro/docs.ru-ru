---
title: Практическое руководство. Выполнение полиморфного запроса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: ad6fd7bf6a23f4cd1591a17b25042fd76ff1d08d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545341"
---
# <a name="how-to-execute-a-polymorphic-query"></a>Практическое руководство. Выполнение полиморфного запроса

В этом разделе показано, как выполнить преформацию [!INCLUDE[esql](../../../../../includes/esql-md.md)] запроса с помощью оператора [OFTYPE](./language-reference/oftype-entity-sql.md) .

### <a name="to-run-the-code-in-this-example"></a>Выполнение кода в этом примере

1. Добавьте [модель School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) в проект и настройте проект для использования Entity Framework. Дополнительные сведения см. в разделе [инструкции. Использование мастера EDM](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

2. На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. Измените концептуальную модель так, чтобы она была наследована с одной таблицей на иерархию, выполнив действия, описанные в [разделе Пошаговое руководство. сопоставление наследования-таблица-иерархия](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).

## <a name="example"></a>Пример

В следующем примере используется оператор OFTYPE для возврата и отображения коллекции только элементов `OnsiteCourses` из коллекции `Courses`.

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a>См. также

- [Поставщик EntityClient для Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Язык Entity SQL](./language-reference/entity-sql-language.md)

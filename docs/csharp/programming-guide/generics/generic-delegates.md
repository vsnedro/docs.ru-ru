---
title: Руководство по программированию на C#. Универсальные методы-делегаты
description: Сведения об использовании универсальных методов-делегатов при программировании на C#. Изучите примеры кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: df417701feb77dc47cff1cdd68eb4c7405d15beb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157412"
---
# <a name="generic-delegates-c-programming-guide"></a>Универсальные делегаты. (Руководство по программированию на C#)

[Делегат](../../language-reference/builtin-types/reference-types.md) может определять собственные параметры типа. В коде, который ссылается на универсальный делегат, можно указать аргумент типа для создания закрытого сконструированного типа. Это будет аналогично созданию экземпляра универсального класса или вызову универсального метода, как показано в следующем примере:  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 В C# версии 2.0 представлена новая функция группового преобразования методов, которая применяется как к конкретным, так и к универсальным типам делегатов, и позволяет записать приведенную выше строку с использованием упрощенного синтаксиса:  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 Делегаты, определенные в универсальном классе, могут использовать параметры класса универсального типа таким же образом, как это делают методы класса.  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 В коде, который ссылается на делегат, необходимо указать аргумент типа содержащего класса, как показано ниже:  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 Универсальные делегаты особенно полезны при определении событий, основанных на типовых шаблонах разработки, поскольку аргумент отправителя может быть строго типизирован и больше не требует приведения к <xref:System.Object> и из него.  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic>
- [Руководство по программированию на C#](../index.md)
- [Введение в универсальные шаблоны](./index.md)
- [Универсальные методы](./generic-methods.md)
- [Универсальные классы](./generic-classes.md)
- [Универсальные интерфейсы](./generic-interfaces.md)
- [Делегаты](../delegates/index.md)
- [Универсальные шаблоны](../../../standard/generics/index.md)

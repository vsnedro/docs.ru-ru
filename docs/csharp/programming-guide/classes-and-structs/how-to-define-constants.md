---
title: Определение констант в C#
description: Узнайте, как определять константы в C#, которые являются полями, значения которых задаются во время компиляции. Используйте константы для присвоения значимых имен особым значениям.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 972deaa4616c15c00e83e26891c4473eae7bfcf8
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513059"
---
# <a name="how-to-define-constants-in-c"></a>Определение констант в C\#

Константы — это поля, значения которых устанавливаются во время компиляции и не изменяются. С помощью констант можно присвоить особым значениям значащие имена вместо числовых литералов.  
  
> [!NOTE]
> В C# с помощью директивы препроцессора [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) нельзя определять константы так, как это было реализовано в C и C++.  
  
 Чтобы определить значения константы целочисленного типа (`int`, `byte` и т. д.), используйте перечисляемый тип. Дополнительные сведения см. в разделе [Перечисление](../../language-reference/builtin-types/enum.md).  
  
 Чтобы определить нецелочисленные константы, можно сгруппировать их в статический класс с именем `Constants`. В этом случае перед любыми ссылками на константы будет необходимо указывать имя класса, как показано в следующем примере.  
  
## <a name="example"></a>Пример  

 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 Используя квалификатор имени класса, вы гарантируете, что вы сами и другие разработчики будете понимать, что имеете дело с константой, которую нельзя изменить.  
  
## <a name="see-also"></a>См. также

- [Классы и структуры](./index.md)

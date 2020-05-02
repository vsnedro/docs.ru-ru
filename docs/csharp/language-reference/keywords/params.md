---
title: Справочник по C#. Ключевое слово params для массивов параметров
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 77d7fd19ff57f80f401191027e2fae95026e1966
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738844"
---
# <a name="params-c-reference"></a>params (справочник по C#)

С помощью ключевого слова `params` можно указать [параметр метода](method-parameters.md), принимающий переменное число аргументов. Тип параметра должен быть одномерным массивом.

В объявлении метода после ключевого слова `params` дополнительные параметры не допускаются, и в объявлении метода допускается только одно ключевое слово `params`.

Если объявленный тип параметра `params` не является одномерным массивом, возникает ошибка компилятора [CS0225](../../misc/cs0225.md).

При вызове метода с параметром `params` можно передать следующие объекты:

- разделенный запятыми список аргументов типа элементов массива;
- массив аргументов указанного типа;
- не передавать аргументы. Если аргументы не отправляются, длина списка `params` равна нулю.

## <a name="example"></a>Пример

В следующем примере показаны различные способы оправки аргументов параметру `params`.

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Параметры методов](method-parameters.md)

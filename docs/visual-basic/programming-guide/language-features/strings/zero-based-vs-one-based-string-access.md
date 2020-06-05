---
title: 'Что лучше: отсчет строк с нуля или с единицы?'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: ce2fcb2610c09a9591a5fd79da4baa74cc533c99
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363660"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Что лучше: отсчет индексации с нуля или с единицы? (Visual Basic)
В этом разделе сравнивается, как Visual Basic и .NET Framework предоставляют доступ к символам в строке. .NET Framework всегда предоставляет доступ к символам в строке с нуля, тогда как Visual Basic предоставляет доступ с нуля и с одной стороны, в зависимости от функции.  
  
## <a name="one-based"></a>С учетом единицы  
 Пример одноVisual Basicной функции можно получить с помощью `Mid` функции. Он принимает аргумент, который указывает на позиции символа, с которого начнется подстрока, начиная с позиции 1. Метод .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> принимает индекс символа в строке, с которой начинается подстрока, начиная с позиции 0. Таким способом, если имеется строка «ABCD», то отдельные символы нумеруются 1, 2, 3, 4, 5 для использования с `Mid` функцией, но 0, 1, 2, 3, 4 для использования с <xref:System.String.Substring%2A?displayProperty=nameWithType> методом.  
  
## <a name="zero-based"></a>С отсчетом от нуля  
 Пример функции Visual Basic, начинающейся с нуля, можно получить с помощью `Split` функции. Он разделяет строку и возвращает массив, содержащий подстроки. Метод .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> также разделяет строку и возвращает массив, содержащий подстроки. Так как `Split` функция и <xref:System.String.Split%2A> метод возвращают .NET Framework массивы, они должны относиться от нуля.  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [Знакомство со строками в Visual Basic](introduction-to-strings.md)

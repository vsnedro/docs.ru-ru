---
description: Дополнительные сведения о типах методов обработки строк в Visual Basic
title: Типы методов для работы со строками
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 02b127d5cd023a8bd73a3042a8bcec340ce63ed8
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429758"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Типы методов для работы со строками в Visual Basic

Существует несколько различных способов анализа строк и управления ими. Некоторые методы являются частью языка Visual Basic, а другие — в `String` классе.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Язык Visual Basic и платформа .NET Framework  

 Visual Basic методы используются в качестве встроенных функций языка. Они могут использоваться без уточнения в коде. В следующем примере показано типичное использование Visual Basic команды обработки строк:  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 В этом примере `Mid` функция выполняет прямую операцию над `aString` и присваивает значение `bString` .  
  
 Список методов обработки строк Visual Basic см. в разделе [Сводка манипулирования строками](../../../language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Общие методы и методы экземпляров  

 Можно также управлять строками с помощью методов `String` класса. В существуют два типа методов `String` : *Общие* методы и методы *экземпляра* .  
  
#### <a name="shared-methods"></a>Общие методы  

 Общий метод — это метод, который является производным от `String` самого класса и не требует работы экземпляра этого класса. Эти методы можно уточнять именем класса ( `String` ), а не экземпляром `String` класса. Пример:  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 В предыдущем примере <xref:System.String.Copy%2A?displayProperty=nameWithType> метод является статическим методом, который действует на заданное выражение и присваивает результирующее значение `bString` .  
  
#### <a name="instance-methods"></a>Методы экземпляра  

 Методы экземпляра, напротив, имеют определенный экземпляр `String` и должны уточняться именем экземпляра. Пример:  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 В этом примере <xref:System.String.Substring%2A?displayProperty=nameWithType> метод является методом экземпляра `String` (то есть `aString` ). Он выполняет операцию над `aString` и присваивает этому значению значение `bString` .  
  
 Дополнительные сведения см. в документации по <xref:System.String> классу.  
  
## <a name="see-also"></a>См. также раздел

- [Знакомство со строками в Visual Basic](introduction-to-strings.md)

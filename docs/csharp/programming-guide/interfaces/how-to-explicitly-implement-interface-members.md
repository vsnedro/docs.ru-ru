---
title: Руководство по программированию на C#. Явная реализация элементов интерфейса
description: Сведения о явной реализации элементов интерфейса при программировании на C#. Доступ к членам осуществляется посредством экземпляра интерфейса.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: a9c019cdcf6e229199d980a2d1913df7c72a2169
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157399"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>Руководство по программированию на C#. Явная реализация элементов интерфейса

В этом примере объявляются [интерфейс](../../language-reference/keywords/interface.md)`IDimensions` и класс `Box`, который явно реализует члены интерфейса `GetLength` и `GetWidth`. Доступ к членам осуществляется посредством экземпляра интерфейса `dimensions`.  
  
## <a name="example"></a>Пример  

 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
  
- Обратите внимание, что следующие строки в методе `Main` закомментированы, поскольку при их компиляции возникнут ошибки. Член интерфейса, реализованный явным образом, недоступен из экземпляра [класса](../../language-reference/keywords/class.md):  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- Также обратите внимание, что следующие строки в методе `Main` успешно выводят на печать размеры поля, поскольку методы вызываются из экземпляра интерфейса:  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](../classes-and-structs/index.md)
- [Интерфейсы](./index.md)
- [Практическое руководство. Явная реализация членов двух интерфейсов](./how-to-explicitly-implement-members-of-two-interfaces.md)

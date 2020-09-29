---
description: '#endif. Справочник по C#'
title: '#endif. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 0ccc00ceab2aa67c77140e3ef09907ba260d7e9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168638"
---
# <a name="endif-c-reference"></a>#endif (Справочник по C#)

`#endif` указывает на конец условной директивы, начало которой было задано с помощью директивы [#if](./preprocessor-if.md). Например,  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a>Remarks  

 Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`. В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#endif`.  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Директивы препроцессора C#](./index.md)

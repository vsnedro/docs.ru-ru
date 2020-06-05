---
title: '#Директива Const'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 91152771a4ef5ec74a7408511ccc2afe28dd442e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415470"
---
# <a name="const-directive"></a>Директива #Const

Определяет константы условной компилятора для Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a>Компоненты  

 `constname`  
 Обязательный. Имя определяемой константы.  
  
 `expression`  
 Обязательный. Literal, другая условная константа компилятора или любое сочетание, включающее любые или все арифметические или логические операторы, кроме `Is` .  
  
## <a name="remarks"></a>Комментарии  

 Константы условной компиляции всегда являются частными для файла, в котором они отображаются. Нельзя создавать открытые константы компилятора с помощью `#Const` директивы. их можно создавать только в пользовательском интерфейсе или с помощью `/define` параметра компилятора.  
  
 В можно использовать только константы условной компиляции и литералы `expression` . Использование стандартной константы, определенной с помощью, `Const` приводит к ошибке. И наоборот, константы, определенные с помощью `#Const` ключевого слова, можно использовать только для условной компиляции. Константы также могут быть неопределенными, в этом случае они имеют значение `Nothing` .  
  
## <a name="example"></a>Пример  

 В этом примере используется директива `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>См. также раздел

- [-define (Visual Basic)](../../reference/command-line-compiler/define.md)
- [Директивы #If...Then...#Else](if-then-else-directives.md)
- [Оператор Const](../statements/const-statement.md)
- [Условная компиляция](../../programming-guide/program-structure/conditional-compilation.md)
- [Оператор If…Then…Else](../statements/if-then-else-statement.md)

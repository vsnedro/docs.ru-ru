---
description: 'Дополнительные сведения: Директива #Region'
title: '#Директива Region'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: 4ba1645cfc51a69d39e6a60b5ea236dd65883e1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797228"
---
# <a name="region-directive"></a>Директива #Region

Сворачивает и скрывает разделы кода в файлах Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`identifier_string`|Обязательный. Строка, которая выступает в качестве заголовка области, если он свернут. По умолчанию области свернуты.|  
|`#End Region`|Завершает блок `#Region`.|  
  
## <a name="remarks"></a>Remarks  

 Используйте директиву `#Region`, чтобы указать блок кода, который можно разворачивать и сворачивать с помощью функции структурирования в редакторе кода Visual Studio. Вы можете разместить или *вложить* области внутри других регионов, чтобы сгруппировать похожие регионы.  
  
## <a name="example"></a>Пример  

 В этом примере используется директива `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>См. также

- [Директивы #If...Then...#Else](if-then-else-directives.md)
- [Структура](/visualstudio/ide/outlining)
- [Практическое руководство. Сворачивание и скрытие частей кода](../../programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)

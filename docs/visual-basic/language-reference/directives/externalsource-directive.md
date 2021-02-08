---
description: 'Дополнительные сведения: Директива #ExternalSource'
title: '#Директива ExternalSource'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: 1f2e73aa152fbe2d97edcde912626696faacd5af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797241"
---
# <a name="externalsource-directive"></a>Директива #ExternalSource

Указывает сопоставление между конкретными строками исходного кода и текстом, внешним по отношению к источнику.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Компоненты  

 `StringLiteral`  
 Путь к внешнему источнику.  
  
 `IntLiteral`  
 Номер строки первой строки внешнего источника.  
  
 `LogicalLine`  
 Строка, в которой возникла ошибка во внешнем источнике.  
  
 `#End ExternalSource`  
 Завершает блок `#ExternalSource`.  
  
## <a name="remarks"></a>Remarks  

 Эта директива используется только компилятором и отладчиком.  
  
 Исходный файл может содержать директивы External Source, которые указывают на сопоставление между конкретными строками кода в исходном файле и внешним по отношению к источнику текстом, например ASPX-файлу. Если во время компиляции обнаружены ошибки в указанном исходном коде, они определяются как поступающие из внешнего источника.  
  
 Директивы External Source не влияют на компиляцию и не могут быть вложенными. Они предназначены только для внутреннего использования приложением.  
  
## <a name="see-also"></a>См. также

- [Условная компиляция](../../programming-guide/program-structure/conditional-compilation.md)

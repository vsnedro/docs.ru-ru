---
description: '#pragma. Справочник по C#'
title: '#pragma. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 2788c2589bee149676c5cb2b4212ec7a060a47af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168521"
---
# <a name="pragma-c-reference"></a>#pragma (Справочник по C#)

Директива `#pragma` предоставляет компилятору специальные инструкции для компиляции файла, в котором она появляется. Компилятор должен поддерживать эти инструкции. Другими словами, директиву `#pragma` нельзя использовать для создания настраиваемых инструкций предварительной обработки. Компилятор Microsoft C# поддерживает следующие две инструкции `#pragma`:  
  
 [#pragma warning](./preprocessor-pragma-warning.md)  
  
 [#pragma checksum](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a>Параметры  

 `pragma-name`  
 Имя распознанной директивы pragma.  
  
 `pragma-arguments`  
 Аргументы директивы pragma.  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Директивы препроцессора C#](./index.md)
- [#pragma warning](./preprocessor-pragma-warning.md)
- [#pragma checksum](./preprocessor-pragma-checksum.md)

---
description: '#pragma. Справочник по C#'
title: '#pragma. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 97d7a786c83a8be21f7fd38873061dba0f9278ae
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137959"
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

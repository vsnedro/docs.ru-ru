---
title: Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: a3d243f39f3fc45ca6b1ba0d26892d4c3db56f59
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397302"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a>Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)
Операторы Line больше не поддерживаются. Функциональные возможности файлового ввода-вывода доступны как `Microsoft.VisualBasic.FileSystem.LineInput` и графические функции доступны в виде `System.Drawing.Graphics.DrawLine` .  
  
 **Идентификатор ошибки:** BC30830  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. При выполнении доступа к файлу используйте `Microsoft.VisualBasic.FileSystem.LineInput` .  
  
2. Если выполняется вывод графики, используйте `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IO>
- <xref:System.Drawing>
- [Доступ к файлам с помощью Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)

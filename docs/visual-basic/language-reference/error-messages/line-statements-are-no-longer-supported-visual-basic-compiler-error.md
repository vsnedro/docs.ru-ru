---
description: 'Дополнительные сведения о: BC30830: операторы "Line" больше не поддерживаются'
title: Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 16696856cee365171000e7b0abc206c42d3f3174
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795876"
---
# <a name="bc30830-line-statements-are-no-longer-supported"></a>BC30830: операторы "Line" больше не поддерживаются

Операторы Line больше не поддерживаются. Функциональные возможности файлового ввода-вывода доступны как `Microsoft.VisualBasic.FileSystem.LineInput` и графические функции доступны в виде `System.Drawing.Graphics.DrawLine` .

 **Идентификатор ошибки:** BC30830

## <a name="to-correct-this-error"></a>Исправление ошибки

- При выполнении доступа к файлу используйте `Microsoft.VisualBasic.FileSystem.LineInput` .

- Если выполняется вывод графики, используйте `System.Drawing.Graphics.Drawline`.

## <a name="see-also"></a>См. также

- <xref:System.IO>
- <xref:System.Drawing>
- [Доступ к файлам с помощью Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)

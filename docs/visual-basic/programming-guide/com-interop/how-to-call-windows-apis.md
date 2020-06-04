---
title: Практическое руководство. Вызов API Windows
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 2c3bb599b79575180eb2b0ec89453f01901f94c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396847"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Практическое руководство. Вызов Windows API (Visual Basic)
В этом примере определяется и вызывается `MessageBox` функция в user32. dll, а затем в нее передается строка.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылка на пространство имен <xref:System>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
- Метод не является статическим, является абстрактным или был определен ранее. Родительский тип является интерфейсом, или длина *имени* или *dllname* равна нулю. (<xref:System.ArgumentException>)  
  
- *Имя* или параметр *dllname* имеет значение `Nothing` . (<xref:System.ArgumentNullException>)  
  
- Содержащий тип был создан ранее с помощью `CreateType`. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>См. также раздел

- [Более подробное рассмотрение вызова неуправляемого кода](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Примеры вызовов неуправляемого кода](../../../framework/interop/platform-invoke-examples.md)
- [Использование неуправляемых функций DLL](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [Определение метода с помощью порождаемого отражения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))
- [Пошаговое руководство. Вызов API Windows](walkthrough-calling-windows-apis.md)
- [COM-взаимодействие](index.md)

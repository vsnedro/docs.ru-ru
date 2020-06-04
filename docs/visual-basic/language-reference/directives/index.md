---
title: Директивы
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5fcf3cb8801bc99dd2096c28cc41ebefeb34592
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410001"
---
# <a name="directives-visual-basic"></a>Директивы (Visual Basic)

В подразделах этого раздела описаны директивы компилятора исходного кода Visual Basic.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Директива #Const](const-directive.md) — Определение константы компилятора  
  
 [Директива #ExternalSource](externalsource-directive.md) — указывает сопоставление между исходными строками и текстом, внешним по отношению к источнику  
  
 [#If... Then... #Else директивы](if-then-else-directives.md) --компилировать выбранные блоки кода  
  
 [Директива #Region](region-directive.md) — сворачивание и скрытие разделов кода в редакторе Visual Studio  
  
 **#Disable, #Enable** — отключение и включение конкретных предупреждений для регионов кода.  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 Можно также отключить и включить список кодов предупреждений с разделителями-запятыми.  
  
## <a name="related-sections"></a>Связанные разделы  

 [Справочник по языку Visual Basic](../index.md)  
  
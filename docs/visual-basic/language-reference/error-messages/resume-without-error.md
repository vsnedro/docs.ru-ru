---
title: Выполнение оператора Resume без ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: b6b565c88acadca048ade22ab00ac68539725f78
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400374"
---
# <a name="resume-without-error"></a>Выполнение оператора Resume без ошибки
`Resume`Оператор обнаружен за пределами кода обработки ошибок, или код был переведен в обработчик ошибок, несмотря на отсутствие ошибки.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Переместите `Resume` оператор в обработчик ошибок или удалите его.  
  
2. Переход к меткам не может осуществляться между процедурами, поэтому выполните поиск по этой процедуре для метки, идентифицирующей обработчик ошибок. Если обнаружена повторяющаяся метка, указанная в качестве целевого объекта `GoTo` инструкции, которая не является `On Error GoTo` инструкцией, измените метку строки, чтобы согласовать ее с предполагаемой целью.  
  
## <a name="see-also"></a>См. также раздел

- [Оператор Resume](../statements/resume-statement.md)
- [Оператор On Error](../statements/on-error-statement.md)

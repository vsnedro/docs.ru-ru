---
title: Выполнение оператора Resume без ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 6dd6805151de52a5e0cf51c520485c0e8558e0a7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870827"
---
# <a name="resume-without-error"></a>Выполнение оператора Resume без ошибки

`Resume`Оператор обнаружен за пределами кода обработки ошибок, или код был переведен в обработчик ошибок, несмотря на отсутствие ошибки.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Переместите `Resume` оператор в обработчик ошибок или удалите его.  
  
2. Переход к меткам не может осуществляться между процедурами, поэтому выполните поиск по этой процедуре для метки, идентифицирующей обработчик ошибок. Если обнаружена повторяющаяся метка, указанная в качестве целевого объекта `GoTo` инструкции, которая не является `On Error GoTo` инструкцией, измените метку строки, чтобы согласовать ее с предполагаемой целью.  
  
## <a name="see-also"></a>См. также

- [Оператор Resume](../statements/resume-statement.md)
- [Оператор On Error](../statements/on-error-statement.md)

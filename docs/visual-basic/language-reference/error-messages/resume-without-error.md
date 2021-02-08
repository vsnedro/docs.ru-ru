---
description: 'Дополнительные сведения: возобновление без ошибок'
title: Выполнение оператора Resume без ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: a2284484be65ae975c6e09499ec19e3cfd8d4a04
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792015"
---
# <a name="resume-without-error"></a>Выполнение оператора Resume без ошибки

`Resume`Оператор обнаружен за пределами кода обработки ошибок, или код был переведен в обработчик ошибок, несмотря на отсутствие ошибки.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Переместите `Resume` оператор в обработчик ошибок или удалите его.  
  
2. Переход к меткам не может осуществляться между процедурами, поэтому выполните поиск по этой процедуре для метки, идентифицирующей обработчик ошибок. Если обнаружена повторяющаяся метка, указанная в качестве целевого объекта `GoTo` инструкции, которая не является `On Error GoTo` инструкцией, измените метку строки, чтобы согласовать ее с предполагаемой целью.  
  
## <a name="see-also"></a>См. также

- [Оператор Resume](../statements/resume-statement.md)
- [Оператор On Error](../statements/on-error-statement.md)

---
description: 'Дополнительные сведения: функции User-Defined (Entity SQL)'
title: Пользовательские функции (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: b5ebff087da08530e13f301e58509ba2d90c3605
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673210"
---
# <a name="user-defined-functions-entity-sql"></a>Пользовательские функции (Entity SQL)

Entity SQL поддерживает вызов встроенных определяемых пользователем функций в запросе. Эти функции можно определить в строке запроса (см [. раздел как вызвать функцию User-Defined](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) или как часть концептуальной модели (см. раздел [как определить пользовательские функции в концептуальной модели](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))). Функции концептуальной модели определяются как команда Entity SQL в элементе [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) элемента [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) в концептуальной модели.  
  
 Entity SQL позволяет определить функции в самой команде запроса. Оператор [функции](function-entity-sql.md) определяет встроенные функции. В одной команде можно задать несколько функций с одним и тем же именем при условии, что эти функции имеют уникальные сигнатуры. Для получения дополнительной информации см. [Function Overload Resolution](function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>См. также

- [Функции](functions-entity-sql.md)

---
description: 'Дополнительные сведения о: интерфейс IMethodMalloc'
title: Интерфейс IMethodMalloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: 6b84ac0ddb49718d24b2cad174613bc311dc509b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736964"
---
# <a name="imethodmalloc-interface"></a>Интерфейс IMethodMalloc

Предоставляет метод для выделения памяти для нового текста функции MSIL.  
  
> [!NOTE]
> `IMethodMalloc`Интерфейс — это простой механизм выделения памяти. Она позволяет выделить память, но не освобождает ее.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Alloc](imethodmalloc-alloc-method.md)|Пытается выделить указанный объем памяти для нового текста функции MSIL.|  
  
## <a name="remarks"></a>Remarks  

 Каждый распределитель зависит от конкретного модуля и гарантирует, что текст функции будет иметь положительное смещение от базового модуля. Память над базовым модулем может быть ценной, поэтому распределитель должен использоваться для выделения памяти только для тела функции.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)

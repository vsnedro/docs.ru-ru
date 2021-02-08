---
description: 'Дополнительные сведения о: интерфейс ICLRDataTarget2'
title: Интерфейс ICLRDataTarget2
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
ms.openlocfilehash: 9ba6d11ea043d3b6ba85544b47e063f585854af8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794849"
---
# <a name="iclrdatatarget2-interface"></a>Интерфейс ICLRDataTarget2

Подкласс [ICLRDataTarget](iclrdatatarget-interface.md) , используемый уровнем служб доступа к данным для управления областями виртуальной памяти в целевом процессе.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AllocVirtual](iclrdatatarget2-allocvirtual-method.md)|Выделяет память в адресном пространстве целевого процесса.|  
|[Метод FreeVirtual](iclrdatatarget2-freevirtual-method.md)|Освобождает память, которая была ранее выделена в адресном пространстве целевого процесса.|  
  
## <a name="remarks"></a>Remarks  

 Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости. Например, реализация активного процесса будет отличаться от реализации дампа памяти. Целевой объект может не поддерживать изменение областей его памяти.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)

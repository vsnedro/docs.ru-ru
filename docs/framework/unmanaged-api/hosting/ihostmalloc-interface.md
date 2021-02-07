---
description: 'Дополнительные сведения о: интерфейс IHostMalloc'
title: Интерфейс IHostMalloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: cd04a0f71fd429ea10b9edcce02806f4afa57148
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708181"
---
# <a name="ihostmalloc-interface"></a>Интерфейс IHostMalloc

Предоставляет методы, позволяющие среде CLR запрашивать детализированные выделения из кучи через узел.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Alloc](ihostmalloc-alloc-method.md)|Запрашивает у узла выделение запрошенного объема памяти из кучи.|  
|[Метод DebugAlloc](ihostmalloc-debugalloc-method.md)|Запрашивает, что узел выделяет запрошенный объем памяти из кучи, и дополнительно следит за местом выделения памяти.|  
|[Метод Free](ihostmalloc-free-method.md)|Освобождает память, выделенную с помощью `Alloc` метода.|  
  
## <a name="remarks"></a>Remarks  

 Среда CLR получает указатель интерфейса на `IHostMalloc` экземпляр, вызывая метод [IHostMemoryManager:: CreateMalloc](ihostmemorymanager-createmalloc-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](ihostmemorymanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)

---
description: 'Дополнительные сведения о: интерфейс IHostAssemblyManager'
title: Интерфейс IHostAssemblyManager
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: 649771f79e65039adfa8c0ade9f167b1679bb917
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709000"
---
# <a name="ihostassemblymanager-interface"></a>Интерфейс IHostAssemblyManager

Предоставляет методы, позволяющие узлу указывать наборы сборок, которые должны быть загружены средой CLR или узлом.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAssemblyStore](ihostassemblymanager-getassemblystore-method.md)|Возвращает указатель интерфейса на объект [IHostAssemblyStore](ihostassemblystore-interface.md) , представляющий список сборок, загруженных узлом.|  
|[Метод GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md)|Возвращает указатель интерфейса на объект [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , представляющий список сборок, которые узел загружает в среду CLR.|  
  
## <a name="remarks"></a>Remarks  

 Узел не является обязательным для реализации `IHostAssemblyManager` или `IHostAssemblyStore` . Если узел выполняет реализацию `IHostAssemblyManager` , он также должен реализовать `IHostAssemblyStore` .  
  
 Среда выполнения запрашивает `IHostAssemblyManager` , вызывая [IHostControl:: жесостманажер](ihostcontrol-gethostmanager-method.md) при инициализации с `IID` IID_IHostAssemblyManager.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyStore](ihostassemblystore-interface.md)
- [Интерфейс IHostControl](ihostcontrol-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)

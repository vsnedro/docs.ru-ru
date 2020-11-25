---
title: Интерфейс IHostSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
ms.openlocfilehash: aafaa1d648396ddaa76193fa15cf7f74394777a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724810"
---
# <a name="ihostsecuritycontext-interface"></a>Интерфейс IHostSecurityContext

Позволяет среде CLR поддерживать сведения о контексте безопасности, реализуемые узлом.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Capture](ihostsecuritycontext-capture-method.md)|Возвращает клон `IHostSecurityContext` экземпляра, возвращенного из вызова [IHostSecurityManager:: getsecuritycontext-](ihostsecuritymanager-getsecuritycontext-method.md).|  
  
## <a name="remarks"></a>Комментарии  

 Узел может управлять доступом кода к маркерам потоков как средой CLR, так и кодом пользователя. Он также может гарантировать, что полные сведения о контексте безопасности передаются по асинхронным операциям или кодовым точкам с ограниченным доступом к коду. `IHostSecurityContext` инкапсулирует эти сведения о контексте безопасности, которые непрозрачны для среды выполнения. Среда выполнения захватывает эти сведения с помощью `Capture` и перемещает их между отправкой рабочего элемента пула потоков, выполнением метода завершения, а также конструкторами модулей и классов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)
- [Интерфейс IHostSecurityManager](ihostsecuritymanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)

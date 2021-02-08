---
description: 'Дополнительные сведения о: интерфейс ICLROnEventManager'
title: Интерфейс ICLROnEventManager
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
ms.openlocfilehash: 7a9c0beec5083bc93f5361bb0e701da5beeedea2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789831"
---
# <a name="iclroneventmanager-interface"></a>Интерфейс ICLROnEventManager

Предоставляет методы, позволяющие основному приложению регистрировать и отменять регистрацию обратных вызовов для событий среды CLR.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md)|Регистрирует указатель обратного вызова для указанного события.|  
|[Метод UnregisterActionOnEvent](iclroneventmanager-unregisteractiononevent-method.md)|Отменяет регистрацию ранее зарегистрированного указателя обратного вызова для указанного события.|  
  
## <a name="remarks"></a>Remarks  

 Для регистрации и отмены регистрации обратных вызовов событий узел получает ссылку на `ICLROnEventManager` , вызывая метод [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .  
  
> [!NOTE]
> События, описанные [еклревент](eclrevent-enumeration.md) , можно инициировать несколько раз и из разных потоков, чтобы сообщить о выгрузке или отключении среды CLR.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrEvent](eclrevent-enumeration.md)
- [Интерфейс IActionOnCLREvent](iactiononclrevent-interface.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)

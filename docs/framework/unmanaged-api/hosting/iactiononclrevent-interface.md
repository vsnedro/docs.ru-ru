---
title: Интерфейс IActionOnCLREvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
ms.openlocfilehash: 8ca4bb1fe35451f95f752a4e71f5f0b541b55e58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721781"
---
# <a name="iactiononclrevent-interface"></a>Интерфейс IActionOnCLREvent

Предоставляет метод [иактиононклревент:: oneven](iactiononclrevent-onevent-method.md) , который выполняет обратные вызовы для событий, зарегистрированных с помощью вызова метода [ICLROnEventManager:: регистерактиононевент](iclroneventmanager-registeractiononevent-method.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод OnEvent](iactiononclrevent-onevent-method.md)|Выполняет обратный вызов для зарегистрированного события.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисление EClrEvent](eclrevent-enumeration.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICLROnEventManager](iclroneventmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)

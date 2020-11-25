---
title: Интерфейс IValidator
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
ms.openlocfilehash: ce417402231d03828243bfb8bb7543c0a644a882
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700994"
---
# <a name="ivalidator-interface"></a>Интерфейс IValidator

Предоставляет методы для проверки переносимых исполняемых (PE) образов и создания отчетов об ошибках проверки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Description|  
|------------|-----------------|  
|Проверить|Проверяет указанный PE-файл или промежуточный язык MSIL.|  
|FormatEventInfo|Возвращает сообщение об ошибке, соответствующее указанной ошибке проверки.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** IValidator. idl, IValidator. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы размещения](hosting-interfaces.md)
- [Компонентный класс CorRuntimeHost](corruntimehost-coclass.md)

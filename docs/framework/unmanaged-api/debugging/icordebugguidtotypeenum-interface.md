---
description: 'Дополнительные сведения о: интерфейс ICorDebugGuidToTypeEnum'
title: Интерфейс ICorDebugGuidToTypeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
ms.openlocfilehash: abcdc9537f6f6ff2e0ac9b2be86734efbf303493
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660990"
---
# <a name="icordebugguidtotypeenum-interface"></a>Интерфейс ICorDebugGuidToTypeEnum

Предоставляет перечислитель, который определяет сопоставление между набором идентификаторов GUID и соответствующими типами, которые представлены экземплярами ICorDebugType. Этот интерфейс наследует методы от интерфейса ICorDebugEnum.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[ICorDebugGuidToTypeEnum:: Next](icordebugguidtotypeenum-next-method.md)|Возвращает указанное число экземпляров [кордебуггуидтотипемаппинг](cordebugguidtotypemapping-structure.md) , которые сопоставляют идентификаторы GUID со сведениями о типе.|  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugGuidToTypeEnum`Объект интерфейса можно извлечь, вызвав метод [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) . Отладчик может вызвать [следующий](icordebugguidtotypeenum-next-method.md) метод этого интерфейса для получения объектов [кордебуггуидтотипемаппинг](cordebugguidtotypemapping-structure.md) , представляющих сопоставления управляемых представлений типов Среда выполнения Windows, загруженных в домен приложения, используемый для вызова метода [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** среда выполнения Windows  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)

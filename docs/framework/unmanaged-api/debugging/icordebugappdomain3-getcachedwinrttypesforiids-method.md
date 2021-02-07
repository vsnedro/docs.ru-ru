---
description: 'Дополнительные сведения о методе: ICorDebugAppDomain3:: GetCachedWinRTTypesForIIDs'
title: Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
ms.openlocfilehash: 76b93cdb8c465935a4aaf36090ee44f2b6253a3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754177"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs

Возвращает перечислитель для кэшированных среда выполнения Windowsных типов в домене приложения на основе их идентификаторов интерфейсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cReqTypes`  
 окне Число обязательных типов.  
  
 `iidsToResolve`  
 окне Указатель на массив, содержащий идентификаторы интерфейса, соответствующие управляемым представлениям возвращаемых типов среда выполнения Windows.  
  
 `ppTypesEnum`  
 заполняет Указатель на адрес объекта "ICorDebugTypeEnum" интерфейса, который позволяет перечислить кэшированные управляемые представления возвращаемых типов среда выполнения Windows на основе идентификаторов интерфейса в `iidsToResolve` .  
  
## <a name="remarks"></a>Remarks  

 Если методу не удается получить сведения для определенного идентификатора интерфейса, соответствующая запись в коллекции "ICorDebugTypeEnum" будет иметь тип `ELEMENT_TYPE_END` для ошибок из-за проблем, связанных с получением данных, или `ELEMENT_TYPE_VOID` для неизвестных идентификаторов интерфейса.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** среда выполнения Windows  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugAppDomain3](icordebugappdomain3-interface.md)

---
title: Метод ICorDebugFrame::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: cacdccf5c27cd1d115134d49e754b4ace2870b72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205163"
---
# <a name="icordebugframegetstackrange-method"></a>Метод ICorDebugFrame::GetStackRange
Возвращает диапазон абсолютных адресов этого кадра стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pStart`  
 заполняет Указатель на объект `CORDB_ADDRESS` , указывающий начальный адрес кадра стека, представленного этим `ICorDebugFrame` объектом.  
  
 `pEnd`  
 заполняет Указатель на объект `CORDB_ADDRESS` , указывающий конечный адрес кадра стека, представленного этим `ICorDebugFrame` объектом.  
  
## <a name="remarks"></a>Remarks  
 Диапазон адресов стека полезен для пиеЦинг вместе чередующихся трассировок стека, собранных из нескольких ядер отладки. Числовой диапазон не предоставляет сведений о содержимом кадра стека. Он имеет смысл только для сравнения расположений в кадрах стека.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

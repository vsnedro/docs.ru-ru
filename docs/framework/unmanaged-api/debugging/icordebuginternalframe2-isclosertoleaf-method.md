---
description: 'Дополнительные сведения о методе: ICorDebugInternalFrame2:: Исклосертолеаф'
title: Метод ICorDebugInternalFrame2::IsCloserToLeaf
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
ms.openlocfilehash: d773f8670f600a5bcd2a8dad7f23fe243195957c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801284"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>Метод ICorDebugInternalFrame2::IsCloserToLeaf

Проверяет, `this` находится ли внутренний кадр ближе к конечному объекту, чем указанный объект ICorDebugFrame.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>Параметры  

 `pFrameToCompare`  
 окне Указатель на `ICorDebugFrame` объект сравнения.  
  
 `pIsCloser`  
 [out] `true` `this` значение, если внутренний кадр находится ближе к конечному объекту, чем кадр, заданный параметром `pFrameToCompare` ; в противном случае — `false` .  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Сравнение успешно выполнено.|  
|E_FAIL|Не удалось выполнить сравнение.|  
|E_INVALIDARG|`pFrameToCompare` или `pIsCloser` равно null.|  
  
## <a name="remarks"></a>Remarks  

 `IsCloserToLeaf` может использоваться для реализации политики для поверх внутренних кадров с другими кадрами в стеке.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)

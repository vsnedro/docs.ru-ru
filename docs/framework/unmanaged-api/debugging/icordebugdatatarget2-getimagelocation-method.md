---
title: Метод ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: 185b6a4979491a323f6eb15ab08a06f87fabc8d3
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976464"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a>Метод ICorDebugDataTarget2::GetImageLocation
Возвращает путь для модуля из базового адреса модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `baseAddress`  
 окне Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.  
  
 `cchName`  
 [входной] Число символов в буфере, которые должен получить путь к модулю.  
  
 `pcchName`  
 [выходной] Указатель на число символов, записанных в буфер `szName`.  
  
 `szName`  
 [выходной] Путь к модулю.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)

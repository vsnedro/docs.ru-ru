---
title: Метод ICorDebugModule::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
ms.openlocfilehash: c2aecadf8688e763a69bd40ca877e44bc0ce5c29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710049"
---
# <a name="icordebugmodulegetname-method"></a>Метод ICorDebugModule::GetName

Возвращает имя файла модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cchname`  
 [in] Размер массива `szName`.  
  
 `pcchName`  
 окне Указатель на длину возвращаемого имени.  
  
 `szName`  
 заполняет Массив, в котором хранится возвращаемое имя.  
  
## <a name="remarks"></a>Комментарии  

 `GetName`Метод возвращает S_OK HRESULT, если имя файла модуля совпадает с именем на диске. `GetName` Возвращает S_FALSE HRESULT, если имя является составным, например, для динамического или в памяти модуля.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

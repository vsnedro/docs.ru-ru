---
description: 'Дополнительные сведения о методе: ICorDebugMDA:: GetXML'
title: Метод ICorDebugMDA::GetXML
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
ms.openlocfilehash: fa506e6e8f306271f10a7a715af9b8bc6a80c1d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801141"
---
# <a name="icordebugmdagetxml-method"></a>Метод ICorDebugMDA::GetXML

Возвращает полный XML-поток, связанный с помощником по отладке управляемого кода (MDA), представленным [ICorDebugMDA](icordebugmda-interface.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cchName`  
 [in] Размер массива `szName`.  
  
 `pcchName`  
 заполняет Указатель на длину XML-потока.  
  
 `szName`  
 заполняет Массив, в котором хранится XML-поток. Массив может быть пустым.  
  
## <a name="remarks"></a>Remarks  

 `GetXML`Метод может повлиять на производительность в зависимости от размера соответствующего потока XML.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugMDA](icordebugmda-interface.md)
- [Диагностика ошибок посредством управляемых помощников по отладке](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

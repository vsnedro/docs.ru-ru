---
title: Метод IDebugAutoAttach::AutoAttach
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
ms.openlocfilehash: 64dd653bb0d4e383075a999e0803e4acfd0fae3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720104"
---
# <a name="idebugautoattachautoattach-method"></a>Метод IDebugAutoAttach::AutoAttach

Выполняет вызванное сервером автоматическое присоединение отладчика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `guidPort`  
 окне Всегда имеет значение `GUID_NULL` .  
  
 `dwPid`  
 окне Идентификатор процесса, обычно полученный с помощью `GetCurrentProcessId` функции.  
  
 `dwProgramType`  
 окне Тип программы: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` или `AUTOATTACH_PROGRAM_UNKNOWN` .  
  
 `dwProgramId`  
 окне Идентификатор программы.  
  
 `pszSessionId`  
 окне Строка, передаваемая командой Debug.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Дбгаутоаттач. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IDebugAutoAttach](idebugautoattach-interface.md)

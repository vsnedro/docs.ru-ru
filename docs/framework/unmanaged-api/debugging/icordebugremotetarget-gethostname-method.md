---
description: 'См. Дополнительные сведения о методе ICorDebugRemoteTarget:: onhostname'
title: Метод ICorDebugRemoteTarget::GetHostName
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
ms.openlocfilehash: a24f34dd638c7031211c2185cd761af0aa24105e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803530"
---
# <a name="icordebugremotetargetgethostname-method"></a>Метод ICorDebugRemoteTarget::GetHostName

Возвращает полное доменное имя или IPv4-адрес целевого компьютера удаленной отладки. В настоящее время IPV6 не поддерживается.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a>Параметры  

 `cchHostName`  
 окне Размер буфера (в символах) `szHostName` . Если этот параметр равен 0 (нулю), он `szHostName` должен иметь значение null.  
  
 `pcchHostName`  
 заполняет Количество символов, включая знак завершения null, в имени узла или IP-адресе. Этот параметр может быть нулевым.  
  
 `szHostName`  
 заполняет Буфер, содержащий имя узла или IP-адрес.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK  
 Имя узла или IP-адрес успешно возвращены.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось вернуть имя узла или IP-адрес.  
  
## <a name="remarks"></a>Remarks  

 Этот метод реализуется модулем записи отладчика. Он должен следовать парадигме нескольких вызовов: при первом вызове вызывающий объект передает значение NULL и `cchHostName` в `szHostName` , и `pcchHostName` возвращает размер требуемого буфера. При втором вызове передается размер, который был ранее возвращен `cchHostName` , и передается буфер соответствующего размера `szHostName` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:** 3,5 SP1  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md)
- [Интерфейс ICorDebug](icordebug-interface.md)

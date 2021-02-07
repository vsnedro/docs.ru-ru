---
description: 'Дополнительные сведения о методе: ICorDebugProcess:: Thread'
title: Метод ICorDebugProcess::GetThread
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type:
- apiref
ms.openlocfilehash: bd636df50afd3f12901c1b48559c44ac6ad0cb81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746910"
---
# <a name="icordebugprocessgetthread-method"></a>Метод ICorDebugProcess::GetThread

Возвращает поток этого процесса с указанным ИДЕНТИФИКАТОРом потока операционной системы (ОС).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwThreadId`  
 окне Идентификатор потока операционной системы для извлекаемого потока.  
  
 `ppThread`  
 заполняет Указатель на адрес объекта ICorDebugThread, представляющего поток.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

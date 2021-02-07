---
description: 'Дополнительные сведения: указатель функции WAITORTIMERCALLBACK'
title: Указатель функции WAITORTIMERCALLBACK
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
ms.openlocfilehash: 6fd9e7eab56e48086eefcb26fc48cbf5f45d4a0e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679060"
---
# <a name="waitortimercallback-function-pointer"></a>Указатель функции WAITORTIMERCALLBACK

Указывает на функцию, которая уведомляет узел о том, что дескриптор ожидания ( <xref:System.Threading.WaitHandle> ) либо получил сигнал, либо превысил время ожидания.  
  
 Этот указатель функции является устаревшим в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `lpParameter`  
 окне Указатель на объект, содержащий сведения, определенные узлом.  
  
 `TimerOrWaitFired`  
 [входные] `true` значение, если истекло время ожидания дескриптора ожидания или `false` он был сигнальным.  
  
## <a name="remarks"></a>Remarks  

 Функция, к которой `WAITORTIMERCALLBACK` points является функцией обратного вызова и должна быть реализована модулем записи размещающего приложения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorWks.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

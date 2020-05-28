---
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
ms.openlocfilehash: ee5dd611888ec52e360ef45fab4c01e9c5b2d6bb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009457"
---
# <a name="waitortimercallback-function-pointer"></a>Указатель функции WAITORTIMERCALLBACK
Указывает на функцию, которая уведомляет узел о том, что дескриптор ожидания ( <xref:System.Threading.WaitHandle> ) либо получил сигнал, либо превысил время ожидания.  
  
 Этот указатель функции является устаревшим в .NET Framework 4.  
  
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
  
## <a name="remarks"></a>Примечания  
 Функция, к которой `WAITORTIMERCALLBACK` points является функцией обратного вызова и должна быть реализована модулем записи размещающего приложения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorWks. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

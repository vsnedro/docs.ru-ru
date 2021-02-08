---
description: 'Дополнительные сведения: указатель функции FLockClrVersionCallback'
title: Указатель функции FLockClrVersionCallback
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: 3506cd30ab2a9e5a06b03f5010c9870280a38378
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785384"
---
# <a name="flockclrversioncallback-function-pointer"></a>Указатель функции FLockClrVersionCallback

Указывает на функцию, которая вызывается средой CLR для указания того, что инициализация запущена или завершена.  
  
 Этот указатель функции является устаревшим в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a>Remarks  

 Эта функция реализуется узлом.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorWks.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция LockClrVersion](lockclrversion-function.md)
- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

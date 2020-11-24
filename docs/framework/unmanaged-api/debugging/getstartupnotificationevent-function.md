---
title: Функция GetStartupNotificationEvent
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
ms.openlocfilehash: 1c6ad35cd42760a4d88cf78bb084a25cf58a1064
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676092"
---
# <a name="getstartupnotificationevent-function"></a>Функция GetStartupNotificationEvent

Создает или открывает обработчик событий, который будет информироваться любой средой CLR, загружаемой в указанный целевой процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a>Параметры  

 `debuggeePID`  
 [in] Идентификатор целевого процесса, из которого следует получать уведомления при запуске среды CLR.  
  
 `phStartupEvent`  
 [out] Указатель на дескриптор, который будет оповещаться средой CLR при запуске.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK  
 Успешно получен дескриптор события уведомления при запуске.  
  
 E_INVALIDARG  
 `phStartupEvent` имеет значение null, или `debuggeePID` не ссылается на процесс, выполняющийся в текущий момент.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось получить дескриптор события уведомления при запуске.  
  
## <a name="remarks"></a>Комментарии  

 В операционной системе Windows `debuggeePID` сопоставляется с идентификатором процесса ОС.  
  
 Событие сигнализирует перед любым выполнением управляемого кода средой CLR, которая оповещает событие.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** dbgshim. h  
  
 **Библиотека:** dbgshim.dll  
  
 **.NET Framework версии:** 3,5 SP1

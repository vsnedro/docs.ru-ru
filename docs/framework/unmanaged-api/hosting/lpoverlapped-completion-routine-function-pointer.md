---
description: 'Дополнительные сведения: указатель функции LPOVERLAPPED_COMPLETION_ROUTINE'
title: Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
ms.openlocfilehash: 6645e6a9746404a4ae355a22cf16e6d164c63bed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679840"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a>Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE

Указывает на функцию, которая уведомляет узел при завершении перекрытия (асинхронного) ввода-вывода на устройство.  
  
 Этот указатель функции является устаревшим в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwErrorCode`  
 окне Значение, которое является кодом ошибки, если устройство было закрыто; в противном случае это значение равно нулю.  
  
 Закрытие устройства приводит к немедленному завершению операций ввода-вывода на устройстве.  
  
 `dwNumberOfBytesTransfered`  
 окне Число байтов, передаваемых операцией ввода-вывода.  
  
 `lpOverlapped`  
 окне Указатель на структуру, содержащую сведения, используемые для завершения запроса ввода-вывода.  
  
## <a name="remarks"></a>Remarks  

 Функция, к которой `LPOVERLAPPED_COMPLETION_ROUTINE` points является функцией обратного вызова и должна быть реализована модулем записи размещающего приложения. Функция обратного вызова позволяет узлу обработать завершенный запрос ввода-вывода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorWks.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

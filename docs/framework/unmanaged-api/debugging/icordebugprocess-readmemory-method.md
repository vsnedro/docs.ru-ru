---
description: 'Дополнительные сведения о методе: ICorDebugProcess:: ReadMemory'
title: Метод ICorDebugProcess::ReadMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: bdf1bda9df416b6d3142e3ae09955e706f260802
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746806"
---
# <a name="icordebugprocessreadmemory-method"></a>Метод ICorDebugProcess::ReadMemory

Считывает указанную область памяти для этого процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>Параметры  

 `address`  
 окне `CORDB_ADDRESS` Значение типа, указывающее базовый адрес памяти для чтения.  
  
 `size`  
 окне Число байтов, считываемых из памяти.  
  
 `buffer`  
 заполняет Буфер, который получает содержимое памяти.  
  
 `read`  
 заполняет Указатель на число байтов, передаваемых в указанный буфер.  
  
## <a name="remarks"></a>Remarks  

 `ReadMemory`Метод в основном предназначен для использования в отладке взаимодействия для проверки областей памяти, используемых неуправляемой частью отлаживаемого кода. Этот метод также можно использовать для считывания кода на языке MSIL и собственного JIT-скомпилированного кода.  
  
 Все управляемые точки останова будут удалены из данных, возвращаемых в `buffer` параметре. Никакие изменения для собственных точек останова, заданных [ICorDebugProcess2:: сетунманажедбреакпоинт](icordebugprocess2-setunmanagedbreakpoint-method.md), не выполняются.  
  
 Кэширование памяти процесса не выполняется.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

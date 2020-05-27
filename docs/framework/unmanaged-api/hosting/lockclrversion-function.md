---
title: Функция LockClrVersion
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 09bcebfdcfea3d5728d404cdb6b5fb170a5432c3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008499"
---
# <a name="lockclrversion-function"></a>Функция LockClrVersion
Позволяет узлу определить, какая версия среды CLR будет использоваться в процессе перед явной инициализацией среды CLR.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `hostCallback`  
 окне Функция, вызываемая средой CLR при инициализации.  
  
 `pBeginHostSetup`  
 окне Функция, вызываемая узлом для информирования среды CLR о начале инициализации.  
  
 `pEndHostSetup`  
 окне Функция, вызываемая узлом для информирования среды CLR о завершении инициализации.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h, а также следующие значения.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|Один или несколько аргументов имеют значение null.|  
  
## <a name="remarks"></a>Примечания  
 Узел вызывает `LockClrVersion` перед инициализацией среды CLR. `LockClrVersion`принимает три параметра, все из которых являются обратными вызовами типа [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md). Этот тип определяется следующим образом.  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 При инициализации среды выполнения выполняются следующие действия.  
  
1. Узел вызывает [CorBindToRuntimeEx](corbindtoruntimeex-function.md) или одну из других функций инициализации среды выполнения. Кроме того, узел может инициализировать среду выполнения с помощью активации объекта COM.  
  
2. Среда выполнения вызывает функцию, указанную `hostCallback` параметром.  
  
3. Функция, указанная с помощью, `hostCallback` выполняет следующую последовательность вызовов:  
  
    - Функция, заданная `pBeginHostSetup` параметром.  
  
    - `CorBindToRuntimeEx`(или другую функцию инициализации среды выполнения).  
  
    - [ICLRRuntimeHost:: SetHostControl](iclrruntimehost-sethostcontrol-method.md).  
  
    - [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md).  
  
    - Функция, заданная `pEndHostSetup` параметром.  
  
 Все вызовы из `pBeginHostSetup` в `pEndHostSetup` должны выполняться в одном потоке или Fiber с одним и тем же логическим стеком. Этот поток может отличаться от потока, в котором `hostCallback` вызывается.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

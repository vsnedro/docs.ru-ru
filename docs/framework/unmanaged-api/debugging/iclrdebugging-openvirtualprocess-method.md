---
title: Метод ICLRDebugging::OpenVirtualProcess
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
ms.openlocfilehash: 1598130eb097655d3e83689956eb3614103eb573
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860374"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a>Метод ICLRDebugging::OpenVirtualProcess
Возвращает интерфейс ICorDebugProcess, соответствующий загруженному в процесс модулю среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleBaseAddress`  
 окне Базовый адрес модуля в целевом процессе. COR_E_NOT_CLR будет возвращен, если указанный модуль не является модулем CLR.  
  
 `pDataTarget`  
 окне Абстракция целевого объекта данных, позволяющая управляемому отладчику проверять состояние процесса. В отладчике должен быть реализован интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) . Необходимо реализовать интерфейс [иклрдебуггинглибрарипровидер](iclrdebugginglibraryprovider-interface.md) для поддержки сценариев, в которых отлаживаемая среда CLR не установлена локально на компьютере.  
  
 `pLibraryProvider`  
 окне Интерфейс обратного вызова поставщика библиотеки, позволяющий находить и загружать библиотеки отладки для конкретных версий по запросу. Этот параметр является обязательным только в `ppProcess` том `pFlags` случае, `null`если значение параметра или не равно.  
  
 `pMaxDebuggerSupportedVersion`  
 окне Самая высокая версия среды CLR, которую отладчик может отлаживать. Необходимо указать основной, дополнительный номер версии и версию сборки из последней версии среды CLR, которую поддерживает этот отладчик, и установить номер редакции 65535 для размещения будущих выпусков среды CLR на месте.  
  
 `riidProcess`  
 окне ИДЕНТИФИКАТОР получаемого интерфейса ICorDebugProcess. В настоящее время допустимыми значениями являются IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 и IID_CORDEBUGPROCESS.  
  
 `ppProcess`  
 заполняет Указатель на COM-интерфейс, идентифицируемый `riidProcess`.  
  
 `pVersion`  
 [вход, выход] Версия среды CLR. Во входных данных это значение может `null`быть равно. Он также может указывать на структуру [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) . в этом случае `wStructVersion` поле структуры должно быть инициализировано равным 0 (нулю).  
  
 В выходных данных возвращаемая `CLR_DEBUGGING_VERSION` структура будет заполнена сведениями о версии для среды CLR.  
  
 `pdwFlags`  
 заполняет Информационные флаги для указанной среды выполнения. Описание флагов см. в [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) разделе.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pDataTarget` равен `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|Обратный вызов [иклрдебуггинглибрарипровидер](iclrdebugginglibraryprovider-interface.md) возвращает ошибку или не предоставляет допустимый маркер.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget`не реализует необходимые интерфейсы целевого объекта данных для этой версии среды выполнения.|  
|CORDBG_E_NOT_CLR|Указанный модуль не является модулем CLR. Это значение HRESULT также возвращается, если модуль среды CLR не удается обнаружить из-за повреждения памяти, модуль недоступен или версия среды CLR позже версии оболочки совместимости.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Эта версия среды выполнения не поддерживает эту модель отладки. В настоящее время модель отладки не поддерживается версиями CLR до .NET Framework 4. После `pwszVersion` этой ошибки параметру OUTPUT по-прежнему присваивается правильное значение.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|Версия CLR больше версии, которую этот отладчик заявляет для поддержки. После `pwszVersion` этой ошибки параметру OUTPUT по-прежнему присваивается правильное значение.|  
|E_NO_INTERFACE|`riidProcess` Интерфейс недоступен.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|`CLR_DEBUGGING_VERSION` Структура не имеет известного значения для `wStructVersion`. Единственным допустимым значением в данный момент является 0.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)

---
title: Функция GetRequestedRuntimeInfo
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
ms.openlocfilehash: 0efda458d51677fcd16140cd0f0a835b76c20173
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617182"
---
# <a name="getrequestedruntimeinfo-function"></a>Функция GetRequestedRuntimeInfo
Возвращает сведения о версии и каталоге о среде CLR, запрашиваемой приложением.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,
    [in]  LPCWSTR  pwszVersion,
    [in]  LPCWSTR  pConfigurationFile,
    [in]  DWORD    startupFlags,
    [in]  DWORD    runtimeInfoFlags,
    [out] LPWSTR   pDirectory,
    [in]  DWORD    dwDirectory,
    [out] DWORD   *dwDirectoryLength,
    [out] LPWSTR   pVersion,
    [in]  DWORD    cchBuffer,
    [out] DWORD   *dwlength  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pExe`  
 окне Имя приложения.  
  
 `pwszVersion`  
 окне Строка, указывающая номер версии среды выполнения.  
  
 `pConfigurationFile`  
 окне Имя файла конфигурации, связанного с `pExe` .  
  
 `startupFlags`  
 окне Одно или несколько значений перечисления [STARTUP_FLAGS](startup-flags-enumeration.md) .  
  
 `runtimeInfoFlags`  
 окне Одно или несколько значений перечисления [RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md) .  
  
 `pDirectory`  
 заполняет Буфер, содержащий путь к каталогу среды выполнения после успешного завершения.  
  
 `dwDirectory`  
 окне Длина буфера каталога.  
  
 `dwDirectoryLength`  
 заполняет Указатель на длину строки пути к каталогу.  
  
 `pVersion`  
 заполняет Буфер, содержащий номер версии среды выполнения после успешного завершения.  
  
 `cchBuffer`  
 окне Длина буфера строки версии.  
  
 `dwlength`  
 заполняет Указатель на длину строки версии.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|ERROR_INSUFFICIENT_BUFFER|Буфер каталога недостаточно велик для хранения пути к каталогу.<br /><br /> -или-<br /><br /> Буфер версии недостаточно велик для хранения строки версии.|  
  
## <a name="remarks"></a>Комментарии  
 `GetRequestedRuntimeInfo`Метод возвращает сведения времени выполнения о версии, загруженной в процесс, что не обязательно является последней версией, установленной на компьютере.  
  
 В .NET Framework версии 2,0 можно получить сведения о последней установленной версии с помощью `GetRequestedRuntimeInfo` метода следующим образом.  
  
- Укажите для `pExe` `pwszVersion` параметров, и `pConfigurationFile` значение null.  
  
- Укажите флаг RUNTIME_INFO_UPGRADE_VERSION в `RUNTIME_INFO_FLAGS` перечислениях для `runtimeInfoFlags` параметра.  
  
 `GetRequestedRuntimeInfo`Метод не возвращает последнюю версию среды CLR в следующих случаях:  
  
- Существует файл конфигурации приложения, указывающий загрузку определенной версии среды CLR. Обратите внимание, что .NET Framework будет использовать файл конфигурации, даже если для параметра указано значение NULL `pConfigurationFile` .  
  
- Метод [CorBindToRuntimeEx](corbindtoruntimeex-function.md) был вызван с указанием более ранней версии среды CLR.  
  
- В настоящее время выполняется приложение, которое было скомпилировано для более ранней версии среды CLR.  
  
 Для `runtimeInfoFlags` параметра можно указать только одну из констант архитектуры `RUNTIME_INFO_FLAGS` перечисления в один момент времени:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Функция GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md)
- [Функция GetVersionFromProcess](getversionfromprocess-function.md)
- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

---
description: Дополнительные сведения о функции Корбиндторунтимебикфг
title: Функция CorBindToRuntimeByCfg
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: c1acf6a8f1d8637bc2d6cd180016ff51cf500107
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790078"
---
# <a name="corbindtoruntimebycfg-function"></a>Функция CorBindToRuntimeByCfg

Загружает среду CLR в процесс с использованием сведений о версии, считываемых из XML-файла.  
  
 Эта функция является устаревшей в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pCfgStream`  
 окне Указатель на `IStream` объект, считывающий XML-файл.  
  
 `reserved`  
 [in] Зарезервирован для будущего использования. Используйте 0 (нуль) в качестве значения.  
  
 `startupFlags`  
 окне Значение перечисления [STARTUP_FLAGS](startup-flags-enumeration.md) , указывающее поведение среды CLR при запуске.  
  
 `rclsid`  
 окне Объект `CLSID` coclass, реализующий интерфейс [ICorRuntimeHost](icorruntimehost-interface.md) или [ICLRRuntimeHost](iclrruntimehost-interface.md) . Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 окне `IID` Либо `ICorRuntimeHost` интерфейса, либо `ICLRRuntimeHost` . Поддерживаемые значения: IID_ICorRuntimeHost или IID_ICLRRuntimeHost.  
  
 `ppv`  
 заполняет Указатель на адрес возвращенного интерфейса.  
  
## <a name="remarks"></a>Remarks  

 Формат XML-файла моделируется после стандартного файла конфигурации приложения. Дополнительные сведения о XML-файлах см. в разделе [Схема файла конфигурации](../../configure-apps/file-schema/index.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntime](corbindtoruntime-function.md)
- [Функция CorBindToRuntimeEx](corbindtoruntimeex-function.md)
- [Функция CorBindToRuntimeHost](corbindtoruntimehost-function.md)
- [Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)
- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

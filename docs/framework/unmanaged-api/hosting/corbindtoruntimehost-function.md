---
description: Дополнительные сведения о функции Корбиндторунтимехост
title: Функция CorBindToRuntimeHost
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeHost
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeHost
helpviewer_keywords:
- CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type:
- apiref
ms.openlocfilehash: 1921eece4c6fa7f1a8fc851f17ce8f9708bc49d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717164"
---
# <a name="corbindtoruntimehost-function"></a>Функция CorBindToRuntimeHost

Позволяет узлам загружать в процесс указанную версию среды CLR.  
  
 Эта функция является устаревшей в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,
    [in] LPCWSTR       pwszBuildFlavor,
    [in] LPCWSTR       pwszHostConfigFile,
    [in] VOID*         pReserved,
    [in] DWORD         startupFlags,
    [in] REFCLSID      rclsid,
    [in] REFIID        riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pwszVersion`  
 окне Строка, описывающая версию среды CLR, которую требуется загрузить.  
  
 Номер версии в платформа .NET Framework состоит из четырех частей, разделенных точками: *основной. дополнительный. сборка. Редакция*. Строка, передаваемая как, `pwszVersion` должна начинаться с символа "v", за которым следуют первые три части номера версии (например, "v 1.0.1529").  
  
 Некоторые версии среды CLR устанавливаются с инструкцией политики, которая определяет совместимость с предыдущими версиями среды CLR. По умолчанию оболочка запуска выполняет проверку на `pwszVersion` соответствие инструкциям политики и загружает последнюю версию среды выполнения, совместимую с запрашиваемой версией. Узел может заставить оболочку пропускать вычисление политики и загружать точную версию, указанную в `pwszVersion` , передав значение STARTUP_LOADER_SAFEMODE для `startupFlags` параметра.  
  
 Если `pwszVersion` — `null,` метод не загружает ни одной версии среды CLR. Вместо этого он возвращает CLR_E_SHIM_RUNTIMELOAD, который указывает, что ему не удалось загрузить среду выполнения.  
  
 `pwszBuildFlavor`  
 окне Строка, указывающая, загружать ли сервер или рабочую станцию сборку среды CLR. Допустимые значения: `svr` и `wks`. Сборка сервера оптимизирована для использования нескольких процессоров для сборок мусора, а сборка рабочей станции оптимизирована для клиентских приложений, работающих на однопроцессорном компьютере.  
  
 Если параметр `pwszBuildFlavor` имеет значение null, загружается сборка рабочей станции. При запуске на однопроцессорном компьютере сборка рабочей станции всегда загружается, даже если параметр `pwszBuildFlavor` имеет значение `svr` . Однако если задано `pwszBuildFlavor` значение `svr` и задана параллельная сборка мусора (см `startupFlags` . Описание параметра), то загружается серверная сборка.  
  
> [!NOTE]
> Параллельная сборка мусора не поддерживается в приложениях, использующих Эмулятор WOW64 x86 в 64-разрядных системах, которые реализуют архитектуру Intel Itanium (прежнее название — IA-64). Дополнительные сведения об использовании WOW64 в 64-разрядных системах Windows см. в разделе [выполнение 32-разрядных приложений](/windows/desktop/WinProg64/running-32-bit-applications).  
  
 `pwszHostConfigFile`  
 окне Имя файла конфигурации узла, указывающего версию среды CLR для загрузки. Если имя файла не содержит полного пути, предполагается, что файл находится в том же каталоге, что и исполняемый файл, выполняющий вызов.  
  
 `pReserved`  
 окне Зарезервировано для будущего расширения.  
  
 `startupFlags`  
 окне Набор флагов, управляющих параллельной сборкой мусора, нейтральным к домену кодом и поведением `pwszVersion` параметра. Значение по умолчанию — один домен, если флаг не установлен. Список поддерживаемых значений см. в разделе [перечисление STARTUP_FLAGS](startup-flags-enumeration.md).  
  
 `rclsid`  
 окне Объект `CLSID` coclass, реализующий интерфейс [ICorRuntimeHost](icorruntimehost-interface.md) или [ICLRRuntimeHost](iclrruntimehost-interface.md) . Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 окне `IID` Запрашиваемый интерфейс. Поддерживаемые значения: IID_ICorRuntimeHost или IID_ICLRRuntimeHost.  
  
 `ppv`  
 заполняет Указатель интерфейса на версию загруженной среды выполнения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntime](corbindtoruntime-function.md)
- [Функция CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md)
- [Функция CorBindToRuntimeEx](corbindtoruntimeex-function.md)
- [Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)
- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

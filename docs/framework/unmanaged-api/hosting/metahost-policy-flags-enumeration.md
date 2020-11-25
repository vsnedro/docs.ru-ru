---
title: Перечисление METAHOST_POLICY_FLAGS
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
ms.openlocfilehash: 16fb112cf5b209091001872567c95bb0b3a8ab61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729997"
---
# <a name="metahost_policy_flags-enumeration"></a>Перечисление METAHOST_POLICY_FLAGS

Предоставляет политики привязки, которые являются общими для большинства хостов среды выполнения. Это перечисление используется методом [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|Определяет политику высокой совместимости, которая не учитывает среду CLR, которая загружается в текущий процесс. Вместо этого он учитывает только установленные CLR и параметры компонента, как производные от самого файла сборки, объявленной встроенной версии или файла конфигурации.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Применяет политику обновления к результату привязки к версии, если точное соответствие не найдено на основе содержимого HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\ . нетфрамеворк\полици\упградес. Это тот же результат, что и [RUNTIME_INFO_UPGRADE_VERSION](runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Результаты привязки возвращаются, как если бы изображение, предоставленное для вызова, было запущено в новом процессе. В настоящее время не `GetRequestedRuntime` учитывает набор сред выполнения, допускающих загрузку, и привязывает их к набору установленных сред выполнения. Этот флаг позволяет узлу определить, к какой среде выполнения будет привязан EXE-файл при запуске.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Если `GetRequestedRuntime` приложению не удается найти среду выполнения, совместимую с входными параметрами, отображается диалоговое окно ошибки. Начиная с .NET Framework 4,5, это диалоговое окно с сообщением об ошибке может иметь форму диалогового окна компонента Windows, в котором спрашивается, нужно ли пользователю включить соответствующую функцию.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` использует образ процесса (и любой соответствующий файл конфигурации) в качестве дополнительных входных данных для процесса привязки. По умолчанию не `GetRequestedRuntime` выполняет откат к пути образа процесса (как правило, к исполняемому файлу, который использовался для запуска процесса) при определении среды выполнения для привязки.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` необходимо проверить, установлен ли соответствующий SKU, если в файле конфигурации нет доступных сведений. Это позволяет приложениям, не имеющим файлов конфигурации, корректно завершать работу на более мелких SKU, чем установка по умолчанию .NET Framework. По умолчанию не `GetRequestedRuntime` проверяет, установлен ли соответствующий SKU, если атрибут sku не указан в элементе файла конфигурации `<supportedRuntime />` .|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` следует пропускать SEM_FAILCRITICALERRORS (который задается вызовом функции [функцию SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) ) и выводить диалоговое окно ошибки. По умолчанию SEM_FAILCRITICALERRORS подавляет диалоговое окно ошибки. Возможно, он был унаследован от другого процесса, и в вашем сценарии может быть нежелательным сообщение об ошибке.|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Размещение перечислений](hosting-enumerations.md)
- [Метод GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md)

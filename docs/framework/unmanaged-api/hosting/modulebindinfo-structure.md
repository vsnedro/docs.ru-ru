---
title: Структура ModuleBindInfo
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: 505015877985492edab4b761b379f33f1e5c6660
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729984"
---
# <a name="modulebindinfo-structure"></a>Структура ModuleBindInfo

Предоставляет подробные сведения о модуле, на который указывает ссылка, и содержащей его сборку.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`dwAppDomainId`|Уникальный идентификатор для `IStream` , возвращаемый вызовом метода [IHostAssemblyStore::P ровидемодуле](ihostassemblystore-providemodule-method.md) , из которого загружается указанный модуль.|  
|`lpAssemblyIdentity`|Уникальный идентификатор сборки, содержащей упоминаемый модуль.|  
|`lpModuleName`|Имя модуля, на который указывает ссылка.|  
  
## <a name="remarks"></a>Комментарии  

 `ModuleBindInfo` передается в качестве параметра в `IHostAssemblyStore::ProvideModule` . Узел предоставляет уникальный идентификатор среде CLR `dwAppDomainId` . После вызова метода [IHostAssemblyStore::P ровидеассембли](ihostassemblystore-provideassembly-method.md) среда выполнения использует идентификатор, чтобы определить, `IStream` сопоставлено ли содержимое объекта. Если это так, среда выполнения загружает существующую копию вместо повторного сопоставления потока. Среда выполнения также использует этот идентификатор в качестве ключа поиска для потоков, возвращаемых из вызовов `IHostAssemblyStore::ProvideAssembly` метода. Таким образом, идентификатор должен быть уникальным для запросов модуля, а также для запросов сборки.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры размещения](hosting-structures.md)
- [Структура AssemblyBindInfo](assemblybindinfo-structure.md)
- [Интерфейс ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Интерфейс ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](ihostassemblymanager-interface.md)

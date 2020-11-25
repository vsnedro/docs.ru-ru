---
title: Метод IAssemblyCache::CreateAssemblyCacheItem
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
ms.openlocfilehash: b417377ea1d0746e563490d87cc9a988e857d943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697042"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a>Метод IAssemblyCache::CreateAssemblyCacheItem

Возвращает ссылку на новый объект [IAssemblyCacheItem](iassemblycacheitem-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwFlags`  
 окне Флаги, определенные в Fusion. idl. Поддерживаются следующие значения.  
  
- IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)  
  
- IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)  
  
 `pvReserved`  
 окне Зарезервировано для будущего расширения. `pvReserved` должен быть пустой ссылкой.  
  
 `ppAsmItem`  
 заполняет Возвращаемый `IAssemblyCacheItem` указатель.  
  
 `pszAssemblyName`  
 [входные, необязательные] Неканонические пары, разделенные запятыми `name=value` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IAssemblyCache](iassemblycache-interface.md)
- [Интерфейс IAssemblyCacheItem](iassemblycacheitem-interface.md)

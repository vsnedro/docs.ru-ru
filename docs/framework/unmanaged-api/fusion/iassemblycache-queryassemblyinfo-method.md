---
description: 'Дополнительные сведения о методе: IAssemblyCache:: Куеряссемблинфо'
title: Метод IAssemblyCache::QueryAssemblyInfo
ms.date: 03/30/2017
api_name:
- IAssemblyCache.QueryAssemblyInfo
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type:
- apiref
ms.openlocfilehash: b3aa0064e24b22cf0af8b4e8d23a8b92d2f1ac34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760918"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a>Метод IAssemblyCache::QueryAssemblyInfo

Возвращает запрошенные данные о указанной сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwFlags`  
 окне Флаги, определенные в Fusion. idl. Поддерживаются следующие значения.  
  
- QUERYASMINFO_FLAG_VALIDATE (0x00000001)  
  
- QUERYASMINFO_FLAG_GETSIZE (0x00000002)  
  
 `pszAssemblyName`  
 окне Имя сборки, для которой будут получены данные.  
  
 `pAsmInfo`  
 [вход, выход] Структура [ASSEMBLY_INFO](assembly-info-structure.md) , содержащая данные о сборке.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyCache](iassemblycache-interface.md)

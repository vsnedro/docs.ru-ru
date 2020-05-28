---
title: Метод IMetaDataEmit::SetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: 0d34c7a2992a2779b96ec87f1a0175d8fcbce34a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007797"
---
# <a name="imetadataemitsetpinvokemap-method"></a>Метод IMetaDataEmit::SetPinvokeMap
Задает или изменяет функции сигнатуры PInvoke метода, как определено в предыдущем вызове [IMetaDataEmit::D ефинепинвокемап](imetadataemit-definepinvokemap-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tk`  
 окне Объект, `mdToken` к которому применяются сведения о сопоставлении.  
  
 `dwMappingFlags`  
 окне Флаги, используемые PInvoke для сопоставления. Это битовая маска `CorPinvokeMap` значений.  
  
 `szImportName`  
 окне Имя целевого экспорта в собственной библиотеке DLL.  
  
 `mrImportDLL`  
 окне `mdModuleRef`Маркер для целевой неуправляемой библиотеки DLL.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)

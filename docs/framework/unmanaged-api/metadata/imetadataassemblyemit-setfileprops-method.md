---
title: Метод IMetaDataAssemblyEmit::SetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 9cf5f3d926c1e742dd9134e7bf292df53e1a4909
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720182"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a>Метод IMetaDataAssemblyEmit::SetFileProps

Изменяет указанную структуру метаданных `File`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `file`  
 окне Токен метаданных, указывающий `File` структуру метаданных, которую необходимо изменить.  
  
 `pbHashValue`  
 окне Указатель на хэш-данные, связанные с файлом.  
  
 `cbHashValue`  
 окне Размер в байтах для `pbHashValue` .  
  
 `dwFileFlags`  
 окне Побитовое сочетание значений [корфилефлагс](corfileflags-enumeration.md) , задающих различные атрибуты файла.  
  
## <a name="remarks"></a>Комментарии  

 Чтобы создать `File` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинефиле](imetadataassemblyemit-definefile-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)

---
description: 'Дополнительные сведения о методе: метод iclrstrongname:: StrongNameGetBlobFromImage'
title: Метод ICLRStrongName::StrongNameGetBlobFromImage
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
ms.openlocfilehash: 32f04e21f1f08f3872ccdd27a64f39ea29d7e060
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799620"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a>Метод ICLRStrongName::StrongNameGetBlobFromImage

Получает двоичное представление образа сборки по указанному адресу памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pbBase`  
 окне Адрес сопоставленного манифеста сборки в памяти.  
  
 `dwLength`  
 окне Размер изображения в байтах в `pbBase` .  
  
 `pbBlob`  
 окне Буфер для хранения двоичного представления изображения.  
  
 `pcbBlob`  
 [вход, выход] Запрошенный максимальный размер (в байтах) `pbBlob` . При возврате фактический размер (в байтах) для `pbBlob` .  
  
## <a name="return-value"></a>Возвращаемое значение  

 `S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameGetBlob](iclrstrongname-strongnamegetblob-method.md)
- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)

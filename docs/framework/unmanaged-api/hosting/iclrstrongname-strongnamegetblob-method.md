---
description: 'Дополнительные сведения о методе: метод iclrstrongname:: StrongNameGetBlob'
title: Метод ICLRStrongName::StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
ms.openlocfilehash: 2b63ebd9c48ad18eef60f83c68fe412a4bd0d94f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799633"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a>Метод ICLRStrongName::StrongNameGetBlob

Заполняет указанный буфер двоичным представлением исполняемого файла по указанному адресу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `wszFilePath`  
 окне Допустимый путь к исполняемому файлу для загрузки.  
  
 `pbBlob`  
 окне Буфер, в который загружается исполняемый файл.  
  
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

- [Метод StrongNameGetBlobFromImage](iclrstrongname-strongnamegetblobfromimage-method.md)
- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)

---
description: 'Дополнительные сведения о методе: метод iclrstrongname:: StrongNameKeyGen'
title: Метод ICLRStrongName::StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
ms.openlocfilehash: c445e1f0290d907f7820c0000f602f2668f59103
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799564"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a>Метод ICLRStrongName::StrongNameKeyGen

Создает пару открытого и закрытого ключей для использования строгого имени.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `wszKeyContainer`  
 окне Запрошенное имя контейнера ключей. `wszKeyContainer` значение должно быть непустой строкой или null для создания временного имени.  
  
 `dwFlags`  
 окне Значение типа, указывающее, следует ли оставлять зарегистрированный ключ. Поддерживаются следующие значения.  
  
- 0x00000000 — используется, если `wszKeyContainer` параметр имеет значение null, чтобы создать имя контейнера временного ключа.  
  
- 0x00000001 ( `SN_LEAVE_KEY` ) — указывает, что ключ должен оставаться зарегистрированным.  
  
 `ppbKeyBlob`  
 заполняет Возвращаемая пара открытого и закрытого ключей.  
  
 `pcbKeyBlob`  
 заполняет Размер (в байтах) `ppbKeyBlob` .  
  
## <a name="return-value"></a>Возвращаемое значение  

 `S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Remarks  

 Метод [метод iclrstrongname:: StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md) создает ключ 1024-bit. После извлечения ключа необходимо вызвать метод [метод iclrstrongname:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) , чтобы освободить выделенную память.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameKeyGenEx](iclrstrongname-strongnamekeygenex-method.md)
- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)

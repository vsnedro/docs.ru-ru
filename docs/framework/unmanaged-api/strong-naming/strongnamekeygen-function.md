---
description: Дополнительные сведения о функции StrongNameKeyGen
title: Функция StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
ms.openlocfilehash: c5f4cfcfa9030ae856acf5fd59ab34a2b8338670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636271"
---
# <a name="strongnamekeygen-function"></a>Функция StrongNameKeyGen

Создает пару открытого и закрытого ключей для использования строгого имени.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `wszKeyContainer`  
 окне Запрошенное имя контейнера ключей. `wszKeyContainer` должен быть непустой строкой или иметь значение NULL для создания временного имени.  
  
 `dwFlags`  
 окне Указывает, следует ли оставить зарегистрированный ключ. Поддерживаются следующие значения.  
  
- 0x00000000 — используется, если `wszKeyContainer` параметр имеет значение null, чтобы создать имя контейнера временного ключа.  
  
- 0x00000001 ( `SN_LEAVE_KEY` ) — указывает, что ключ должен оставаться зарегистрированным.  
  
 `ppbKeyBlob`  
 заполняет Возвращаемая пара открытого и закрытого ключей.  
  
 `pcbKeyBlob`  
 заполняет Размер (в байтах) `ppbKeyBlob` .  
  
## <a name="return-value"></a>Возвращаемое значение  

 `true` При успешном завершении; в противном случае — `false` .  
  
## <a name="remarks"></a>Remarks  

 `StrongNameKeyGen`Функция создает 1024-разрядный ключ. После извлечения ключа необходимо вызвать функцию [StrongNameFreeBuffer](strongnamefreebuffer-function.md) , чтобы освободить выделенную память.  
  
 Если `StrongNameKeyGen` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [Метод StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)

---
title: Метод ICLRMetadataLocator::GetMetadata
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
ms.openlocfilehash: f0ba2342e9704ba06dd1d3612f699298c734a5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723523"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a>Метод ICLRMetadataLocator::GetMetadata

Вызывается службами доступа к данным среды CLR для получения метаданных изображения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `imagePath`  
 окне Строка, указывающая путь к файлу изображения.  
  
 `imageTimestamp`  
 окне Метка времени файла изображения.  
  
 `imageSize`  
 окне Размер файла изображения.  
  
 `mvid`  
 окне Глобальный уникальный идентификатор изображения.  
  
 `mdRva`  
 окне Относительный виртуальный адрес (RVA) метаданных. Адрес отсчитывается относительно базового адреса образа.  
  
 `flags`  
 [in] Зарезервирован для будущего использования.  
  
 `bufferSize`  
 окне Размер буфера, в который следует поместить метаданные.  
  
 `buffer`  
 заполняет Буфер для размещения метаданных.  
  
 `dataSize`  
 заполняет Размер возвращаемых метаданных.  
  
## <a name="remarks"></a>Комментарии  

 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRMetadataLocator](iclrmetadatalocator-interface.md)

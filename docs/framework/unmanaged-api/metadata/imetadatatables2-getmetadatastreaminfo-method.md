---
description: 'Дополнительные сведения о методе: IMetaDataTables2:: GetMetaDataStreamInfo'
title: Метод IMetaDataTables2::GetMetaDataStreamInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 323c31931cc97f18ff09df83c57153a3629d0a10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799252"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a>Метод IMetaDataTables2::GetMetaDataStreamInfo

Возвращает имя, размер и содержимое потока метаданных по указанному индексу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ix`  
 окне Индекс запрошенного потока метаданных.  
  
 `ppchName`  
 заполняет Указатель на имя потока.  
  
 `ppv`  
 заполняет Указатель на поток метаданных.  
  
 `pcb`  
 заполняет Размер (в байтах) `ppv` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataTables2](imetadatatables2-interface.md)
- [Интерфейс IMetaDataTables](imetadatatables-interface.md)

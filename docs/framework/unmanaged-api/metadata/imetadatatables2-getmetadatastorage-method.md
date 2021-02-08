---
description: 'Дополнительные сведения о методе: IMetaDataTables2:: Жетметадатастораже'
title: Метод IMetaDataTables2::GetMetaDataStorage
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
ms.openlocfilehash: df6bbc69be05986dc6d4f143cec7ec09a2d78ee5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799256"
---
# <a name="imetadatatables2getmetadatastorage-method"></a>Метод IMetaDataTables2::GetMetaDataStorage

Возвращает размер и содержимое метаданных, хранящихся в указанном разделе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppvMd`  
 [вход, выход] Указатель на раздел метаданных.  
  
 `pcbMd`  
 заполняет Размер потока метаданных.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataTables2](imetadatatables2-interface.md)
- [Интерфейс IMetaDataTables](imetadatatables-interface.md)

---
description: 'Дополнительные сведения о методе: IMetaDataTables:: BLOB'
title: Метод IMetaDataTables::GetBlob
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
ms.openlocfilehash: 733f94c280283e00b644fe7811d450efbc7e1e7c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688394"
---
# <a name="imetadatatablesgetblob-method"></a>Метод IMetaDataTables::GetBlob

Возвращает указатель на большой двоичный объект (BLOB) по указанному индексу столбца.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ixBlob`  
 окне Адрес памяти, из которого будет получено значение `ppData` .  
  
 `pcbData`  
 заполняет Указатель на размер в байтах `ppData` .  
  
 `ppData`  
 заполняет Указатель на указатель на извлекаемые двоичные данные.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataTables](imetadatatables-interface.md)
- [Интерфейс IMetaDataTables2](imetadatatables2-interface.md)

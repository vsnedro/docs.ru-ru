---
description: 'Дополнительные сведения о методе: IMetaDataTables:: Жеткодедтокенинфо'
title: Метод IMetaDataTables::GetCodedTokenInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
ms.openlocfilehash: 982a13636d8b4572113038eaa658158e6c2ca966
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688290"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a>Метод IMetaDataTables::GetCodedTokenInfo

Возвращает указатель на массив токенов, связанных с указанным индексом строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ixCdTkn`  
 окне Тип возвращаемого закодированного токена.  
  
 `pcTokens`  
 заполняет Указатель на длину `ppTokens` .  
  
 `ppTokens`  
 заполняет Указатель на указатель на массив, содержащий список возвращенных токенов.  
  
 `ppName`  
 заполняет Указатель на указатель на имя маркера в `ixCdTkn` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataTables](imetadatatables-interface.md)
- [Интерфейс IMetaDataTables2](imetadatatables2-interface.md)

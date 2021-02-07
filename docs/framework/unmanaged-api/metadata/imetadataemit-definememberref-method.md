---
description: 'Дополнительные сведения: IMetaDataEmit::D метод Ефинемемберреф'
title: Метод IMetaDataEmit::DefineMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: 1d88294cea14369c8a8f16b6048f96472fbb9502
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753423"
---
# <a name="imetadataemitdefinememberref-method"></a>Метод IMetaDataEmit::DefineMemberRef

Определяет ссылку на член модуля вне текущей области и получает маркер для этого эталонного определения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tkImport`  
 окне Токен для класса или интерфейса целевого элемента, если элемент не является глобальным; Если элемент является глобальным, `mdModuleRef` маркер для этого файла.  
  
 `szName`  
 окне Имя целевого элемента.  
  
 `pvSigBlob`  
 окне Сигнатура целевого элемента.  
  
 `cbSigBlob`  
 окне Число байтов в `pvSigBlob` .  
  
 `pmr`  
 заполняет `mdMemberRef` Назначенный маркер.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)

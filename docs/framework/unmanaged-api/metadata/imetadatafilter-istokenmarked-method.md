---
description: 'Дополнительные сведения о методе: IMetaDataFilter:: Истокенмаркед'
title: Метод IMetaDataFilter::IsTokenMarked
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
ms.openlocfilehash: dddb0aa9040a2f5ef3ec972bb37a9e8778ddffe8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677792"
---
# <a name="imetadatafilteristokenmarked-method"></a>Метод IMetaDataFilter::IsTokenMarked

Возвращает значение, указывающее, помечен ли заданный маркер метаданных как обработанный.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tk`  
 окне Токен для проверки на наличие метки обработки.  
  
 `pIsMarked`  
 заполняет Значение, равное, если объект был `true` `tk` обработан; в противном случае — `false` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataFilter](imetadatafilter-interface.md)

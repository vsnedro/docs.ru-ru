---
description: 'Дополнительные сведения: IMetaDataEmit::D метод Ефинесекуритяттрибутесет'
title: Метод IMetaDataEmit::DefineSecurityAttributeSet
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
ms.openlocfilehash: 3512857ca23d65389b0e150bd24234d272ddd9b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784058"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a>Метод IMetaDataEmit::DefineSecurityAttributeSet

Создает набор разрешений безопасности для присоединения к объекту, на который ссылается указанный токен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tkObj`  
 окне Токен, к которому присоединены сведения о безопасности.  
  
 `rSecAttrs`  
 окне Массив `COR_SECATTR` структур.  
  
 `cSecAttrs`  
 окне Количество элементов в `rSecAttrs` .  
  
 `pulErrorAttr`  
 заполняет В случае сбоя метода указывает индекс в `rSecAttrs` элементе, вызвавшем проблему.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)

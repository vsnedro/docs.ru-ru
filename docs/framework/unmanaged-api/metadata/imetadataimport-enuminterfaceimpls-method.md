---
description: 'Дополнительные сведения: метод IMetaDataImport:: Енуминтерфацеимплс'
title: Метод IMetaDataImport::EnumInterfaceImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: 5276d1edb3be0cae76b18a06241dc6b9952e1a72
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649420"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>Метод IMetaDataImport::EnumInterfaceImpls

Перечисляет все интерфейсы, реализованные указанным `TypeDef` .
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель.  
  
 `td`  
 окне Токен TypeDef, маркеры MethodDef которого представляют реализации интерфейса для перечисления.  
  
 `rImpls`  
 заполняет Массив, используемый для хранения маркеров MethodDef.  
  
 `cMax`  
 окне Максимальная длина `rImpls` массива.  
  
 `pcImpls`  
 заполняет Фактическое число токенов, возвращаемых в `rImpls` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` успешно возвращено.|  
|`S_FALSE`|Отсутствуют токены MethodDef для перечисления. В этом случае `pcImpls` значение равно нулю.|  

## <a name="remarks"></a>Remarks

Перечисление Возвращает коллекцию `mdInterfaceImpl` токенов для каждого интерфейса, реализованного с помощью указанного объекта `TypeDef` . Маркеры интерфейса возвращаются в том порядке, в котором были указаны интерфейсы (с помощью `DefineTypeDef` или `SetTypeDefProps` ). Свойства возвращаемых `mdInterfaceImpl` токенов можно запрашивать с помощью [жетинтерфацеимплпропс](imetadataimport-getinterfaceimplprops-method.md).
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

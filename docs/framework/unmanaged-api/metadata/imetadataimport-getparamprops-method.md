---
description: 'Дополнительные сведения: метод IMetaDataImport:: GetParamProps'
title: Метод IMetaDataImport::GetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
ms.openlocfilehash: 2c48215836dfb3ae44edc9a2bf10d4028fd82bb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728123"
---
# <a name="imetadataimportgetparamprops-method"></a>Метод IMetaDataImport::GetParamProps

Возвращает значения метаданных для параметра, на который ссылается указанный токен ParamDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tk`  
 окне Токен Парамдеф, представляющий параметр, для которого возвращаются метаданные.  
  
 `pmd`  
 заполняет Указатель на токен MethodDef, представляющий метод, который принимает параметр.  
  
 `pulSequence`  
 заполняет Порядковый номер параметра в списке аргументов метода.  
  
 `szName`  
 заполняет Буфер для хранения имени параметра.  
  
 `cchName`  
 окне Запрошенный размер в расширенных символах `szName` .  
  
 `pchName`  
 заполняет Возвращаемый размер в расширенных символах `szName` .  
  
 `pdwAttr`  
 заполняет Указатель на любые флаги атрибутов, связанные с параметром. Это битовая маска `CorParamAttr` значений.  
  
 `pdwCPlusTypeFlag`  
 заполняет Указатель на флаг, указывающий, что параметр является <xref:System.ValueType> .  
  
 `ppValue`  
 заполняет Указатель на константную строку, возвращенную параметром.  
  
 `pcchValue`  
 заполняет Размер `ppValue` в расширенных символах или нуль, если не содержит `ppValue` строку.  
  
## <a name="remarks"></a>Remarks

Значения последовательности в `pulSequence` аргументе начинаются с 1 для параметров. Возвращаемое значение имеет порядковый номер 0.

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

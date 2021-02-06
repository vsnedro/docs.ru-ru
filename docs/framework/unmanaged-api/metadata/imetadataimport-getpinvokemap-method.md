---
description: 'Дополнительные сведения: метод IMetaDataImport:: Жетпинвокемап'
title: Метод IMetaDataImport::GetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
ms.openlocfilehash: fcf45f4741709423aa48dcf895dfc4be276e19fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649446"
---
# <a name="imetadataimportgetpinvokemap-method"></a>Метод IMetaDataImport::GetPinvokeMap

Возвращает токен ModuleRef, представляющий целевую сборку вызова PInvoke.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tk`  
 окне Токен FieldDef или MethodDef для получения метаданных сопоставления PInvoke для.  
  
 `pdwMappingFlags`  
 заполняет Указатель на флаги, используемые для сопоставления. Это значение является битовой маской из перечисления [CorPinvokeMap](corpinvokemap-enumeration.md) .  
  
 `szImportName`  
 заполняет Имя неуправляемой целевой библиотеки DLL.  
  
 `cchImportName`  
 окне Размер в расширенных символах `szImportName` .  
  
 `pchImportName`  
 заполняет Число расширенных символов, возвращаемых в `szImportName` .  
  
 `pmrImportDLL`  
 заполняет Указатель на токен ModuleRef, представляющий неуправляемую библиотеку целевых объектов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

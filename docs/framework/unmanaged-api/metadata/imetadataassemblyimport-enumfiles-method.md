---
description: 'Дополнительные сведения о методе: IMetaDataAssemblyImport:: Енумфилес'
title: Метод IMetaDataAssemblyImport::EnumFiles
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: 25282edd081e937e4c84334f9f004e201b9db46f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671026"
---
# <a name="imetadataassemblyimportenumfiles-method"></a>Метод IMetaDataAssemblyImport::EnumFiles

Перечисляет файлы, на которые ссылается текущий манифест сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель. При первом вызове этого метода это значение должно быть нулевым.  
  
 `rFiles`  
 заполняет Массив, используемый для хранения `mdFile` маркеров метаданных.  
  
 `cMax`  
 окне Максимальное число `mdFile` токенов, которые могут быть помещены в `rFiles` .  
  
 `pcTokens`  
 заполняет Количество маркеров, которые `mdFile` в действительности помещаются в `rFiles` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumFiles` успешно возвращено.|  
|`S_FALSE`|Нет токенов для перечисления. В этом случае `pcTokens` имеет значение 0.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)

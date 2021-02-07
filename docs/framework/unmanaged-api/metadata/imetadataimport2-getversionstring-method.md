---
description: 'Дополнительные сведения о методе: IMetaDataImport2:: GetVersionString'
title: Метод IMetaDataImport2::GetVersionString
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
ms.openlocfilehash: 6f7e296607dc3167936c69d52a8baae4f5555b88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688563"
---
# <a name="imetadataimport2getversionstring-method"></a>Метод IMetaDataImport2::GetVersionString

Возвращает номер версии среды выполнения, которая использовалась для построения сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzBuf`  
 заполняет Массив для хранения строки, указывающей версию.  
  
 `ccBufSize`  
 окне Размер массива в расширенных символах `pwzBuf` .  
  
 `pccBufSize`  
 заполняет Число расширенных символов, включая знак завершения null, возвращаемый в `pwzBuf` массиве.  
  
## <a name="remarks"></a>Remarks  

 `GetVersionString`Метод получает встроенную версию текущей области метаданных. Если область не была сохранена, она не будет иметь встроенной версии и будет возвращена пустая строка.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)

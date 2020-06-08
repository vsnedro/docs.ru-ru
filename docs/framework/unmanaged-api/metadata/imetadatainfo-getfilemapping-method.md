---
title: Метод IMetaDataInfo::GetFileMapping
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
ms.openlocfilehash: 5ef5d9ae3da4dff13a461162f0ba3466d3d8192c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501265"
---
# <a name="imetadatainfogetfilemapping-method"></a>Метод IMetaDataInfo::GetFileMapping
Возвращает область памяти сопоставленного файла и тип сопоставления.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppvData`  
 заполняет Указатель на начало сопоставленного файла.  
  
 `pcbData`  
 заполняет Размер сопоставленной области. Если `pdwMappingType` имеет значение `fmFlat` , то это размер файла.  
  
 `pdwMappingType`  
 заполняет Значение [CorFileMapping](corfilemapping-enumeration.md) , указывающее тип сопоставления. Текущая реализация среды CLR всегда возвращает `fmFlat` . Другие значения зарезервированы для использования в будущем. Однако всегда следует проверять возвращаемое значение, так как в будущих версиях или выпусках служб могут быть включены другие значения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|Все выходные данные заполнены.|  
|`E_INVALIDARG`|Значение NULL передано в качестве значения аргумента.|  
|`COR_E_NOTSUPPORTED`|Реализация CLR не может предоставить сведения о области памяти. Это может происходить по следующим причинам:<br /><br /> — Область метаданных была открыта с помощью `ofWrite` `ofCopyMemory` флага или.<br />— Область метаданных была открыта без `ofReadOnly` флага.<br />— Метод [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) использовался для открытия только части файла с метаданными.<br />— Файл не является переносимым исполняемым файлом (PE). **Примечание.**  Эти условия зависят от реализации CLR и, скорее всего, будут ослаблены в будущих версиях среды CLR.|  
  
## <a name="remarks"></a>Примечания  
 Память, `ppvData` на которую указывает указатель, допустима, только если базовая область метаданных открыта.  
  
 Чтобы этот метод работал, при сопоставлении метаданных файла на диске с памятью путем вызова метода [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) необходимо указать `ofReadOnly` флаг и не указывать `ofWrite` `ofCopyMemory` флаг или.  
  
 Выбранный тип сопоставления файлов для каждой области зависит от конкретной реализации среды CLR. Он не может быть задан пользователем. Текущая реализация CLR всегда возвращает `fmFlat` в `pdwMappingType` , но это может измениться в будущих версиях CLR или в будущих выпусках данной версии службы. Всегда следует проверять возвращаемое значение в `pdwMappingType` , поскольку разные типы будут иметь разные макеты и смещения.  
  
 Передача значения NULL для любого из трех параметров не поддерживается. Метод возвращает значение `E_INVALIDARG` , и ни один из выходных данных не заполнен. Пропуск типа сопоставления или размера региона может привести к аварийному завершению программы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataInfo](imetadatainfo-interface.md)
- [Перечисление CorFileMapping](corfilemapping-enumeration.md)

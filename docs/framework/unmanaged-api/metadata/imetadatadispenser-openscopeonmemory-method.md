---
title: Метод IMetaDataDispenser::OpenScopeOnMemory
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 69e5e05012d2b44a76a986591ec990f66bf8ae20
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007329"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>Метод IMetaDataDispenser::OpenScopeOnMemory
Открывает область памяти, которая содержит существующие метаданные. Это значит, что этот метод открывает указанную область памяти, в которой существующие данные обрабатываются как метаданные.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pData`  
 окне Указатель, указывающий начальный адрес области памяти.  
  
 `cbData`  
 окне Размер области памяти в байтах.  
  
 `dwOpenFlags`  
 окне Значение перечисления [коропенфлагс](coropenflags-enumeration.md) , определяющее режим (чтение, запись и т. д.) для открытия.  
  
 `riid`  
 окне Идентификатор IID требуемого интерфейса метаданных, который должен быть возвращен; вызывающий объект будет использовать интерфейс для импорта (чтения) или выдачи (записи) метаданных.  
  
 Значение `riid` должно указывать один из интерфейсов "import" или "Emit". Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 или IID_IMetaDataImport2.  
  
 `ppIUnk`  
 заполняет Указатель на возвращаемый интерфейс.  
  
## <a name="remarks"></a>Примечания  
 Копию метаданных в памяти можно запросить с помощью методов из одного из интерфейсов "Импорт" или добавить к методам из одного из интерфейсов "выдачи".  
  
 `OpenScopeOnMemory`Метод аналогичен методу [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) , за исключением того, что интересующие метаданные уже существуют в памяти, а не в файле на диске.  
  
 Если целевая область памяти не содержит метаданных среды CLR, `OpenScopeOnMemory` метод завершится ошибкой.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataDispenser](imetadatadispenser-interface.md)
- [Интерфейс IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

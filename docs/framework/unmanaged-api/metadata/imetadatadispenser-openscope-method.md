---
title: Метод IMetaDataDispenser::OpenScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 8d9de753f1c44338a96e990def80643d591f2a8b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007472"
---
# <a name="imetadatadispenseropenscope-method"></a>Метод IMetaDataDispenser::OpenScope
Открывает существующий файл на диске и сопоставляет его метаданные с памятью.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szScope`  
 окне Имя открываемого файла. Файл должен содержать метаданные среды CLR.  
  
 `dwOpenFlags`  
 окне Значение перечисления [коропенфлагс](coropenflags-enumeration.md) , определяющее режим (чтение, запись и т. д.) для открытия.  
  
 `riid`  
 окне Идентификатор IID требуемого интерфейса метаданных, который должен быть возвращен; вызывающий объект будет использовать интерфейс для импорта (чтения) или выдачи (записи) метаданных.  
  
 Значение `riid` должно указывать один из интерфейсов "import" или "Emit". Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 или IID_IMetaDataImport2.  
  
 `ppIUnk`  
 заполняет Указатель на возвращаемый интерфейс.  
  
## <a name="remarks"></a>Примечания  
 Копию метаданных в памяти можно запросить с помощью методов из одного из интерфейсов "Импорт" или добавить к методам из одного из интерфейсов "выдачи".  
  
 Если целевой файл не содержит метаданные CLR, `OpenScope` метод завершится ошибкой.  
  
 В .NET Framework версии 1,0 и 1,1, если область открыта с параметром `dwOpenFlags` офреад, она может предоставлять общий доступ. То есть, если последующие вызовы `OpenScope` передают имя ранее открытого файла, существующая область используется повторно, а новый набор структур данных не создается. Тем не менее проблемы могут возникать из-за этого общего доступа.  
  
 В .NET Framework версии 2,0 области, открытые с параметром `dwOpenFlags` офреад, больше не являются общими. Используйте значение Офреадонли, чтобы разрешить общий доступ к области. При совместном использовании области запросы, использующие интерфейсы метаданных для чтения и записи, завершатся ошибкой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
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

---
description: 'Дополнительные сведения о методе: IMetaDataTables:: GetColumnInfo'
title: Метод IMetaDataTables::GetColumnInfo
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: 21980567c5f9b364362f7e3ff02ee3a5e60b01ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688238"
---
# <a name="imetadatatablesgetcolumninfo-method"></a>Метод IMetaDataTables::GetColumnInfo

Получает данные о указанном столбце в указанной таблице.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetColumnInfo (
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a>Параметры

=======

 `ixTbl`  
 окне Индекс требуемой таблицы.  
  
 `ixCol`  
 окне Индекс нужного столбца.  
  
 `poCol`  
 заполняет Указатель на смещение столбца в строке.  
  
 `pcbCol`  
 заполняет Указатель на размер столбца в байтах.  
  
 `pType`  
 заполняет Указатель на тип значений в столбце.  
  
 `ppName`  
 заполняет Указатель на указатель на имя столбца.  

## <a name="remarks"></a>Remarks

Возвращаемый тип столбца попадает в диапазон значений:

| птипе                    | Описание   | Вспомогательная функция                   |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0.. 63)   | Избежать           | **исридтипе**<br>**исридортокен** |
| `iCodedToken`..`iCodedTokenMax`<br>(64.. 95) | Закодированный маркер | **искодедтокентипе** <br>**исридортокен** |
| `iSHORT` (96)            | Int16         | **исфикседтипе**                   |
| `iUSHORT` (97)           | UInt16        | **исфикседтипе**                   |
| `iLONG` (98)             | Int32         | **исфикседтипе**                   |
| `iULONG` (99)            | UInt32        | **исфикседтипе**                   |
| `iBYTE` (100)            | Byte          | **исфикседтипе**                   |
| `iSTRING` (101)          | Строка        | **ишеаптипе**                    |
| `iGUID` (102)            | Guid          | **ишеаптипе**                    |
| `iBLOB` (103)            | BLOB-объект          | **ишеаптипе**                    |

Значения, хранящиеся в *куче* (т `IsHeapType == true` . е.), можно считывать с помощью:

- `iSTRING`: **IMetadataTables. GetString**
- `iGUID`: **IMetadataTables. с GUID**
- `iBLOB`: **IMetadataTables. BLOB**

> [!IMPORTANT]
> Чтобы использовать константы, определенные в приведенной выше таблице, включите директиву, `#define _DEFINE_META_DATA_META_CONSTANTS` предоставленную файлом заголовка *COR. h* .

## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataTables](imetadatatables-interface.md)
- [Интерфейс IMetaDataTables2](imetadatatables2-interface.md)

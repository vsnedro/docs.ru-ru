---
title: Метод IMetaDataTables::GetNextUserString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
ms.openlocfilehash: bb53d980a7b2121854748d5117bc539fed125163
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680369"
---
# <a name="imetadatatablesgetnextuserstring-method"></a>Метод IMetaDataTables::GetNextUserString

Возвращает индекс строки, содержащей следующую жестко заданную строку в текущем столбце таблицы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ixUserString`  
 окне Значение индекса из текущего строкового столбца.  
  
 `pNext`  
 заполняет Указатель на индекс строки следующей строки в столбце.  
  
## <a name="remarks"></a>Комментарии  

 Мы не рекомендуем использовать этот метод, так как он не возвращает последовательные результаты. Сведения о таблице GUID см. в документации по Common Language Infrastructure (CLI), особенно в разделе "Partition II: определение метаданных и семантика". Документация доступна в Интернете; см. раздел [ECMA C# and Common Language Infrastructure](../../../standard/components.md#applicable-standards) Standards и [Standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataTables](imetadatatables-interface.md)
- [Интерфейс IMetaDataTables2](imetadatatables2-interface.md)

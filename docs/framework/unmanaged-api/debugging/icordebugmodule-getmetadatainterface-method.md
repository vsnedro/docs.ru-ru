---
description: 'Дополнительные сведения о методе: ICorDebugModule:: Жетметадатаинтерфаце'
title: Метод ICorDebugModule::GetMetaDataInterface
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
ms.openlocfilehash: 39af2560b4c10f6dc490bfba5425e2339a7c1823
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691648"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>Метод ICorDebugModule::GetMetaDataInterface

Возвращает объект интерфейса метаданных, который может использоваться для проверки метаданных модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `riid`  
 окне Идентификатор ссылки, указывающий интерфейс метаданных.  
  
 `ppObj`  
 заполняет Указатель на адрес `T:IUnknown` объекта, который является одним из [интерфейсов метаданных](../metadata/metadata-interfaces.md).  
  
## <a name="remarks"></a>Remarks  

 Отладчик может использовать `GetMetaDataInterface` метод, чтобы создать копию исходных метаданных для модуля, который необходимо сделать для изменения этого модуля. Отладчик вызывает метод `GetMetaDataInterface` [IMetaDataEmit:: саветомемори](../metadata/imetadataemit-savetomemory-method.md) , чтобы получить объект интерфейса [IMetaDataEmit](../metadata/imetadataemit-interface.md) для этого модуля, а затем вызывает методические данные класса, чтобы сохранить копию метаданных модуля в памяти.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метаданные](../metadata/index.md)

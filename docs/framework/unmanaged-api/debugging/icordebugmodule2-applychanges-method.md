---
title: Метод ICorDebugModule2::ApplyChanges
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
ms.openlocfilehash: a6b1a7c9be821890a3f15d8c3297273607f5bedd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709704"
---
# <a name="icordebugmodule2applychanges-method"></a>Метод ICorDebugModule2::ApplyChanges

Применяет изменения в метаданных и изменения в коде промежуточного языка MSIL к выполняющемуся процессу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cbMetadata`  
 окне Размер (в байтах) разностных метаданных.  
  
 `pbMetadata`  
 окне Буфер, содержащий разностные метаданные. Адрес буфера возвращается методом [IMetaDataEmit2:: саведелтатомемори](../metadata/imetadataemit2-savedeltatomemory-method.md) .  
  
 Относительные виртуальные адреса (RVA) в метаданных должны относиться к началу кода MSIL.  
  
 `cbIL`  
 окне Размер (в байтах) разностного кода MSIL.  
  
 `pbIL`  
 окне Буфер, содержащий обновленный код MSIL.  
  
## <a name="remarks"></a>Комментарии  

 `pbMetadata`Параметр находится в особом формате разностных метаданных (в виде выходных данных [IMetaDataEmit2:: саведелтатомемори](../metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata` принимает предыдущие метаданные в качестве основы и описывает отдельные изменения, которые необходимо применить к этой базе.  
  
 В отличие от этого, `pbIL[` параметр] содержит новый код MSIL для обновленного метода и предназначен для полной замены предыдущего MSIL для этого метода.  
  
 Если разностный код MSIL и метаданные были созданы в памяти отладчика, отладчик вызывает метод `ApplyChanges` , чтобы отправить изменения в среду CLR. Среда выполнения обновляет свои таблицы метаданных, помещает новый код MSIL в процесс и настраивает JIT-компиляцию нового MSIL. После применения изменений отладчик должен вызвать [IMetaDataEmit2:: ресетенклог](../metadata/imetadataemit2-resetenclog-method.md) , чтобы подготовиться к следующему сеансу редактирования. Затем отладчик может продолжить процесс.  
  
 Всякий раз, когда отладчик вызывает `ApplyChanges` модуль с разностными метаданными, он должен также вызвать метод [IMetaDataEmit:: ApplyEditAndContinue](../metadata/imetadataemit-applyeditandcontinue-method.md) с теми же разностными метаданными для всех его копий метаданных этого модуля, за исключением копирования, используемой для отправки изменений. Если копия метаданных по каким-либо причинам не синхронизирована с фактическими метаданными, то отладчик всегда может создать копию и получить новую копию.  
  
 В случае `ApplyChanges` сбоя метода сеанс отладки находится в недопустимом состоянии и должен быть перезапущен.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

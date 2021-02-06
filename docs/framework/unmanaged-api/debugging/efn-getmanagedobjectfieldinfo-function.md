---
description: Дополнительные сведения о функции _EFN_GetManagedObjectFieldInfo
title: Функция _EFN_GetManagedObjectFieldInfo
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
ms.openlocfilehash: 749ab286a86db07c1b66ff2b61ff073d15334800
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637892"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a>\_ЕФН \_ жетманажедобжектфиелдинфо, функция

Возвращает смещение от начала объекта до поля и значение поля, используя предоставленный указатель объекта и имя поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `Client`  
 окне Указатель на клиент отладки.  
  
 `objAddr`  
 окне Указатель на управляемый объект.  
  
 сзфиелднаме  
 окне Указатель управляемого объекта на имя поля.  
  
 `pValue`  
 заполняет Значение поля. Этот параметр может быть нулевым.  
  
 `pOffset`  
 заполняет Смещение от `objAddr` до поля. Этот параметр может быть нулевым.  
  
## <a name="remarks"></a>Remarks  

 Если смещение равно 0, смещение не записывается.  
  
 Если в текущем потоке нет управляемого кода, функция возвращает HRESULT SOS_E_NOMANAGEDCODE со значением устройства 0x82 и кодом ошибки 0x1000.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** SOS_Stacktrace. h  
  
 **Версия платформа .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции отладки](debugging-global-static-functions.md)

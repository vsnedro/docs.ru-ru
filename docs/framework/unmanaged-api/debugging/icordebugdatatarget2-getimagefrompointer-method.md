---
description: 'Дополнительные сведения о методе: метод icordebugdatatarget2:: Жетимажефромпоинтер'
title: Метод ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: bcf73fa522072707a7b08d90965fcd38188c2bb5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764402"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a>Метод ICorDebugDataTarget2::GetImageFromPointer

Возвращает базовый адрес и размер модуля из адреса в этом модуле.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `addr`  
 Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее адрес в модуле.  
  
 `pImageBase`  
 заполняет Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.  
  
 `pSize`  
 Указатель на размер модуля.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)

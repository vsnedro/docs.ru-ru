---
description: 'Дополнительные сведения о методе: метод icordebugdatatarget2:: GetSymbolProviderForImage'
title: Метод ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 7b4493b6c0959dc39d955d7691a22ac6905034b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764389"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a>Метод ICorDebugDataTarget2::GetSymbolProviderForImage

Возвращает поставщика символов для модуля из базового адреса модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `imageBaseAddress`  
 окне Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.  
  
 `ppSymProvider`  
 заполняет Указатель на адрес объекта [метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md) .  
  
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

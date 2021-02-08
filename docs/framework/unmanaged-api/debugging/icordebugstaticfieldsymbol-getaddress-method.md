---
description: 'Дополнительные сведения о методе: Икордебугстатикфиелдсимбол::/Address'
title: Метод ICorDebugStaticFieldSymbol::GetAddress
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: 1944839ff6afc31dc3667111397cbb088b95b412
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801011"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a>Метод ICorDebugStaticFieldSymbol::GetAddress

Получает адрес статического поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a>Параметры  

 pRVA  
 [out] Указатель на относительный виртуальный адрес (RVA) статического поля.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)

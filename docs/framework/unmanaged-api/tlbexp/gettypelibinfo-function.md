---
title: Функция GetTypeLibInfo
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
ms.openlocfilehash: e9f6ae9a0fcd6651395c54c2e44973e53668c1ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708326"
---
# <a name="gettypelibinfo-function"></a>Функция GetTypeLibInfo

Возвращает сведения о указанной библиотеке типов, изучая ее структуру [тлибаттр](/windows/win32/api/oaidl/ns-oaidl-tlibattr) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szFile`  
 окне Имя файла библиотеки типов.  
  
 `pTypeLibID`  
 заполняет Идентификатор GUID библиотеки типов.  
  
 `pTypeLibLCID`  
 заполняет ИДЕНТИФИКАТОР локализации библиотеки типов.  
  
 `pTypeLibPlatform`  
 заполняет Флаг [Сискинд](/windows/win32/api/oaidl/ne-oaidl-syskind) , определяющий целевую операционную систему для библиотеки типов. Распространенные значения: SYS_WIN32 и SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 заполняет Основной номер версии библиотеки типов. Например, для версии *x. y* основной номер версии — *x*.  
  
 `pTypeLibMinorVer`  
 заполняет Дополнительный номер версии библиотеки типов. Например, для версии *x. y* дополнительный номер версии — *y*.  
  
## <a name="remarks"></a>Комментарии  

 `GetTypeLibInfo`Функция вызывается [Tlbexp.exe (программа экспорта библиотек типов)](../../tools/tlbexp-exe-type-library-exporter.md). Это средство создает библиотеку типов, описывающую типы в сборке среды CLR.  
  
 Если какой-либо из параметров имеет значение null, функция возвращает объект `HRESULT` `E_POINTER` . В противном случае возвращается значение `S_OK`.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Тлбреф. h  
  
 **Библиотека:** Тлбреф. lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Вспомогательные функции Tlbexp](index.md)
- [Функция Лоадтипелибекс](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

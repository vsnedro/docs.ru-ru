---
title: Метод ResolveTypeLib
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
ms.openlocfilehash: 65bbae614c8872ab5d78b3855b56ceaf2aad50da
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558190"
---
# <a name="resolvetypelib-method"></a>Метод ResolveTypeLib
Разрешает простое имя библиотеки типов, возвращая полный путь.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a>Параметры  
 `bstrSimpleName`  
 окне Значение типа [BSTR](/previous-versions/windows/desktop/automat/bstr) , содержащее простое имя библиотеки типов.  
  
 `tlbid`  
 окне Идентификатор GUID, назначенный библиотеке типов в реестре.  
  
 `lcid`  
 окне ИДЕНТИФИКАТОР локализации библиотеки типов.  
  
 `wMajorVersion`  
 окне Основной номер версии библиотеки типов. Например, для версии *x. y*основной номер версии — *x*.  
  
 `wMinorVersion`  
 окне Дополнительный номер версии библиотеки типов. Например, для версии *x. y*дополнительный номер версии — *y*.  
  
 `syskind`  
 окне Флаг [Сискинд](/windows/win32/api/oaidl/ne-oaidl-syskind) , определяющий операционную среду. Распространенные значения: SYS_WIN32 и SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 заполняет Указатель на [BSTR](/previous-versions/windows/desktop/automat/bstr) , содержащий полный путь к библиотеке типов с именем в `bstrSimpleName` параметре.  
  
## <a name="remarks"></a>Примечания  
 `ResolveTypeLib`Метод вызывается [функцией LoadTypeLibWithResolver](loadtypelibwithresolver-function.md) во время обработки [Tlbexp.exe (средство экспорта библиотеки типов)](../../tools/tlbexp-exe-type-library-exporter.md) .  
  
 Пользовательские реализации этого интерфейса должны возвращать [строку BSTR](/previous-versions/windows/desktop/automat/bstr) , содержащую полный путь к библиотеке типов с именем в `bstrSimpleName` параметре.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Тлбреф. idl, Тлбреф. h  
  
 **Библиотека:** Тлбреф. lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Вспомогательные функции Tlbexp](index.md)
- [лоадтипелибекс](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

---
description: Дополнительные сведения о перечислении Кормесодимпл
title: Перечисление CorMethodImpl
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
ms.openlocfilehash: 157db81a72742f1f2aae7e95249b819b2396ef4b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784396"
---
# <a name="cormethodimpl-enumeration"></a>Перечисление CorMethodImpl

Содержит значения, описывающие возможности реализации метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`miCodeTypeMask`|Флаги, описывающие тип кода.|  
|`miIL`|Указывает, что реализация метода является промежуточным языком Майкрософт (MSIL).|  
|`miNative`|Указывает, что для метода используется стандартная реализация.|  
|`miOPTIL`|Указывает, что реализация метода — OPIL.|  
|`miRuntime`|Указывает, что реализация метода предоставляется средой CLR.|  
|`miManagedMask`|Флаги, указывающие, является ли код управляемым или неуправляемым.|  
|`miUnmanaged`|Указывает, что реализация метода является неуправляемой.|  
|`miManaged`|Указывает, что реализация метода является управляемой.|  
|`miForwardRef`|Указывает, что метод определен. Этот флаг используется в основном в сценариях слияния.|  
|`miPreserveSig`|Указывает, что подпись метода не может быть искажена для преобразования HRESULT.|  
|`miInternalCall`|Зарезервировано для внутреннего использования средой CLR.|  
|`miSynchronized`|Указывает, что метод является однопотоковым через его тело.|  
|`miNoInlining`|Указывает, что метод нельзя выполнять как встроенный.|  
|`miAggressiveInlining`|Указывает, что метод должен быть встроенным, если это возможно.|  
|`miNoOptimization`|Указывает, что метод не должен быть оптимизирован.|  
|`miMaxMethodImplVal`|Максимальное допустимое значение для `CorMethodImpl` .|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](metadata-enumerations.md)

---
title: Функция CloseCLREnumeration
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
ms.openlocfilehash: 575e194cf952f02a3fe4fce9e955e45e1bc3653d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673917"
---
# <a name="closeclrenumeration-function"></a>Функция CloseCLREnumeration

Закрывает все допустимые события продолжения запуска среды CLR, расположенные в массиве дескрипторов, возвращаемых [функцией EnumerateCLRs](enumerateclrs-function.md), и освобождает память для массивов дескрипторов и строковых путей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pHandleArray`  
 окне Указатель на массив дескрипторов событий, возвращаемых [функцией EnumerateCLRs](enumerateclrs-function.md).  
  
 `pStringArray`  
 окне Указатель на массив строковых путей среды CLR, возвращенных [функцией EnumerateCLRs](enumerateclrs-function.md).  
  
 `dwArrayLength`  
 [in] Значение DWORD, содержащее размер (длину) массива `pHandleArray` или `pStringArray` (они одинаковые).  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK  
 Дескрипторы, открытые [функцией EnumerateCLRs](enumerateclrs-function.md) , закрываются, а память, выделенная для дескрипторов и массивов строк, освобождается.  
  
 E_INVALIDARG  
 Длина массива `pHandleArray` не соответствует длине, переданной в `dwArrayLength`.  
  
 E_FAIL (или другие коды возврата E_)  
 Функции не удалось освободить память для массивов `pHandleArray` и `pStringArray`.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** dbgshim. h  
  
 **Библиотека:** dbgshim.dll  
  
 **.NET Framework версии:** 3,5 SP1

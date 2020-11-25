---
title: Функция StrongNameErrorInfo
ms.date: 03/30/2017
api_name:
- StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameErrorInfo
helpviewer_keywords:
- StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type:
- apiref
ms.openlocfilehash: 90abfcd573795ae529714e21b13f90d6e15c7dad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732272"
---
# <a name="strongnameerrorinfo-function"></a>Функция StrongNameErrorInfo

Получает код последней ошибки, вызванной одной из функций строгого имени.  
  
 Эта функция является устаревшей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameErrorInfo ();
```  
  
## <a name="return-value"></a>Возвращаемое значение  

 Последний код ошибки COM, заданный одной из функций строгого имени.  
  
## <a name="remarks"></a>Комментарии  

 Большинство методов со строгим именем возвращают простой `true` или `false` индикатор успешного завершения. Используйте `StrongNameErrorInfo` функцию, чтобы получить значение HRESULT, указывающее последнюю ошибку, созданную функциями строгого имени.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  

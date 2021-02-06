---
description: Дополнительные сведения о функции Стронгнамирроринфо
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
ms.openlocfilehash: a02e5f3d101a34c8ed13cb0f70fd2e95d945cb4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646404"
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
  
## <a name="remarks"></a>Remarks  

 Большинство методов со строгим именем возвращают простой `true` или `false` индикатор успешного завершения. Используйте `StrongNameErrorInfo` функцию, чтобы получить значение HRESULT, указывающее последнюю ошибку, созданную функциями строгого имени.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  

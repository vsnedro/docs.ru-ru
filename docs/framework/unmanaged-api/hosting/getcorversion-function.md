---
description: Дополнительные сведения о функции Жеткорверсион
title: Функция GetCORVersion
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 96899b2193be9307314dbc2afb7cd6d70d229cfe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785332"
---
# <a name="getcorversion-function"></a>Функция GetCORVersion

Возвращает номер версии общеязыковой среды выполнения (CLR), которая выполняется в текущем процессе.  
  
 Эта функция является устаревшей в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>Параметры  

 `pbuffer`  
 Указатель на буфер, в котором среда CLR возвращает строку, указывающую версию среды выполнения, которая в данный момент загружена в процесс. Возвращаемая строка принимает ту же форму, что и строки, переданные в [CorBindToRuntimeEx](corbindtoruntimeex-function.md), например "v 1.0.1216". Если среда выполнения еще не загружена в процесс, функция возвращает соответствующие сведения о каталоге для последней версии среды выполнения, установленной на компьютере.  
  
 `cchBuffer`  
 Число символов `WCHAR` , которые могут храниться в `pbuffer` .  
  
 `dwLength`  
 Указатель на число символов, фактически возвращаемых в `pbuffer` . Если `pbuffer` является пустым указателем, среда выполнения возвращает E_POINTER. Если число символов превышает длину `pbuffer` , среда выполнения возвращает ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

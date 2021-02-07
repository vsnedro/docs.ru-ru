---
description: Дополнительные сведения о функции _CorExeMain2
title: Функция _CorExeMain2
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
ms.openlocfilehash: 4629ea2f6c2ba13351c409bc382077eea926b507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717112"
---
# <a name="_corexemain2-function"></a>Функция _CorExeMain2

Выполняет точку входа в указанном коде, сопоставленном с памятью. Эта функция вызывается загрузчиком операционной системы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pUnmappedPE`  
 окне Указатель на код, сопоставленный с памятью.  
  
 `cUnmappedPE`  
 окне Количество элементов, которые `pUnmappedPE` могут храниться.  
  
 `pImageNameIn`  
 окне Указатель на имя исполняемого образа.  
  
 `pLoadersFileName`  
 окне Имя файла загрузчика.  
  
 `pCmdLine`  
 окне Параметры командной строки, если они есть.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)

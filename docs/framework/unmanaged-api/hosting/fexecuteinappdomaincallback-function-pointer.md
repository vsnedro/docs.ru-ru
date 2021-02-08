---
description: 'Дополнительные сведения: указатель функции Фексекутеинаппдомаинкаллбакк'
title: Указатель функции FExecuteInAppDomainCallback
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
ms.openlocfilehash: 97c7fe14a3eafd6f4626d8729be3b45ad5502f1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785400"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a>Указатель функции FExecuteInAppDomainCallback

Указывает на функцию, которая вызывается средой CLR для выполнения управляемого кода.  
  
 Этот указатель функции является устаревшим в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cookie`  
 окне Указатель на непрозрачную память, выделенную вызывающим объектом, содержащую управляемый код для выполнения.  
  
 Выделение и время существования этой памяти управляются вызывающим объектом (то есть средой CLR). Это не управляемая средой CLR память в куче.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorWks.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

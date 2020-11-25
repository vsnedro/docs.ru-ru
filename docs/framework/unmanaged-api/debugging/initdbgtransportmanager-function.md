---
title: Функция InitDbgTransportManager
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
ms.openlocfilehash: a5b4783eadb8045733b9ebd6d10c4e31f7829498
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716685"
---
# <a name="initdbgtransportmanager-function"></a>Функция InitDbgTransportManager

Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK  
 Успешно.  
  
 E_OUTOFMEMORY  
 Функции не удалось выделить память для диспетчера транспорта.  
  
 E_FAIL (или другие коды возврата E_)  
 Прочие сбои.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Кореклрремотедебуггингинтерфацес. h  
  
 **Библиотека:** mscordbi_macx86.dll  
  
 **.NET Framework версии:** 3,5 SP1

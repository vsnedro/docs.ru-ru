---
title: Метод ICorDebugThread::EnumerateChains
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
ms.openlocfilehash: 711fccd65379bc3e5e178869e7220dd84fd07fbe
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379705"
---
# <a name="icordebugthreadenumeratechains-method"></a>Метод ICorDebugThread::EnumerateChains
Получает указатель интерфейса на перечислитель Икордебугчаиненум, который содержит все цепочки стека в этом объекте ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppChains`  
 заполняет Указатель на адрес `ICorDebugChainEnum` объекта, который допускает перечисление всех цепочек стека в этом потоке, начиная с активной (то есть самой последней) цепочки.  
  
## <a name="remarks"></a>Remarks  
 Цепочка стека представляет физический стек вызовов для потока. В следующих случаях создается граница цепочки стеков:  
  
- Переход с управляемого на неуправляемый или неуправляемый на управляемый.  
  
- Переключение контекста.  
  
- Перехват пользовательского потока отладчиком.  
  
 В простом случае для потока, в котором выполняется исключительно управляемый код в одном контексте, между потоками и цепочками стеков будет существовать соответствие "один к одному".  
  
 Отладчик может захотеть перераспределить физические стеки вызовов всех потоков на логические стеки вызовов. Это может привести к сортировке всех цепочек потоков по связям "Вызывающий/вызываемый" и их перегруппировку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

---
title: Функция PreBindAssemblyEx
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
ms.openlocfilehash: a729249f7b0681941a0b1a478dbe2c0d9d6cd01c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723965"
---
# <a name="prebindassemblyex-function"></a>Функция PreBindAssemblyEx

Возвращает отображаемое имя после применения политики для сборки.  
  
 Эта функция поддерживает .NET Frameworkную инфраструктуру и не предназначена для непосредственного использования в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppCtx`  
 окне Определяет контекст приложения.  
  
 `pName`  
 окне Определяет имя сборки.  
  
 `pAsmParent`  
 окне Определяет родительскую сборку. Этот параметр не учитывается.  
  
 `pwzRuntimeVersion`  
 окне Определяет версию среды выполнения.  
  
 `ppNamePostPolicy`  
 заполняет Содержит отображаемое имя после применения политики.  
  
 `pvReserved`  
 окне Зарезервировано для будущего расширения. `pvReserved` должен быть пустой ссылкой.  
  
## <a name="remarks"></a>Комментарии  

 `ppNamePostPolicy`Выходной параметр задается только в том случае, если функция возвращает значение HRESULT FUSION_E_REF_DEF_MISMATCH. В противном случае — значение null.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Глобальные статические функции Fusion](fusion-global-static-functions.md)

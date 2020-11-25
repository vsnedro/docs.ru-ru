---
title: Функция IsFrameworkAssembly
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
ms.openlocfilehash: 828c7660d6c006e700302d119ce4caf7d76e5d84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728567"
---
# <a name="isframeworkassembly-function"></a>Функция IsFrameworkAssembly

Возвращает значение, указывающее, является ли указанная сборка управляемой.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzAssemblyReference`  
 окне Имя проверяемой сборки.  
  
 `pbIsFrameworkAssembly`  
 заполняет Логическое значение, указывающее, является ли сборка управляемой.  
  
 `pwzFrameworkAssemblyIdentity`  
 окне Неканоническая строка, содержащая уникальный идентификатор сборки.  
  
 `pccSize`  
 [входной] Размер `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Комментарии  

 `pwzAssemblyReference`Параметр является указателем на символьную строку, содержащую имя сборки.  
  
 Если эта сборка является частью .NET Framework, `pbIsFrameworkAssembly` параметр будет содержать логическое значение `true` .  
  
 Если именованная сборка не является частью .NET Framework или если `pwzAssemblyReference` параметр не имеет имени сборки, `pbIsFrameworkAssembly` то будет содержать логическое значение `false` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
## <a name="see-also"></a>См. также раздел

- [Глобальные статические функции Fusion](fusion-global-static-functions.md)

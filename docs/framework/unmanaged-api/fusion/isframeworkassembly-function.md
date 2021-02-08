---
description: Дополнительные сведения о функции Исфрамеворкассембли
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
ms.openlocfilehash: 8f264df7b1ae5c494298b11ebd94cc93aed5543a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800023"
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
  
## <a name="remarks"></a>Remarks  

 `pwzAssemblyReference`Параметр является указателем на символьную строку, содержащую имя сборки.  
  
 Если эта сборка является частью платформа .NET Framework, `pbIsFrameworkAssembly` параметр будет содержать логическое значение `true` .  
  
 Если именованная сборка не является частью платформа .NET Framework или если `pwzAssemblyReference` параметр не имеет имени сборки, `pbIsFrameworkAssembly` то будет содержать логическое значение `false` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции Fusion](fusion-global-static-functions.md)

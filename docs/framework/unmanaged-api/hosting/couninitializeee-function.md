---
description: Дополнительные сведения о функции CoUninitializeEE
title: Функция CoUninitializeEE
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
ms.openlocfilehash: e356135ea027bd52520eff9084ad2f7f09e1fe0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746169"
---
# <a name="couninitializeee-function"></a>Функция CoUninitializeEE

`CoUninitializeEE` является устаревшим и не предоставляет никаких функциональных возможностей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Remarks  

 Подсистема выполнения среды CLR не может быть выгружена из процесса. Чтобы завершить работу подсистемы выполнения, [корекситпроцесс](corexitprocess-function.md)вызов.  
  
## <a name="see-also"></a>См. также

- [Функция CoInitializeEE](coinitializeee-function.md)
- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)

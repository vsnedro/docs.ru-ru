---
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
ms.openlocfilehash: e6616392eaa23f8ba40247c5aabd12e4d530cea1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687851"
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
  
## <a name="see-also"></a>См. также раздел

- [Функция CoInitializeEE](coinitializeee-function.md)
- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)

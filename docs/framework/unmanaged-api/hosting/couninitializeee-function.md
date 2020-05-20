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
ms.openlocfilehash: fa6297e926d53c02bb0d1af7b59b45b8ee152399
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616467"
---
# <a name="couninitializeee-function"></a>Функция CoUninitializeEE
`CoUninitializeEE`является устаревшим и не предоставляет никаких функциональных возможностей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Remarks  
 Подсистема выполнения среды CLR не может быть выгружена из процесса. Чтобы завершить работу подсистемы выполнения, [корекситпроцесс](corexitprocess-function.md)вызов.  
  
## <a name="see-also"></a>См. также статью

- [Функция CoInitializeEE](coinitializeee-function.md)
- [Глобальные статические функции метаданных](../metadata/metadata-global-static-functions.md)

---
title: Интерфейс ISymUnmanagedENCUpdate
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: 1986d5f91a3dcfa31a43f729ee1f50129e083f5f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501746"
---
# <a name="isymunmanagedencupdate-interface"></a>Интерфейс ISymUnmanagedENCUpdate
Предоставляет функции для функции "изменить и продолжить".  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetLocalVariableCount](isymunmanagedencupdate-getlocalvariablecount-method.md)|Возвращает число локальных переменных.|  
|[Метод GetLocalVariables](isymunmanagedencupdate-getlocalvariables-method.md)|Возвращает локальные переменные.|  
|[Метод InitializeForEnc](isymunmanagedencupdate-initializeforenc-method.md)|Позволяет вычислять границы методов перед первым вызовом метода [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) .|  
|[Метод UpdateMethodLines](isymunmanagedencupdate-updatemethodlines-method.md)|Позволяет обновлять сведения о строке для метода, который не был перекомпилирован, но строки были перемещены независимо друг от друга. Допускается использование разности для каждой инструкции.|  
|[Метод UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md)|Позволяет компилятору опускать функции, которые не были изменены из потока базы данных программы (PDB) при условии, что сведения о строке соответствуют требованиям. Правильная информация о строке может быть определена со старыми сведениями о строке PDB и одной разностью для всех строк в функции.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)

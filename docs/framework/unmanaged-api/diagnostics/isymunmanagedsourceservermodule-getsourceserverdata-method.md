---
description: 'Дополнительные сведения о методе: ISymUnmanagedSourceServerModule:: Жетсаурцесервердата'
title: Метод ISymUnmanagedSourceServerModule::GetSourceServerData
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
ms.openlocfilehash: cdba764534000273170ccd693a3fbc7b5df9c3c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763167"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a>Метод ISymUnmanagedSourceServerModule::GetSourceServerData

Возвращает данные исходного сервера для модуля. Вызывающий объект должен освободить ресурсы с помощью `CoTaskMemFree` .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a>Параметры  

 `pDataByteCount`  
 заполняет Указатель на объект `ULONG32` , который получает размер (в байтах) данных сервера-источника.  
  
 `ppData`  
 заполняет Указатель на возвращаемое `pDataByteCount` значение.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedSourceServerModule](isymunmanagedsourceservermodule-interface.md)

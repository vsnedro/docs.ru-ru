---
description: 'Дополнительные сведения о методе: ICLRDataTarget:: Request'
title: Метод ICLRDataTarget::Request
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
ms.openlocfilehash: 75c400a51a2fdaf0044d85b5f483d783fae4628b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712172"
---
# <a name="iclrdatatargetrequest-method"></a>Метод ICLRDataTarget::Request

Вызывается службами доступа к данным среды CLR для запроса операции, как определено в реализации.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `reqCode`  
 окне Определяется пользователем.  
  
 `inBufferSize`  
 окне Размер входного буфера, используемого для входящего запроса.  
  
 `inBuffer`  
 окне Буфер, содержащий запрос.  
  
 `outBufferSize`  
 окне Размер выходного буфера, используемого для ответа.  
  
 `outBuffer`  
 заполняет Буфер, содержащий ответ.  
  
## <a name="remarks"></a>Remarks  

 `Request`Метод упрощает добавление неуказанных пользовательских операций. Это значит, что этот метод обеспечивает расширяемость без необходимости пересмотра определения интерфейса.  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)

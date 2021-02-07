---
description: 'Дополнительные сведения о методе: IAssemblyCacheItem:: Креатестреам'
title: Метод IAssemblyCacheItem::CreateStream
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
ms.openlocfilehash: 89592d8fe1a7f43a7da20dd10883881c3339f088
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760879"
---
# <a name="iassemblycacheitemcreatestream-method"></a>Метод IAssemblyCacheItem::CreateStream

Создает поток с указанными именем и форматом.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a>Параметры

`dwFlags`\
окне Флаги, определенные в Fusion. idl.

`pszStreamName`\
окне Имя создаваемого потока.

`dwFormat`\
окне Формат файла для потоковой передачи.

`dwFormatFlags`\
окне Флаги формата, определенные в Fusion. idl.

`ppIStream`\
заполняет Указатель на адрес возвращенного экземпляра [IStream](/windows/desktop/api/objidl/nn-objidl-istream) .

`puliMaxSize`\
[входные, необязательные] Максимальный размер потока, на который ссылается `ppIStream` .

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** Fusion. h

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyCacheItem](iassemblycacheitem-interface.md)

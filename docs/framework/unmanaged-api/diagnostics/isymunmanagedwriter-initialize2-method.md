---
title: Метод ISymUnmanagedWriter::Initialize2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
ms.openlocfilehash: 93a96a5da3342f4beff611de1d448dc199dd39dd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687134"
---
# <a name="isymunmanagedwriterinitialize2-method"></a>Метод ISymUnmanagedWriter::Initialize2

Задает интерфейс передатчика метаданных, с которым будет связан этот модуль записи, и задает имя выходного файла, в который будут записываться отладочные символы. Этот метод также позволяет задать конечное расположение файла базы данных программы (PDB).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a>Параметры  

 `emitter`  
 окне Указатель на интерфейс передатчика метаданных.  
  
 `tempfilename`  
 окне Указатель на объект `WCHAR` , содержащий имя файла, в который записываются отладочные символы. Если имя файла задано для модуля записи, который не использует имена файлов, этот параметр пропускается.  
  
 `pIStream`  
 окне Если указан, средство записи символов создает символы в заданном, а не в <xref:System.Runtime.InteropServices.ComTypes.IStream> файле, указанном в `filename` параметре. Параметр `pIStream` не обязателен.  
  
 `fFullBuild`  
 [входные] `true` значение, если это полная перестроение; `false` если это инкрементная компиляция.  
  
 `finalfilename`  
 окне Указатель на объект `WCHAR` , который является строкой пути к окончательному расположению PDB-файла.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Метод Initialize](isymunmanagedwriter-initialize-method.md)

---
title: Метод ISymUnmanagedWriter::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: 1553e616f60b4f05c06b6457d47454dfb4bc2eb7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614777"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="10db7-102">Метод ISymUnmanagedWriter::Initialize</span><span class="sxs-lookup"><span data-stu-id="10db7-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="10db7-103">Задает интерфейс передатчика метаданных, с которым будет связан этот модуль записи, и задает имя выходного файла, в который будут записываться отладочные символы.</span><span class="sxs-lookup"><span data-stu-id="10db7-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="10db7-104">Этот метод может быть вызван только один раз и должен вызываться перед любым другим методом записи.</span><span class="sxs-lookup"><span data-stu-id="10db7-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="10db7-105">Некоторым модулям записи может потребоваться имя файла.</span><span class="sxs-lookup"><span data-stu-id="10db7-105">Some writers may require a file name.</span></span> <span data-ttu-id="10db7-106">Однако всегда можно передать имя файла этому методу без какого-либо негативного воздействия на модули записи, которые не используют имя файла.</span><span class="sxs-lookup"><span data-stu-id="10db7-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10db7-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10db7-107">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10db7-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="10db7-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="10db7-109">окне Указатель на интерфейс передатчика метаданных.</span><span class="sxs-lookup"><span data-stu-id="10db7-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="10db7-110">окне Имя файла, в который записываются отладочные символы.</span><span class="sxs-lookup"><span data-stu-id="10db7-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="10db7-111">Если имя файла задано для модуля записи, который не использует имена файлов, этот параметр пропускается.</span><span class="sxs-lookup"><span data-stu-id="10db7-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="10db7-112">окне Если этот параметр указан, модуль записи символов выдает символы в заданный объект, а не в <xref:System.Runtime.InteropServices.ComTypes.IStream> файл, указанный в `filename` аргументе.</span><span class="sxs-lookup"><span data-stu-id="10db7-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="10db7-113">Параметр `pIStream` не обязателен.</span><span class="sxs-lookup"><span data-stu-id="10db7-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="10db7-114">[входные] `true` значение, если это полная перестроение; `false`если это инкрементная компиляция.</span><span class="sxs-lookup"><span data-stu-id="10db7-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10db7-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10db7-115">Return Value</span></span>  
 <span data-ttu-id="10db7-116">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="10db7-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10db7-117">Требования</span><span class="sxs-lookup"><span data-stu-id="10db7-117">Requirements</span></span>  
 <span data-ttu-id="10db7-118">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="10db7-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10db7-119">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="10db7-119">See also</span></span>

- [<span data-ttu-id="10db7-120">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="10db7-120">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="10db7-121">Метод Initialize2</span><span class="sxs-lookup"><span data-stu-id="10db7-121">Initialize2 Method</span></span>](isymunmanagedwriter-initialize2-method.md)

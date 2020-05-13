---
title: Метод ICorDebugSymbolProvider::GetMethodProps
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
ms.openlocfilehash: c9e73c4de7389405d9e4b643036709ff2dbb82e6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379564"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="fed54-102">Метод ICorDebugSymbolProvider::GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="fed54-102">ICorDebugSymbolProvider::GetMethodProps Method</span></span>
<span data-ttu-id="fed54-103">Возвращает сведения о свойствах метода, такие как токен метаданных метода и сведения о его универсальных параметрах, для указанного относительного виртуального адреса (RVA) в этом методе.</span><span class="sxs-lookup"><span data-stu-id="fed54-103">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed54-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fed54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fed54-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fed54-105">Parameters</span></span>  
 `codeRVA`  
 <span data-ttu-id="fed54-106">[in] Относительный виртуальный адрес в методе, сведения о котором требуется извлечь.</span><span class="sxs-lookup"><span data-stu-id="fed54-106">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="fed54-107">[out] Указатель на токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="fed54-107">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="fed54-108">[out] Указатель на количество универсальных параметров, связанных с данным методом.</span><span class="sxs-lookup"><span data-stu-id="fed54-108">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="fed54-109">[in] Размер массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="fed54-109">[in] The size of the `signature` array.</span></span> <span data-ttu-id="fed54-110">См. раздел «Примечания».</span><span class="sxs-lookup"><span data-stu-id="fed54-110">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="fed54-111">[out] Указатель на размер возвращаемого массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="fed54-111">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="fed54-112">[out] Буфер, в котором хранятся сигнатуры TypeSpec для всех универсальных параметров.</span><span class="sxs-lookup"><span data-stu-id="fed54-112">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fed54-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="fed54-113">Remarks</span></span>  
 <span data-ttu-id="fed54-114">Чтобы получить требуемый размер `signature` массива метода, присвойте `cbSignature` аргументу значение 0 и `signature` **значение NULL**.</span><span class="sxs-lookup"><span data-stu-id="fed54-114">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="fed54-115">После возврата метода параметр `pcbSignature` будет содержать число байт, требуемое для массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="fed54-115">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fed54-116">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="fed54-116">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed54-117">Требования</span><span class="sxs-lookup"><span data-stu-id="fed54-117">Requirements</span></span>  
 <span data-ttu-id="fed54-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fed54-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fed54-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fed54-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fed54-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fed54-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fed54-121">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fed54-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed54-122">См. также</span><span class="sxs-lookup"><span data-stu-id="fed54-122">See also</span></span>

- [<span data-ttu-id="fed54-123">Метод GetTypeProps</span><span class="sxs-lookup"><span data-stu-id="fed54-123">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)
- [<span data-ttu-id="fed54-124">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="fed54-124">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="fed54-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fed54-125">Debugging Interfaces</span></span>](debugging-interfaces.md)

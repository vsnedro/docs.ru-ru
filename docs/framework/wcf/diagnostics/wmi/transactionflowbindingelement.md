---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 577502d1cd3d81784cb9b1eb3b249376b8ffa6b8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234899"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="5bb8d-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="5bb8d-102">TransactionFlowBindingElement</span></span>

<span data-ttu-id="5bb8d-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="5bb8d-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bb8d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bb8d-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5bb8d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5bb8d-105">Methods</span></span>  

 <span data-ttu-id="5bb8d-106">Класс TransactionFlowBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5bb8d-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="5bb8d-107">Properties</span></span>  

 <span data-ttu-id="5bb8d-108">Класс TransactionFlowBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="5bb8d-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="5bb8d-109">IssuedTokens</span></span>  

 <span data-ttu-id="5bb8d-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="5bb8d-110">Data type: string</span></span>  
  
 <span data-ttu-id="5bb8d-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="5bb8d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bb8d-112">Задает требование для заголовка выданных маркеров безопасности (IssuedTokens из WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="5bb8d-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="5bb8d-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="5bb8d-113">TransactionProtocol</span></span>  

 <span data-ttu-id="5bb8d-114">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="5bb8d-114">Data type: string</span></span>  
  
 <span data-ttu-id="5bb8d-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="5bb8d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bb8d-116">Протокол транзакций, используемый службой для передачи транзакций.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="5bb8d-117">Transactions</span><span class="sxs-lookup"><span data-stu-id="5bb8d-117">Transactions</span></span>  

 <span data-ttu-id="5bb8d-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="5bb8d-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="5bb8d-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="5bb8d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5bb8d-120">Указывает, поддерживается ли входящая транзакция.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bb8d-121">Требования</span><span class="sxs-lookup"><span data-stu-id="5bb8d-121">Requirements</span></span>  
  
|<span data-ttu-id="5bb8d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="5bb8d-122">MOF</span></span>|<span data-ttu-id="5bb8d-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5bb8d-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="5bb8d-124">Namespace</span></span>|<span data-ttu-id="5bb8d-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="5bb8d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bb8d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5bb8d-126">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>

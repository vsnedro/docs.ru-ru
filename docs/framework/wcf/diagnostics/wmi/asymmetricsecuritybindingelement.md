---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 00485ff80a0064e700d99203de3aa581d3761f30
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255732"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="46f20-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="46f20-102">AsymmetricSecurityBindingElement</span></span>

<span data-ttu-id="46f20-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="46f20-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46f20-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46f20-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="46f20-105">Методы</span><span class="sxs-lookup"><span data-stu-id="46f20-105">Methods</span></span>  

 <span data-ttu-id="46f20-106">Класс AsymmetricSecurityBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="46f20-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="46f20-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="46f20-107">Properties</span></span>  

 <span data-ttu-id="46f20-108">Класс AsymmetricSecurityBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="46f20-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="46f20-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="46f20-109">MessageProtectionOrder</span></span>  

 <span data-ttu-id="46f20-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="46f20-110">Data type: string</span></span>  
  
 <span data-ttu-id="46f20-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="46f20-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46f20-112">Порядок шифрования и подписывания сообщений для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="46f20-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="46f20-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="46f20-113">RequireSignatureConfirmation</span></span>  

 <span data-ttu-id="46f20-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="46f20-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="46f20-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="46f20-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46f20-116">Указывает, требует ли привязка подтверждения подписи.</span><span class="sxs-lookup"><span data-stu-id="46f20-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46f20-117">Требования</span><span class="sxs-lookup"><span data-stu-id="46f20-117">Requirements</span></span>  
  
|<span data-ttu-id="46f20-118">MOF</span><span class="sxs-lookup"><span data-stu-id="46f20-118">MOF</span></span>|<span data-ttu-id="46f20-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="46f20-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="46f20-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="46f20-120">Namespace</span></span>|<span data-ttu-id="46f20-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="46f20-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46f20-122">См. также</span><span class="sxs-lookup"><span data-stu-id="46f20-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

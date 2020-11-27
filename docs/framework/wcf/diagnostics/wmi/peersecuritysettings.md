---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 2de417e4a4f5c6197551c1408da6907e2fa7c635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269006"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="ed539-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ed539-102">PeerSecuritySettings</span></span>

<span data-ttu-id="ed539-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ed539-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed539-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed539-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ed539-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ed539-105">Methods</span></span>  

 <span data-ttu-id="ed539-106">Класс PeerSecuritySettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="ed539-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ed539-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="ed539-107">Properties</span></span>  

 <span data-ttu-id="ed539-108">Класс PeerSecuritySettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="ed539-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="ed539-109">Режим</span><span class="sxs-lookup"><span data-stu-id="ed539-109">Mode</span></span>  

 <span data-ttu-id="ed539-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="ed539-110">Data type: string</span></span>  
  
 <span data-ttu-id="ed539-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="ed539-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed539-112">Определяет, использует ли настроенная с помощью привязки конечная точка безопасность на уровне сообщений и на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="ed539-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="ed539-113">Транспорт</span><span class="sxs-lookup"><span data-stu-id="ed539-113">Transport</span></span>  

 <span data-ttu-id="ed539-114">Тип данных: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ed539-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="ed539-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="ed539-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed539-116">Параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="ed539-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed539-117">Требования</span><span class="sxs-lookup"><span data-stu-id="ed539-117">Requirements</span></span>  
  
|<span data-ttu-id="ed539-118">MOF</span><span class="sxs-lookup"><span data-stu-id="ed539-118">MOF</span></span>|<span data-ttu-id="ed539-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ed539-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ed539-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="ed539-120">Namespace</span></span>|<span data-ttu-id="ed539-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="ed539-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed539-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ed539-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>

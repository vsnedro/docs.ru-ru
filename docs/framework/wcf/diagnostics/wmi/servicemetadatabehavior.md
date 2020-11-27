---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 921a880dad0d77558a70dff8a09f75c25a3cbb8a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262285"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="83e4a-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="83e4a-102">ServiceMetadataBehavior</span></span>

<span data-ttu-id="83e4a-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="83e4a-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e4a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83e4a-104">Syntax</span></span>  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="83e4a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="83e4a-105">Methods</span></span>  

 <span data-ttu-id="83e4a-106">Класс ServiceMetadataBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="83e4a-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="83e4a-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="83e4a-107">Properties</span></span>  

 <span data-ttu-id="83e4a-108">Класс ServiceMetadataBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="83e4a-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="83e4a-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="83e4a-109">ExternalMetadataLocation</span></span>  

 <span data-ttu-id="83e4a-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="83e4a-110">Data type: string</span></span>  
  
 <span data-ttu-id="83e4a-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="83e4a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83e4a-112">Задает расположение, в которое служба перенаправляет запросы метаданных.</span><span class="sxs-lookup"><span data-stu-id="83e4a-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="83e4a-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="83e4a-113">HttpGetEnabled</span></span>  

 <span data-ttu-id="83e4a-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="83e4a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="83e4a-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="83e4a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83e4a-116">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="83e4a-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="83e4a-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="83e4a-117">HttpGetUrl</span></span>  

 <span data-ttu-id="83e4a-118">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="83e4a-118">Data type: string</span></span>  
  
 <span data-ttu-id="83e4a-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="83e4a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83e4a-120">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="83e4a-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="83e4a-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="83e4a-121">HttpsGetEnabled</span></span>  

 <span data-ttu-id="83e4a-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="83e4a-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="83e4a-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="83e4a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83e4a-124">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="83e4a-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="83e4a-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="83e4a-125">HttpsGetUrl</span></span>  

 <span data-ttu-id="83e4a-126">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="83e4a-126">Data type: string</span></span>  
  
 <span data-ttu-id="83e4a-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="83e4a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="83e4a-128">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="83e4a-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83e4a-129">Требования</span><span class="sxs-lookup"><span data-stu-id="83e4a-129">Requirements</span></span>  
  
|<span data-ttu-id="83e4a-130">MOF</span><span class="sxs-lookup"><span data-stu-id="83e4a-130">MOF</span></span>|<span data-ttu-id="83e4a-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="83e4a-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="83e4a-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="83e4a-132">Namespace</span></span>|<span data-ttu-id="83e4a-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="83e4a-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83e4a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="83e4a-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>

---
title: Интерфейс IAppDomainSetup
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
ms.openlocfilehash: d504101747995557ba526c88de451ebab7b3c556
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698563"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="4e853-102">Интерфейс IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="4e853-102">IAppDomainSetup Interface</span></span>

<span data-ttu-id="4e853-103">Предоставляет свойства, позволяющие узлу настроить <xref:System.AppDomain?displayProperty=nameWithType> тип перед вызовом метода [ICorRuntimeHost:: CreateDomainEx](icorruntimehost-createdomainex-method.md) для его создания.</span><span class="sxs-lookup"><span data-stu-id="4e853-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4e853-104">Свойства</span><span class="sxs-lookup"><span data-stu-id="4e853-104">Properties</span></span>  
  
|<span data-ttu-id="4e853-105">Свойство</span><span class="sxs-lookup"><span data-stu-id="4e853-105">Property</span></span>|<span data-ttu-id="4e853-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4e853-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="4e853-107">Возвращает или задает имя каталога, содержащего приложение.</span><span class="sxs-lookup"><span data-stu-id="4e853-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="4e853-108">Возвращает или задает имя приложения.</span><span class="sxs-lookup"><span data-stu-id="4e853-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="4e853-109">Возвращает или задает имя области, относящейся к приложению, в котором файлы копируются при теневом копировании.</span><span class="sxs-lookup"><span data-stu-id="4e853-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="4e853-110">Возвращает или задает имя файла конфигурации для приложения.</span><span class="sxs-lookup"><span data-stu-id="4e853-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="4e853-111">Возвращает или задает имя каталога, в котором хранятся и обращаются динамически создаваемые файлы.</span><span class="sxs-lookup"><span data-stu-id="4e853-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="4e853-112">Возвращает или задает путь к файлу лицензии, связанному с этим доменом.</span><span class="sxs-lookup"><span data-stu-id="4e853-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="4e853-113">Возвращает или задает список каталогов в сочетании с <xref:System.AppDomainSetup.ApplicationBase%2A> каталогом для проверки закрытых сборок.</span><span class="sxs-lookup"><span data-stu-id="4e853-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="4e853-114">Возвращает или задает строковое значение, которое включает или исключает <xref:System.AppDomainSetup.ApplicationBase%2A> из пути поиска для приложения.</span><span class="sxs-lookup"><span data-stu-id="4e853-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="4e853-115">Возвращает или задает имена каталогов, содержащих сборки для теневого копирования.</span><span class="sxs-lookup"><span data-stu-id="4e853-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="4e853-116">Возвращает или задает строку, которая указывает, включено ли теневое копирование.</span><span class="sxs-lookup"><span data-stu-id="4e853-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="4e853-117">Допустимые значения: "true" или "false".</span><span class="sxs-lookup"><span data-stu-id="4e853-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e853-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4e853-118">Remarks</span></span>  

 <span data-ttu-id="4e853-119">`IAppDomainSetup`Интерфейс соответствует управляемому <xref:System.IAppDomainSetup> интерфейсу, который <xref:System.AppDomainSetup> реализуется типом.</span><span class="sxs-lookup"><span data-stu-id="4e853-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="4e853-120"><xref:System.IAppDomainSetup?displayProperty=nameWithType>Подробные описания его свойств см. в разделе.</span><span class="sxs-lookup"><span data-stu-id="4e853-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="4e853-121">`IAppDomainSetup` представляет сведения о привязке сборки, которые можно добавить к <xref:System.AppDomain> экземпляру перед его созданием.</span><span class="sxs-lookup"><span data-stu-id="4e853-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="4e853-122">Например, узел может установить <xref:System.AppDomainSetup.ApplicationBase%2A> свойство, чтобы установить корневой каталог, который проверяет среда CLR для управляемых сборок.</span><span class="sxs-lookup"><span data-stu-id="4e853-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e853-123">Требования</span><span class="sxs-lookup"><span data-stu-id="4e853-123">Requirements</span></span>  

 <span data-ttu-id="4e853-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e853-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e853-125">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4e853-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e853-126">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e853-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e853-127">**.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e853-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e853-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4e853-128">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [<span data-ttu-id="4e853-129">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4e853-129">Hosting Interfaces</span></span>](hosting-interfaces.md)

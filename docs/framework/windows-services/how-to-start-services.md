---
title: Практическое руководство. Запуск служб
description: Ознакомьтесь с несколькими способами запуска служб. Установленную службу необходимо запустить. Процедура запуска вызывает метод OnStart в классе службы.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
ms.openlocfilehash: 4a2f9b291e60b12b1465fbb6bbbd1604572359a7
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925726"
---
# <a name="how-to-start-services"></a><span data-ttu-id="a202a-105">Практическое руководство. Запуск служб</span><span class="sxs-lookup"><span data-stu-id="a202a-105">How to: Start Services</span></span>

<span data-ttu-id="a202a-106">Установленную службу необходимо запустить.</span><span class="sxs-lookup"><span data-stu-id="a202a-106">After a service is installed, it must be started.</span></span> <span data-ttu-id="a202a-107">Процедура запуска вызывает метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> в классе службы.</span><span class="sxs-lookup"><span data-stu-id="a202a-107">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="a202a-108">Как правило, метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> определяет полезные действия, которые будет выполнять служба.</span><span class="sxs-lookup"><span data-stu-id="a202a-108">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="a202a-109">Запущенная служба остается активной, пока не будет приостановлена или остановлена вручную.</span><span class="sxs-lookup"><span data-stu-id="a202a-109">After a service starts, it remains active until it is manually paused or stopped.</span></span>

<span data-ttu-id="a202a-110">Службы можно настроить на запуск автоматически или вручную.</span><span class="sxs-lookup"><span data-stu-id="a202a-110">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="a202a-111">Служба, которая запускается автоматически, будет запущена при первом включении или перезагрузке компьютера, на котором она установлена.</span><span class="sxs-lookup"><span data-stu-id="a202a-111">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="a202a-112">Службу, которая запускается вручную, должен запустить пользователь.</span><span class="sxs-lookup"><span data-stu-id="a202a-112">A user must start a service that starts manually.</span></span>

> [!NOTE]
> <span data-ttu-id="a202a-113">По умолчанию службы, созданные с помощью Visual Studio, настроены на запуск вручную.</span><span class="sxs-lookup"><span data-stu-id="a202a-113">By default, services created with Visual Studio are set to start manually.</span></span>

<span data-ttu-id="a202a-114">Есть несколько способов запуска службы вручную: из **диспетчера служб** или **обозревателя сервера** либо из кода, используя компонент, который называется <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="a202a-114">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>

<span data-ttu-id="a202a-115">Вы можете задать свойство <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> в классе <xref:System.ServiceProcess.ServiceInstaller>, чтобы определить способ запуска службы — вручную или автоматически.</span><span class="sxs-lookup"><span data-stu-id="a202a-115">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>

### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="a202a-116">Настройка способа запуска службы</span><span class="sxs-lookup"><span data-stu-id="a202a-116">To specify how a service should start</span></span>

1. <span data-ttu-id="a202a-117">Создав службу, добавьте для нее необходимые установщики.</span><span class="sxs-lookup"><span data-stu-id="a202a-117">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="a202a-118">Дополнительные сведения см. в разделе [Практическое руководство. Добавление установщиков в приложение-службу](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="a202a-118">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>

2. <span data-ttu-id="a202a-119">В конструкторе щелкните установщик процессов службы, с которой вы работаете.</span><span class="sxs-lookup"><span data-stu-id="a202a-119">In the designer, click the service installer for the service you are working with.</span></span>

3. <span data-ttu-id="a202a-120">В **окне свойств** задайте свойству <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="a202a-120">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>

    |<span data-ttu-id="a202a-121">Чтобы установить службу</span><span class="sxs-lookup"><span data-stu-id="a202a-121">To have your service install</span></span>|<span data-ttu-id="a202a-122">Задайте это значение</span><span class="sxs-lookup"><span data-stu-id="a202a-122">Set this value</span></span>|
    |----------------------------------|--------------------|
    |<span data-ttu-id="a202a-123">При перезапуске компьютера</span><span class="sxs-lookup"><span data-stu-id="a202a-123">When the computer is restarted</span></span>|<span data-ttu-id="a202a-124">**Автоматический**</span><span class="sxs-lookup"><span data-stu-id="a202a-124">**Automatic**</span></span>|
    |<span data-ttu-id="a202a-125">При запуске службы с помощью явного действия пользователя</span><span class="sxs-lookup"><span data-stu-id="a202a-125">When an explicit user action starts the service</span></span>|<span data-ttu-id="a202a-126">**Manual** (Вручную)</span><span class="sxs-lookup"><span data-stu-id="a202a-126">**Manual**</span></span>|

    > [!TIP]
    > <span data-ttu-id="a202a-127">Чтобы полностью запретить запуск службы, можно задать свойству <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> значение **Disabled** (Отключено).</span><span class="sxs-lookup"><span data-stu-id="a202a-127">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="a202a-128">Это можно сделать, если вы собираетесь перезагружать сервер несколько раз и хотите сэкономить время, запретив запуск служб, которые обычно запускаются одновременно.</span><span class="sxs-lookup"><span data-stu-id="a202a-128">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a202a-129">Эти и другие свойства можно изменить после установки службы.</span><span class="sxs-lookup"><span data-stu-id="a202a-129">These and other properties can be changed after your service is installed.</span></span>

    <span data-ttu-id="a202a-130">Есть несколько способов запуска службы, для процесса <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> которой настроено значение **Manual** (Вручную): из **диспетчера служб** или **обозревателя серверов** либо из кода.</span><span class="sxs-lookup"><span data-stu-id="a202a-130">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="a202a-131">Важно отметить, что в действительности не все эти методы приводят к запуску службы в контексте **диспетчера служб**. При использовании **обозревателя сервера** и программных способов применяется контроллер.</span><span class="sxs-lookup"><span data-stu-id="a202a-131">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>

### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="a202a-132">Запуск службы вручную из обозревателя сервера</span><span class="sxs-lookup"><span data-stu-id="a202a-132">To manually start a service from Server Explorer</span></span>

1. <span data-ttu-id="a202a-133">В **обозревателе сервера** добавьте нужный сервер, если его нет в списке.</span><span class="sxs-lookup"><span data-stu-id="a202a-133">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="a202a-134">Дополнительные сведения см. в разделах "Практическое руководство. Подключение и инициализация обозревателя серверов или обозревателя баз данных".</span><span class="sxs-lookup"><span data-stu-id="a202a-134">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>

2. <span data-ttu-id="a202a-135">Разверните узел **Службы** и выберите службу, которую нужно запустить.</span><span class="sxs-lookup"><span data-stu-id="a202a-135">Expand the **Services** node, and then locate the service you want to start.</span></span>

3. <span data-ttu-id="a202a-136">Щелкните службу правой кнопкой мыши и выберите команду **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="a202a-136">Right-click the name of the service, and click **Start**.</span></span>

### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="a202a-137">Запуск службы вручную из диспетчера служб</span><span class="sxs-lookup"><span data-stu-id="a202a-137">To manually start a service from Services Control Manager</span></span>

1. <span data-ttu-id="a202a-138">Откройте **диспетчер служб**, сделав следующее:</span><span class="sxs-lookup"><span data-stu-id="a202a-138">Open the **Services Control Manager** by doing one of the following:</span></span>

    - <span data-ttu-id="a202a-139">В Windows XP и 2000 Professional щелкните правой кнопкой мыши значок **Мой компьютер** на рабочем столе и выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="a202a-139">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="a202a-140">В открывшемся диалоговом окне разверните узел **Службы и приложения**.</span><span class="sxs-lookup"><span data-stu-id="a202a-140">In the dialog box that appears, expand the **Services and Applications** node.</span></span>

      <span data-ttu-id="a202a-141">\- или -</span><span class="sxs-lookup"><span data-stu-id="a202a-141">\- or -</span></span>

    - <span data-ttu-id="a202a-142">В Windows Server 2003 и Windows 2000 Server нажмите кнопку **Пуск**, выберите **Программы**, **Администрирование** и **Службы**.</span><span class="sxs-lookup"><span data-stu-id="a202a-142">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="a202a-143">В Windows NT версии 4.0 можно открыть это диалоговое окно на **панели управления**.</span><span class="sxs-lookup"><span data-stu-id="a202a-143">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>

    <span data-ttu-id="a202a-144">Теперь ваша служба должна отобразиться в списке **Службы**.</span><span class="sxs-lookup"><span data-stu-id="a202a-144">You should now see your service listed in the **Services** section of the window.</span></span>

2. <span data-ttu-id="a202a-145">Выберите службу в списке, щелкните ее правой кнопкой мыши и нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="a202a-145">Select your service in the list, right-click it, and then click **Start**.</span></span>

### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="a202a-146">Запуск службы вручную из кода</span><span class="sxs-lookup"><span data-stu-id="a202a-146">To manually start a service from code</span></span>

1. <span data-ttu-id="a202a-147">Создайте экземпляр класса <xref:System.ServiceProcess.ServiceController> и настройте его для взаимодействия со службой, которой нужно управлять.</span><span class="sxs-lookup"><span data-stu-id="a202a-147">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>

2. <span data-ttu-id="a202a-148">Чтобы запустить службу, вызовите метод <xref:System.ServiceProcess.ServiceController.Start%2A>.</span><span class="sxs-lookup"><span data-stu-id="a202a-148">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>

## <a name="see-also"></a><span data-ttu-id="a202a-149">См. также</span><span class="sxs-lookup"><span data-stu-id="a202a-149">See also</span></span>

- [<span data-ttu-id="a202a-150">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="a202a-150">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="a202a-151">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="a202a-151">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="a202a-152">Практическое руководство. Добавление установщиков в приложение-службу</span><span class="sxs-lookup"><span data-stu-id="a202a-152">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)

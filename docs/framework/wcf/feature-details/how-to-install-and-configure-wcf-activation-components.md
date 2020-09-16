---
title: Практическое руководство. Установка и настройка компонентов активации WCF
description: Узнайте, как настроить службу активации процессов Windows (WAS) в Windows Vista для размещения служб WCF, не взаимодействующих по протоколу HTTP.
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 085a69421f0aa7b763bd2222820ced4b4a7e1c81
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557870"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="c061b-103">Практическое руководство. Установка и настройка компонентов активации WCF</span><span class="sxs-lookup"><span data-stu-id="c061b-103">How to: Install and Configure WCF Activation Components</span></span>

<span data-ttu-id="c061b-104">В этом разделе описываются шаги, необходимые для настройки службы активации Windows (также известной как WAS) в Windows Vista для размещения служб Windows Communication Foundation (WCF), не передающих сетевые протоколы HTTP.</span><span class="sxs-lookup"><span data-stu-id="c061b-104">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on Windows Vista to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="c061b-105">Настройка предполагает следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="c061b-105">The following sections outline the steps for this configuration:</span></span>

- <span data-ttu-id="c061b-106">Установите (или подтвердите установку) компоненты активации WCF.</span><span class="sxs-lookup"><span data-stu-id="c061b-106">Install (or confirm the installation of) the WCF activation components.</span></span>

- <span data-ttu-id="c061b-107">Настройте WAS на поддержку отличных от HTTP протоколов.</span><span class="sxs-lookup"><span data-stu-id="c061b-107">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="c061b-108">Следующая процедура настраивает Windows Vista для активации TCP.</span><span class="sxs-lookup"><span data-stu-id="c061b-108">The following procedure configures Windows Vista for TCP activation.</span></span>

<span data-ttu-id="c061b-109">После установки и настройки WAS см. раздел [как разместить службу WCF в WAS](how-to-host-a-wcf-service-in-was.md) для процедур создания службы WCF, предоставляющей конечную точку, которая не является КОНЕЧНОЙ точкой HTTP.</span><span class="sxs-lookup"><span data-stu-id="c061b-109">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>

## <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="c061b-110">Установка компонентов активации WCF, работающих по отличному от HTTP протоколу</span><span class="sxs-lookup"><span data-stu-id="c061b-110">To install the WCF non-HTTP activation components</span></span>

1. <span data-ttu-id="c061b-111">В меню **Пуск** выберите пункт **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="c061b-111">Click the **Start** button, and then click **Control Panel**.</span></span>

2. <span data-ttu-id="c061b-112">Последовательно выберите **Программы**, **Программы и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="c061b-112">Click **Programs**, and then click **Programs and Features**.</span></span>

3. <span data-ttu-id="c061b-113">В меню **задачи** выберите команду **Включение или отключение компонентов Windows**.</span><span class="sxs-lookup"><span data-stu-id="c061b-113">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>

4. <span data-ttu-id="c061b-114">Найдите узел WinFX, выберите и разверните его.</span><span class="sxs-lookup"><span data-stu-id="c061b-114">Find the WinFX node, select and then expand it.</span></span>

5. <span data-ttu-id="c061b-115">Выберите пункт **WCF-компоненты активации, отличные от HTTP** и сохраните параметр.</span><span class="sxs-lookup"><span data-stu-id="c061b-115">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>

## <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="c061b-116">Настройка WAS на поддержку протокола TCP</span><span class="sxs-lookup"><span data-stu-id="c061b-116">To configure the WAS to support TCP activation</span></span>

1. <span data-ttu-id="c061b-117">Для поддержки активации по net.tcp веб-узел по умолчанию необходимо сначала привязать к порту net.tcp.</span><span class="sxs-lookup"><span data-stu-id="c061b-117">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="c061b-118">Это можно сделать с помощью Appcmd.exe, который устанавливается вместе с набором средств управления IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="c061b-118">You can do this by using Appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="c061b-119">В окне командной строки с правами администратора выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="c061b-119">In an administrator-level Command Prompt window, run the following command.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="c061b-120">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="c061b-120">This command is a single line of text.</span></span> <span data-ttu-id="c061b-121">Она добавляет привязку узла к протоколу net.tcp в веб-узел по умолчанию, ожидающему передачи данных по протоколу TCP на порту 808 с любым именем узла.</span><span class="sxs-lookup"><span data-stu-id="c061b-121">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>

2. <span data-ttu-id="c061b-122">Несмотря на то что все приложения в узле имеют общую привязку к протоколу net.tcp, включать поддержку net.tcp можно для каждого приложения отдельно.</span><span class="sxs-lookup"><span data-stu-id="c061b-122">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="c061b-123">Для включения протокола net.tcp для данного приложения необходимо выполнить следующую команду из командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="c061b-123">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp
    ```

    > [!NOTE]
    > <span data-ttu-id="c061b-124">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="c061b-124">This command is a single line of text.</span></span> <span data-ttu-id="c061b-125">Эта команда обеспечивает доступ к \<*WCF Application*> приложению или с помощью `http://localhost/<WCF Application>` и `net.tcp://localhost/<WCF Application>` .</span><span class="sxs-lookup"><span data-stu-id="c061b-125">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>

     <span data-ttu-id="c061b-126">Удалите привязку сайта к протоколу net.tcp, добавленную ранее для данного образца.</span><span class="sxs-lookup"><span data-stu-id="c061b-126">Remove the net.tcp site binding you added for this sample.</span></span>

     <span data-ttu-id="c061b-127">Для удобства два нижеописанных действия выполняются в пакетом файле RemoveNetTcpSiteBinding.cmd, расположенном в каталоге с образцами.</span><span class="sxs-lookup"><span data-stu-id="c061b-127">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="c061b-128">Удалите протокол net.tcp из списка разрешенных протоколов, выполнив следующую команду в окне командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="c061b-128">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="c061b-129">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="c061b-129">This command is a single line of text.</span></span>

    2. <span data-ttu-id="c061b-130">Удалите привязку узла к протоколу net.tcp, выполнив следующую команду в окне командной строки с повышенными привилегиями:</span><span class="sxs-lookup"><span data-stu-id="c061b-130">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > <span data-ttu-id="c061b-131">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="c061b-131">This command is a single line of text.</span></span>

## <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="c061b-132">Удаление протокола net.tcp из списка разрешенных протоколов</span><span class="sxs-lookup"><span data-stu-id="c061b-132">To remove net.tcp from the list of enabled protocols</span></span>

1. <span data-ttu-id="c061b-133">Для того чтобы удалить протокол net.tcp из списка разрешенных протоколов, необходимо выполнить следующую команду в окне командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="c061b-133">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
    ```

    > [!NOTE]
    > <span data-ttu-id="c061b-134">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="c061b-134">This command is a single line of text.</span></span>

## <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="c061b-135">Удаление привязки узла к протоколу net.tcp</span><span class="sxs-lookup"><span data-stu-id="c061b-135">To remove the net.tcp site binding</span></span>

1. <span data-ttu-id="c061b-136">Для того чтобы удалить привязку узла к протоколу net.tcp, необходимо выполнить следующую команду в окне командной строки с правами администратора:</span><span class="sxs-lookup"><span data-stu-id="c061b-136">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
    -bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="c061b-137">Эта команда представляет собой одну строку текста.</span><span class="sxs-lookup"><span data-stu-id="c061b-137">This command is a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="c061b-138">См. также</span><span class="sxs-lookup"><span data-stu-id="c061b-138">See also</span></span>

- [<span data-ttu-id="c061b-139">Активация TCP</span><span class="sxs-lookup"><span data-stu-id="c061b-139">TCP Activation</span></span>](../samples/tcp-activation.md)
- [<span data-ttu-id="c061b-140">Активация MSMQ</span><span class="sxs-lookup"><span data-stu-id="c061b-140">MSMQ Activation</span></span>](../samples/msmq-activation.md)
- [<span data-ttu-id="c061b-141">Активация NamedPipe</span><span class="sxs-lookup"><span data-stu-id="c061b-141">NamedPipe Activation</span></span>](../samples/namedpipe-activation.md)
- <span data-ttu-id="c061b-142">[Функции размещения Windows Server App Fabric](/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c061b-142">[Windows Server App Fabric Hosting Features](/previous-versions/appfabric/ee677189(v=azure.10))</span></span>

---
title: Инструкции брандмауэра
description: Узнайте, как включить порты или программы в примерах брандмауэра для WCF. Используйте одну из этих процедур в зависимости от требований и среды безопасности.
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: de55d067960b8f2096c129f6feaf037219e06a96
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246146"
---
# <a name="firewall-instructions"></a><span data-ttu-id="d1b9a-104">Инструкции по брандмауэру</span><span class="sxs-lookup"><span data-stu-id="d1b9a-104">Firewall instructions</span></span>

<span data-ttu-id="d1b9a-105">Необходимо включить несколько портов или программ в брандмауэре, чтобы образцы Windows Communication Foundation (WCF) могли работать.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-105">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="d1b9a-106">Многие из образцов сообщаются с использованием портов в диапазоне 8000-8003 и порта 9000.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-106">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="d1b9a-107">По умолчанию брандмауэр включен и запрещает доступ к этим портам.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-107">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="d1b9a-108">Чтобы включить брандмауэр для примеров, завершите одну из следующих операций, в зависимости от требований и среды безопасности.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-108">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>

- <span data-ttu-id="d1b9a-109">Вариант 1. В интерактивном режиме включите образцы во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-109">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="d1b9a-110">Не вносите изменения в конфигурацию брандмауэра заранее и перейдите к построению и выполнению образцов.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-110">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="d1b9a-111">При запуске образца появляется диалоговое окно **оповещение системы безопасности Windows** .</span><span class="sxs-lookup"><span data-stu-id="d1b9a-111">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="d1b9a-112">Затем программу данного образца можно добавить в интерактивном режиме в незаблокированный список.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-112">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="d1b9a-113">После этого необходимо перезагрузить образец.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-113">With this procedure, you may have to then restart the sample.</span></span>

- <span data-ttu-id="d1b9a-114">Вариант 2. Включите программы образцов заранее.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-114">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="d1b9a-115">Запустите приложение **панели управления Брандмауэр Windows** и включите примеры программ, которые планируется запустить.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-115">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="d1b9a-116">Сначала необходимо построить программы, чтобы исполняемые файлы существовали.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-116">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="d1b9a-117">Более подробные инструкции см. в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-117">You can find more detailed instructions in the following procedure.</span></span>

- <span data-ttu-id="d1b9a-118">Вариант 3. Включите диапазон портов заранее.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-118">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="d1b9a-119">Запустите приложение **панели управления Брандмауэр Windows** и включите порты 80, 443, 8000-8003 и 9000, которые используются в примерах.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-119">Start the **Windows Firewall Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="d1b9a-120">Более подробные инструкции см. в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-120">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="d1b9a-121">Этот вариант менее безопасен, чем другие, поскольку он позволяет использовать эти порты любой программе, а не только образцам.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-121">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>

<span data-ttu-id="d1b9a-122">Если есть сомнения, какой вариант выбрать, используйте первый.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-122">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="d1b9a-123">Если брандмауэр выполняется с другого поставщика, может потребоваться внести похожие изменения.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-123">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1b9a-124">Изменение конфигурации брандмауэра влияет на безопасность.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-124">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="d1b9a-125">Рекомендуется записывать вносимые изменения и удалять их по завершении работы с образцами.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-125">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>

## <a name="enable-samples-programs-in-advance"></a><span data-ttu-id="d1b9a-126">Включить образцы программ заранее</span><span class="sxs-lookup"><span data-stu-id="d1b9a-126">Enable samples programs in advance</span></span>

1. <span data-ttu-id="d1b9a-127">Выполните сборку примера.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-127">Build the sample.</span></span>

2. <span data-ttu-id="d1b9a-128">Выберите **запустить**  >  **Запуск**и введите `firewall.cpl` .</span><span class="sxs-lookup"><span data-stu-id="d1b9a-128">Choose **Start** > **Run**, and enter `firewall.cpl`.</span></span> <span data-ttu-id="d1b9a-129">Откроется окно приложения **панели управления Брандмауэр Windows** .</span><span class="sxs-lookup"><span data-stu-id="d1b9a-129">This opens the **Windows Firewall Control Panel** applet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d1b9a-130">Для запуска образцов, которым необходима возможность связи через брандмауэр Windows, требуется разрешение на изменение параметров брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-130">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="d1b9a-131">Если некоторые параметры брандмауэра недоступны и компьютер подключен к домену, возможно, системный администратор управляет этими параметрами через групповую политику.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-131">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>

3. <span data-ttu-id="d1b9a-132">Выполните одно из следующих действий, чтобы разрешить выполнение программы через брандмауэр Windows.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-132">Complete one of the following operating-specific steps to allow a program through the Windows Firewall:</span></span>

    - <span data-ttu-id="d1b9a-133">В Windows 7 или Windows Server 2008 R2 щелкните **Разрешить программу или компонент через брандмауэр Windows**.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-133">On Windows 7 or Windows Server 2008 R2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="d1b9a-134">Щелкните **изменить параметры**  >  **Разрешить другую программу**.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-134">Click **Change Settings** > **Allow Another Program**.</span></span>

    - <span data-ttu-id="d1b9a-135">В Windows Vista или Windows Server 2008 щелкните **Разрешить программу через брандмауэр Windows**.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-135">On Windows Vista or Windows Server 2008, click **Allow a program through Windows Firewall**.</span></span>

4. <span data-ttu-id="d1b9a-136">На вкладке **исключения** нажмите кнопку **Добавить программу**.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-136">On the **Exceptions** tab, click **Add Program**.</span></span>

5. <span data-ttu-id="d1b9a-137">Нажмите кнопку **Обзор** и выберите исполняемый файл примера, который планируется запустить.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-137">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>

6. <span data-ttu-id="d1b9a-138">Повторите шаги 4 и 5, пока не будут добавлены исполняемые файлы всех примеров, которые планируется запустить.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-138">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>

7. <span data-ttu-id="d1b9a-139">Нажмите кнопку **ОК** , чтобы закрыть приложение брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-139">Click **OK** to close the firewall applet.</span></span>

## <a name="enable-a-port-range-in-advance"></a><span data-ttu-id="d1b9a-140">Включить диапазон портов заранее</span><span class="sxs-lookup"><span data-stu-id="d1b9a-140">Enable a port range in advance</span></span>

1. <span data-ttu-id="d1b9a-141">Выберите **запустить**  >  **Запуск**и введите `firewall.cpl` .</span><span class="sxs-lookup"><span data-stu-id="d1b9a-141">Choose **Start** > **Run**, and enter `firewall.cpl`.</span></span> <span data-ttu-id="d1b9a-142">Откроется окно приложения **панели управления Брандмауэр Windows** .</span><span class="sxs-lookup"><span data-stu-id="d1b9a-142">This opens the **Windows Firewall Control Panel** applet.</span></span>

2. <span data-ttu-id="d1b9a-143">В Windows 7 или Windows Server 2008 R2 выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-143">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>

    1. <span data-ttu-id="d1b9a-144">Щелкните **Дополнительные параметры** в левом столбце окна Брандмауэр Windows.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-144">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>

    2. <span data-ttu-id="d1b9a-145">В левом столбце щелкните **правила для входящих подключений** .</span><span class="sxs-lookup"><span data-stu-id="d1b9a-145">Click **Inbound Rules** in the left column.</span></span>

    3. <span data-ttu-id="d1b9a-146">Щелкните **новые правила** в правом столбце.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-146">Click **New Rules** in the right column.</span></span>

    4. <span data-ttu-id="d1b9a-147">Выберите **порт** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-147">Select **Port** and click **next**.</span></span>

    5. <span data-ttu-id="d1b9a-148">Выберите **TCP** и введите `8000, 8001, 8002, 8003, 9000, 80, 443` в поле **определенные локальные порты** .</span><span class="sxs-lookup"><span data-stu-id="d1b9a-148">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>

    6. <span data-ttu-id="d1b9a-149">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-149">Click **Next**.</span></span>

    7. <span data-ttu-id="d1b9a-150">Установите флажок **Разрешить подключение**и нажмите кнопку **Далее** .</span><span class="sxs-lookup"><span data-stu-id="d1b9a-150">Select **Allow the connection**, and click **Next** .</span></span>

    8. <span data-ttu-id="d1b9a-151">Выберите **домен** и **частный**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-151">Select **Domain** and **Private**, and click **Next**.</span></span>

    9. <span data-ttu-id="d1b9a-152">Присвойте этому правилу имя `WCF-WF 4.0 Samples` и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-152">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>

    10. <span data-ttu-id="d1b9a-153">Щелкните **правила для исходящих подключений** и повторите шаги c до h.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-153">Click **Outbound Rules** and repeat steps c to h.</span></span>

3. <span data-ttu-id="d1b9a-154">В Windows Vista или Windows Server 2008 выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-154">On Windows Vista or Windows Server 2008, follow these steps.</span></span>

    1. <span data-ttu-id="d1b9a-155">Выберите элемент **Разрешение запуска программы через брандмауэр Windows**.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-155">Click **Allow a program through Windows Firewall**.</span></span>

    2. <span data-ttu-id="d1b9a-156">На вкладке **исключения** нажмите кнопку **Добавить порт**.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-156">On the **Exceptions** tab, click **Add Port**.</span></span>

    3. <span data-ttu-id="d1b9a-157">Введите имя, введите 8000 в качестве номера порта и выберите параметр **TCP** .</span><span class="sxs-lookup"><span data-stu-id="d1b9a-157">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>

    4. <span data-ttu-id="d1b9a-158">Нажмите кнопку **изменить область** , выберите параметр только **Моя сеть** (подсеть) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-158">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>

    5. <span data-ttu-id="d1b9a-159">Повторите шаги от B до D для портов 8001, 8002, 8003, 9000, 80 и 443.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-159">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>

4. <span data-ttu-id="d1b9a-160">Нажмите кнопку **ОК** , чтобы закрыть приложение брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-160">Click **OK** to close the firewall applet.</span></span>

> [!NOTE]
> <span data-ttu-id="d1b9a-161">Удалите все исключения брандмауэра по завершении работы с примерами.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-161">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="d1b9a-162">Для этого откройте **Панель управления брандмауэра Windows** и удалите все программы или записи портов, добавленные в предыдущих процедурах.</span><span class="sxs-lookup"><span data-stu-id="d1b9a-162">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>

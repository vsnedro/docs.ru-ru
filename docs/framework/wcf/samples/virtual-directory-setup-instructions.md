---
title: Инструкции по настройке виртуальных каталогов
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: dba6547888935ccf36ec0924fd3c95e8fbda5688
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243655"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="ef64e-102">Инструкции по настройке виртуальных каталогов</span><span class="sxs-lookup"><span data-stu-id="ef64e-102">Virtual Directory Setup Instructions</span></span>

<span data-ttu-id="ef64e-103">Примеры Windows Communication Foundation (WCF) предназначены для совместного использования общего виртуального каталога с именем servicemodelsamples, сопоставленного с папкой%SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="ef64e-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef64e-104">Переменная %SystemDrive% обычно имеет значение C: или D: в зависимости от того, на каком диске установлены службы IIS.</span><span class="sxs-lookup"><span data-stu-id="ef64e-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="ef64e-105">Вы можете запустить Setupvroot.bat и Cleanupvroot.bat файлы из [процедуры однократной настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md) , чтобы создать виртуальный каталог.</span><span class="sxs-lookup"><span data-stu-id="ef64e-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="ef64e-106">Если требуется создать виртуальный каталог вручную, воспользуйтесь следующими процедурами.</span><span class="sxs-lookup"><span data-stu-id="ef64e-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="ef64e-107">Процедуры</span><span class="sxs-lookup"><span data-stu-id="ef64e-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="ef64e-108">Создание виртуального каталога в IIS 7,0 или 7,5</span><span class="sxs-lookup"><span data-stu-id="ef64e-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="ef64e-109">В меню **Пуск** выберите пункт **выполнить**, а затем введите **inetmgr** , чтобы открыть оснастку MMC службы IIS (IIS).</span><span class="sxs-lookup"><span data-stu-id="ef64e-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="ef64e-110">В левой области разверните узел с именем компьютера, а затем разверните узел **сайты** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="ef64e-111">Щелкните правой кнопкой мыши **веб-сайт по умолчанию** и выберите пункт **Добавить приложение** , чтобы открыть **окно Добавление приложения**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="ef64e-112">В окне введите псевдоним создаваемого `servicemodelsamples` виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="ef64e-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="ef64e-113">Создайте следующий каталог: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="ef64e-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="ef64e-114">Укажите путь к физическому каталогу %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="ef64e-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="ef64e-115">Большинство образцов WCF при построении копируют исполняемые файлы службы именно в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="ef64e-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="ef64e-116">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-116">Click **OK**.</span></span> <span data-ttu-id="ef64e-117">Веб-приложение для образцов WCF создано.</span><span class="sxs-lookup"><span data-stu-id="ef64e-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ef64e-118">Эту задачу необходимо выполнить только один раз, так как все примеры WCF используют одно и то же веб-приложение servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="ef64e-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ef64e-119">В этой документации термины `virtual directory` и `Web application` являются синонимами.</span><span class="sxs-lookup"><span data-stu-id="ef64e-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="ef64e-120">Кроме создания виртуального каталога, необходимо также задать его свойства, чтобы разрешить выполнение служб WCF.</span><span class="sxs-lookup"><span data-stu-id="ef64e-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="ef64e-121">Дополнительные сведения см. далее.</span><span class="sxs-lookup"><span data-stu-id="ef64e-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="ef64e-122">Создание виртуального каталога в IIS 5.1 и 6.0</span><span class="sxs-lookup"><span data-stu-id="ef64e-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="ef64e-123">Откройте окно командной строки и введите, `start inetmgr` чтобы открыть оснастку MMC службы IIS (IIS).</span><span class="sxs-lookup"><span data-stu-id="ef64e-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="ef64e-124">В левой области разверните узел с именем компьютера, а затем разверните узел **веб-сайты** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="ef64e-125">Щелкните правой кнопкой мыши **веб-сайт по умолчанию** и выберите **создать, виртуальный каталог,** чтобы открыть мастер создания виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="ef64e-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="ef64e-126">В мастере введите в `servicemodelsamples` качестве псевдонима создаваемого виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="ef64e-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="ef64e-127">Укажите путь к каталогу %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="ef64e-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="ef64e-128">Большинство образцов WCF при построении копируют исполняемые файлы службы именно в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="ef64e-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="ef64e-129">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-129">Click **Next**.</span></span>  
  
7. <span data-ttu-id="ef64e-130">По умолчанию устанавливаются следующие флажки:</span><span class="sxs-lookup"><span data-stu-id="ef64e-130">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="ef64e-131">**Чтение**</span><span class="sxs-lookup"><span data-stu-id="ef64e-131">**Read**</span></span>  
  
    - <span data-ttu-id="ef64e-132">**Запуск скриптов (например, ASP)**</span><span class="sxs-lookup"><span data-stu-id="ef64e-132">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="ef64e-133">Нажмите кнопку **Далее**, а затем кнопку **Готово** , чтобы завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="ef64e-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ef64e-134">Эту задачу необходимо выполнить только один раз, так как все примеры WCF используют один и тот же виртуальный каталог servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="ef64e-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="ef64e-135">Установка дополнительных свойств виртуального каталога в IIS 7,0 или 7,5</span><span class="sxs-lookup"><span data-stu-id="ef64e-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="ef64e-136">Щелкните узел servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="ef64e-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="ef64e-137">В нижней части окна будет указано два представления.</span><span class="sxs-lookup"><span data-stu-id="ef64e-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="ef64e-138">Выберите **представление функций** , если оно еще не выбрано.</span><span class="sxs-lookup"><span data-stu-id="ef64e-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="ef64e-139">Дважды щелкните запись для **обзора каталогов**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="ef64e-140">На панели действия выберите параметр **включить** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="ef64e-141">Это позволит обращаться к каталогу каталога с помощью веб-обозревателя Internet Explorer, что упростит отладку службы.</span><span class="sxs-lookup"><span data-stu-id="ef64e-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="ef64e-142">Наконец необходимо задать свойства безопасности папки servicemodelsamples, чтобы другие пользователи могли получать доступ к ней.</span><span class="sxs-lookup"><span data-stu-id="ef64e-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="ef64e-143">Дополнительные сведения см. далее.</span><span class="sxs-lookup"><span data-stu-id="ef64e-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="ef64e-144">Задание дополнительных свойств виртуального каталога в IIS 5.1 и 6.0</span><span class="sxs-lookup"><span data-stu-id="ef64e-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="ef64e-145">Щелкните правой кнопкой мыши узел servicemodelsamples и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="ef64e-146">По умолчанию устанавливаются следующие флажки:</span><span class="sxs-lookup"><span data-stu-id="ef64e-146">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="ef64e-147">**Чтение**</span><span class="sxs-lookup"><span data-stu-id="ef64e-147">**Read**</span></span>  
  
    - <span data-ttu-id="ef64e-148">**Посещения журнала**</span><span class="sxs-lookup"><span data-stu-id="ef64e-148">**Log visits**</span></span>  
  
    - <span data-ttu-id="ef64e-149">**Индексировать этот ресурс**</span><span class="sxs-lookup"><span data-stu-id="ef64e-149">**Index this resource**</span></span>  
  
3. <span data-ttu-id="ef64e-150">Установите флажок **Просмотр каталогов** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="ef64e-151">Это позволит обращаться к каталогу каталога с помощью веб-обозревателя Internet Explorer, что упростит отладку службы.</span><span class="sxs-lookup"><span data-stu-id="ef64e-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="ef64e-152">Установка свойств безопасности папки в IIS 7,0 или 7,5</span><span class="sxs-lookup"><span data-stu-id="ef64e-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="ef64e-153">Перейдите к каталогу %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="ef64e-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="ef64e-154">Щелкните правой кнопкой мыши папку servicemodelsamples и выберите команду **поделиться** или **поделиться с**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="ef64e-155">Щелкните стрелку вниз слева от кнопки **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="ef64e-156">Выберите запись **поиска** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-156">Select the **Find** entry.</span></span> <span data-ttu-id="ef64e-157">Откроется окно **Выбор пользователей или групп** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-157">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="ef64e-158">Щелкните **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-158">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="ef64e-159">Щелкните **Расположения**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-159">Click **Locations**.</span></span> <span data-ttu-id="ef64e-160">Откроется окно " **расположения** ".</span><span class="sxs-lookup"><span data-stu-id="ef64e-160">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="ef64e-161">Выберите запись, соответствующую используемому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="ef64e-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="ef64e-162">Важно выбрать локальный компьютер, а не запись, соответствующую всем перечисленным доменам и сетям.</span><span class="sxs-lookup"><span data-stu-id="ef64e-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="ef64e-163">Выбрав компьютер, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-163">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="ef64e-164">Щелкните **Find Now**(Найти).</span><span class="sxs-lookup"><span data-stu-id="ef64e-164">Click **Find Now**.</span></span> <span data-ttu-id="ef64e-165">В результатах поиска появятся объекты, связанные с локальным компьютером.</span><span class="sxs-lookup"><span data-stu-id="ef64e-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="ef64e-166">Найдите запись **IIS_IUSRS** в столбце **имя (относительное различающееся имя)** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="ef64e-167">Выберите эту запись и нажмите кнопку **ОК** , чтобы закрыть окно Результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="ef64e-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="ef64e-168">Нажмите кнопку **ОК** , чтобы закрыть окно **Выбор пользователей или групп** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="ef64e-169">Нажмите кнопку **общий доступ** , чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="ef64e-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="ef64e-170">После внесения изменений для включения общего доступа нажмите кнопку **Готово** , чтобы закрыть окно **общего доступа к файлам** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="ef64e-171">Задание свойств безопасности папки в IIS 5.1 и 6.0</span><span class="sxs-lookup"><span data-stu-id="ef64e-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="ef64e-172">Перейдите к каталогу %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="ef64e-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="ef64e-173">Щелкните правой кнопкой мыши папку **servicemodelsamples** и выберите пункт **общий доступ и безопасность.**</span><span class="sxs-lookup"><span data-stu-id="ef64e-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="ef64e-174">Перейдите на вкладку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-174">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="ef64e-175">Если вы используете IIS 6,0, в поле **группы или пользователи** проверьте, указана ли **учетная запись гостя в Интернете** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="ef64e-176">Если базы данных в списке нет:</span><span class="sxs-lookup"><span data-stu-id="ef64e-176">If it is not listed:</span></span>  
  
    1. <span data-ttu-id="ef64e-177">Нажмите кнопку **Пуск**, затем щелкните **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="ef64e-178">Если значок **учетные записи пользователей** не отображается, щелкните **Переключиться в представление категорий**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3. <span data-ttu-id="ef64e-179">Щелкните значок **учетные записи пользователей** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-179">Click the **User Accounts** icon.</span></span>  
  
    4. <span data-ttu-id="ef64e-180">В разделе "или выберите значок панели управления" щелкните **учетные записи пользователей**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5. <span data-ttu-id="ef64e-181">В диалоговом окне **учетные записи пользователей** перейдите на вкладку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6. <span data-ttu-id="ef64e-182">Щелкните **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-182">Click **Advanced**.</span></span>  
  
    7. <span data-ttu-id="ef64e-183">В диалоговом окне **Локальные пользователи и группы** щелкните, чтобы развернуть папку **Пользователи** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8. <span data-ttu-id="ef64e-184">В области справа дважды щелкните **Гостевая учетная запись Интернета**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="ef64e-185">В диалоговом окне **Свойства** скопируйте имя, используемое в качестве гостевой учетной записи Интернета.</span><span class="sxs-lookup"><span data-stu-id="ef64e-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="ef64e-186">По умолчанию имя состоит из префикса «USR_» и имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="ef64e-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="ef64e-187">Закройте диалоговое окно **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="ef64e-188">Закройте диалоговое окно **Локальные пользователи и группы** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="ef64e-189">Закройте диалоговое окно **учетные записи пользователей** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="ef64e-190">Закройте диалоговое окно другие **учетные записи пользователей** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="ef64e-191">В диалоговом окне **Свойства servicemodelsamples** на вкладке **Безопасность** нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="ef64e-192">Введите имя компьютера, а затем обратную косую черту, а затем вставьте имя учетной записи пользователя Интернета, например Мимачиненаме \\ % интернетгуестаккаунтнаме%.</span><span class="sxs-lookup"><span data-stu-id="ef64e-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="ef64e-193">Щелкните **Проверить имена** , чтобы проверить добавление.</span><span class="sxs-lookup"><span data-stu-id="ef64e-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="ef64e-194">Если оно допустимо, то будет выделено подчеркиванием и прописными буквами.</span><span class="sxs-lookup"><span data-stu-id="ef64e-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="ef64e-195">Для IIS 6,0 также убедитесь, что СЕТЕВая служба указана в поле **группы или пользователи** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="ef64e-196">Если учетная запись NETWORK SERVICE отсутствует, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ef64e-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1. <span data-ttu-id="ef64e-197">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-197">Click **Add**.</span></span>  
  
    2. <span data-ttu-id="ef64e-198">В диалоговом окне **Выбор пользователей или групп** введите имя компьютера, а затем обратную косую черту.</span><span class="sxs-lookup"><span data-stu-id="ef64e-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3. <span data-ttu-id="ef64e-199">Введите **Служба** после обратной косой черты (без пробела).</span><span class="sxs-lookup"><span data-stu-id="ef64e-199">Type **service** after the backslash (no space).</span></span>  
  
    4. <span data-ttu-id="ef64e-200">Нажмите кнопку **Проверить имена**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-200">Click **Check names**.</span></span>  
  
    5. <span data-ttu-id="ef64e-201">Если найдено несколько имен, выберите **Сетевая служба** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6. <span data-ttu-id="ef64e-202">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Выбор пользователей или групп** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="ef64e-203">Если вы используете Windows XP с пакетом обновления 2 (SP2) с IIS 5,1, убедитесь, что в поле **имена групп или пользователей** указаны и учетная запись гостя в Интернете, и имя ASPNET.</span><span class="sxs-lookup"><span data-stu-id="ef64e-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="ef64e-204">Обратите внимание, что пользователь ASPNET может быть членом встроенной группы безопасности **Пользователи** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="ef64e-205">Если да, то если группа **Пользователи** указана в диалоговом окне, вам не нужно добавлять ее в качестве отдельного элемента в список разрешенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="ef64e-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="ef64e-206">Чтобы проверить, является ли ASPNET членом группы безопасности " **Пользователи** ", сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ef64e-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1. <span data-ttu-id="ef64e-207">В меню **Пуск** выберите пункт **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="ef64e-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="ef64e-208">Щелкните значок **учетные записи пользователей** .</span><span class="sxs-lookup"><span data-stu-id="ef64e-208">Click the **User Accounts** icon.</span></span>  
  
    3. <span data-ttu-id="ef64e-209">В столбце **Группа** убедитесь, что для **ASPNET** задано значение "Пользователи".</span><span class="sxs-lookup"><span data-stu-id="ef64e-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef64e-210">См. также</span><span class="sxs-lookup"><span data-stu-id="ef64e-210">See also</span></span>

- [<span data-ttu-id="ef64e-211">Инструкции по размещению в службах IIS</span><span class="sxs-lookup"><span data-stu-id="ef64e-211">Internet Information Service Hosting Instructions</span></span>](internet-information-service-hosting-instructions.md)

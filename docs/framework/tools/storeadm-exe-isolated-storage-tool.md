---
title: Storeadm.exe (средство изолированного хранилища)
description: Ознакомьтесь с Storeadm.exe, средством изолированного хранилища. С его помощью можно получить список или удалить все существующие хранилища для текущего пользователя.
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
ms.openlocfilehash: 153fc2b4b5a955fd5ed768d1492f053595363e6e
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517013"
---
# <a name="storeadmexe-isolated-storage-tool"></a><span data-ttu-id="186e3-104">Storeadm.exe (средство изолированного хранилища)</span><span class="sxs-lookup"><span data-stu-id="186e3-104">Storeadm.exe (Isolated Storage Tool)</span></span>
<span data-ttu-id="186e3-105">Программа изолированного хранилища выводит список или удаляет все существующие хранилища для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="186e3-105">The Isolated Storage tool lists or removes all existing stores for the current user.</span></span>  
  
 <span data-ttu-id="186e3-106">Эта программа автоматически устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="186e3-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="186e3-107">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика для Visual Studio (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="186e3-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="186e3-108">Дополнительные сведения см. в разделе [Командные строки](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="186e3-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="186e3-109">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="186e3-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="186e3-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="186e3-110">Syntax</span></span>  
  
```console  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
## <a name="parameters"></a><span data-ttu-id="186e3-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="186e3-111">Parameters</span></span>  
  
|<span data-ttu-id="186e3-112">Параметр</span><span class="sxs-lookup"><span data-stu-id="186e3-112">Option</span></span>|<span data-ttu-id="186e3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="186e3-113">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="186e3-114">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="186e3-114">**/h**[**elp**]</span></span>|<span data-ttu-id="186e3-115">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="186e3-115">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="186e3-116">**/list**</span><span class="sxs-lookup"><span data-stu-id="186e3-116">**/list**</span></span>|<span data-ttu-id="186e3-117">Отображает все существующие хранилища для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="186e3-117">Displays all existing stores for the current user.</span></span> <span data-ttu-id="186e3-118">В их число включаются хранилища для всех приложений или сборок, выполненных данным пользователем.</span><span class="sxs-lookup"><span data-stu-id="186e3-118">This includes the stores for all applications or assemblies executed by this user.</span></span>|  
|<span data-ttu-id="186e3-119">**/machine**</span><span class="sxs-lookup"><span data-stu-id="186e3-119">**/machine**</span></span>|<span data-ttu-id="186e3-120">Выбирает хранилище компьютера.</span><span class="sxs-lookup"><span data-stu-id="186e3-120">Selects the machine store.</span></span> <span data-ttu-id="186e3-121">Используйте этот параметр вместе с параметром **/list** или **/remove**, чтобы указать, что данное действие должно применяться к хранилищу компьютера.</span><span class="sxs-lookup"><span data-stu-id="186e3-121">Use this option with the **/list** or **/remove** option to specify that the action should apply to the machine store.</span></span><br /><br /> <span data-ttu-id="186e3-122">Новые возможности в .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="186e3-122">New in the .NET Framework 2.0</span></span>|  
|<span data-ttu-id="186e3-123">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="186e3-123">**/quiet**</span></span>|<span data-ttu-id="186e3-124">Определяет тихий режим, отключает вывод всех сообщений, кроме сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="186e3-124">Specifies quiet mode; suppresses informational output so that only error messages appear.</span></span>|  
|<span data-ttu-id="186e3-125">**/remove**</span><span class="sxs-lookup"><span data-stu-id="186e3-125">**/remove**</span></span>|<span data-ttu-id="186e3-126">Полностью удаляет все существующие хранилища для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="186e3-126">Permanently removes all existing stores for the current user.</span></span>|  
|<span data-ttu-id="186e3-127">**/roaming**</span><span class="sxs-lookup"><span data-stu-id="186e3-127">**/roaming**</span></span>|<span data-ttu-id="186e3-128">Задает перемещаемое хранилище.</span><span class="sxs-lookup"><span data-stu-id="186e3-128">Selects the roaming store.</span></span> <span data-ttu-id="186e3-129">Используйте этот параметр вместе с параметром **/list** или **/remove**, чтобы указать, что данное действие должно применяться к перемещаемому хранилищу.</span><span class="sxs-lookup"><span data-stu-id="186e3-129">Use this option with the **/list** or **/remove** options to specify that the action should apply to the roaming store.</span></span>|  
|<span data-ttu-id="186e3-130">**/?**</span><span class="sxs-lookup"><span data-stu-id="186e3-130">**/?**</span></span>|<span data-ttu-id="186e3-131">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="186e3-131">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="186e3-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="186e3-132">Remarks</span></span>  
 <span data-ttu-id="186e3-133">При запуске программы Storeadm.exe из командной строки без указания параметров будут отображены ее синтаксис и параметры.</span><span class="sxs-lookup"><span data-stu-id="186e3-133">Running Storeadm.exe from the command line without specifying any options displays the syntax and options for the tool.</span></span>  
  
 <span data-ttu-id="186e3-134">Обычно используется лишь один из параметров **/list** и **/remove**, однако при использовании нескольких параметров они будут обрабатываться в порядке их указания в командной строке.</span><span class="sxs-lookup"><span data-stu-id="186e3-134">The **/list** and **/remove** options are typically used one at a time; however, if two or more options are specified they will be performed in the order in which they appear on the command line.</span></span>  
  
 <span data-ttu-id="186e3-135">Приложение может выбрать для сохранения одно из двух хранилищ пользователя или хранилище компьютера.</span><span class="sxs-lookup"><span data-stu-id="186e3-135">Applications have a choice of saving to one of two stores for a user or to the machine store:</span></span>  
  
- <span data-ttu-id="186e3-136">Локальное хранилище располагается в том месте, которое гарантированно не является перемещаемым (в Windows 2000 или более поздних версиях), даже если для пользователя включен режим перемещения данных.</span><span class="sxs-lookup"><span data-stu-id="186e3-136">The local store exists in a location that is guaranteed not to roam (on Windows 2000 and later) even if user data roaming is enabled for the user.</span></span>  
  
- <span data-ttu-id="186e3-137">Перемещаемое хранилище располагается в месте, которое можно переместить, но только если для пользователя включен режим перемещения с помощью средств администрирования Windows NT.</span><span class="sxs-lookup"><span data-stu-id="186e3-137">The roaming store exists in a location that is able to roam, but can only do so if roaming is enabled for the user via Windows NT administration.</span></span>  
  
- <span data-ttu-id="186e3-138">Хранилище компьютера является общим для всех пользователей данного компьютера и располагается в его общем каталоге.</span><span class="sxs-lookup"><span data-stu-id="186e3-138">The machine store is common to all users on a machine and is stored under a common directory on that machine.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="186e3-139">Поддержка хранилища компьютера является новой возможностью .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="186e3-139">The machine store is new in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="186e3-140">Управление программой Storeadm.exe не зависит от того, включен ли режим перемещения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="186e3-140">Whether roaming is actually enabled for the user does not affect the administration of Storeadm.exe.</span></span> <span data-ttu-id="186e3-141">При запуске программы без параметров все действия применяются к локальному хранилищу.</span><span class="sxs-lookup"><span data-stu-id="186e3-141">Running the tool without any options applies all actions to the local store.</span></span> <span data-ttu-id="186e3-142">При запуске программы с параметром **/roaming** все действия будут применяться к перемещаемому хранилищу.</span><span class="sxs-lookup"><span data-stu-id="186e3-142">Running the tool with the **/roaming** option applies all actions to the store that is able to roam.</span></span> <span data-ttu-id="186e3-143">При запуске программы с параметром **/machine** все действия применяются к хранилищу компьютера.</span><span class="sxs-lookup"><span data-stu-id="186e3-143">Running the tool with the **/machine** option applies all actions to the machine store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="186e3-144">См. также</span><span class="sxs-lookup"><span data-stu-id="186e3-144">See also</span></span>

- [<span data-ttu-id="186e3-145">Инструменты</span><span class="sxs-lookup"><span data-stu-id="186e3-145">Tools</span></span>](index.md)
- [<span data-ttu-id="186e3-146">Изолированное хранилище</span><span class="sxs-lookup"><span data-stu-id="186e3-146">Isolated Storage</span></span>](../../standard/io/isolated-storage.md)
- [<span data-ttu-id="186e3-147">Командные строки</span><span class="sxs-lookup"><span data-stu-id="186e3-147">Command Prompts</span></span>](developer-command-prompt-for-vs.md)

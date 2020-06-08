---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: b6a1c8fce17e3e5a54366c2ff4dff4e6aa668f56
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408664"
---
# <a name="-errorreport"></a><span data-ttu-id="a8414-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="a8414-102">-errorreport</span></span>

<span data-ttu-id="a8414-103">Указывает, как компилятор Visual Basic должен сообщать о внутренних ошибках компилятора.</span><span class="sxs-lookup"><span data-stu-id="a8414-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8414-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8414-104">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="a8414-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8414-105">Remarks</span></span>

<span data-ttu-id="a8414-106">Этот параметр предоставляет удобный способ для сообщения о внутренней ошибке компилятора Visual Basic команде разработчиков Visual Basic в корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a8414-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="a8414-107">По умолчанию компилятор не отправляет сведения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a8414-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="a8414-108">Однако при возникновении внутренней ошибки компилятора этот параметр позволяет сообщить о ней в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a8414-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="a8414-109">Эта информация поможет инженерам Майкрософт определить причину и улучшить следующий выпуск Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a8414-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="a8414-110">Возможность отправлять отчеты пользователем зависит от политики разрешений компьютера и пользователя.</span><span class="sxs-lookup"><span data-stu-id="a8414-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="a8414-111">Следующая таблица обобщает эффект параметра `-errorreport`.</span><span class="sxs-lookup"><span data-stu-id="a8414-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="a8414-112">Параметр</span><span class="sxs-lookup"><span data-stu-id="a8414-112">Option</span></span>|<span data-ttu-id="a8414-113">Поведение</span><span class="sxs-lookup"><span data-stu-id="a8414-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="a8414-114">При возникновении внутренней ошибки компилятора появляется диалоговое окно, в котором можно просмотреть точные данные, собранные компилятором.</span><span class="sxs-lookup"><span data-stu-id="a8414-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="a8414-115">Вы можете определить, есть ли в отчете об ошибках конфиденциальные сведения, и принять решение о том, отправлять ли его в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a8414-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="a8414-116">Если вы решили отправить его, а параметры политики компьютера и пользователя это разрешают, компилятор отправляет данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a8414-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="a8414-117">Отчет об ошибке помещается в очередь.</span><span class="sxs-lookup"><span data-stu-id="a8414-117">Queues the error report.</span></span> <span data-ttu-id="a8414-118">При входе с правами администратора можно сообщить о любых сбоях с момента последнего входа в систему (предложение отправить отчеты об ошибках будет выводиться не чаще одного раза в три дня).</span><span class="sxs-lookup"><span data-stu-id="a8414-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="a8414-119">Это поведение по умолчанию, если параметр `-errorreport` не указан.</span><span class="sxs-lookup"><span data-stu-id="a8414-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="a8414-120">Если возникает внутренняя ошибка компилятора, а параметры политики компьютера и пользователя это разрешают, компилятор отправляет данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a8414-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="a8414-121">Параметр `-errorreport:send` пытается автоматически отправить сведения об ошибке в корпорацию Майкрософт, если отчеты включены с помощью системных параметров [Отчеты об ошибках Windows](/windows/desktop/wer/windows-error-reporting).</span><span class="sxs-lookup"><span data-stu-id="a8414-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="a8414-122">Если возникает внутренняя ошибка компилятора, сбор данных и их отправка в корпорацию Майкрософт выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="a8414-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="a8414-123">Компилятор отправляет данные, включающие стек на момент возникновения ошибки, который обычно содержит некоторый исходный код.</span><span class="sxs-lookup"><span data-stu-id="a8414-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="a8414-124">Если `-errorreport` используется с параметром [-bugreport](bugreport.md), то отправляется весь исходный файл.</span><span class="sxs-lookup"><span data-stu-id="a8414-124">If `-errorreport` is used with the [-bugreport](bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="a8414-125">Этот вариант лучше всего использовать с параметром [-bugreport](bugreport.md), так как он позволяет специалистам Майкрософт легче воспроизвести ошибку.</span><span class="sxs-lookup"><span data-stu-id="a8414-125">This option is best used with the [-bugreport](bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="a8414-126">Параметр `-errorreport` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="a8414-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="a8414-127">Пример</span><span class="sxs-lookup"><span data-stu-id="a8414-127">Example</span></span>

<span data-ttu-id="a8414-128">Следующий код пытается скомпилировать `T2.vb`, и если компилятор обнаруживает внутреннюю ошибку компилятора, он предлагает вам отправить отчет об ошибке в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a8414-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="a8414-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a8414-129">See also</span></span>

- [<span data-ttu-id="a8414-130">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="a8414-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a8414-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="a8414-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="a8414-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="a8414-132">-bugreport</span></span>](bugreport.md)

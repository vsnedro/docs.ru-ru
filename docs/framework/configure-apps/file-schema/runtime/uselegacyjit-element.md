---
title: Элемент <useLegacyJit>
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
ms.openlocfilehash: a126b8c0050a8d1fd96a3d090f9b018a9faa07a7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968855"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="b3213-102">Элемент \<useLegacyJit></span><span class="sxs-lookup"><span data-stu-id="b3213-102">\<useLegacyJit> Element</span></span>

<span data-ttu-id="b3213-103">Определяет, использует ли среда CLR устаревший 64-разрядный JIT-компилятор для JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="b3213-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<useLegacyJit>**  
  
## <a name="syntax"></a><span data-ttu-id="b3213-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3213-104">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="b3213-105">В имени элемента `useLegacyJit` учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="b3213-105">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3213-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="b3213-106">Attributes and elements</span></span>

<span data-ttu-id="b3213-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b3213-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3213-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b3213-108">Attributes</span></span>  
  
| <span data-ttu-id="b3213-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b3213-109">Attribute</span></span> | <span data-ttu-id="b3213-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="b3213-110">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="b3213-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b3213-111">Required attribute.</span></span><br><br><span data-ttu-id="b3213-112">Указывает, использует ли среда выполнения устаревший JIT-компилятор 64.</span><span class="sxs-lookup"><span data-stu-id="b3213-112">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="b3213-113">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="b3213-113">enabled attribute</span></span>  
  
| <span data-ttu-id="b3213-114">Значение</span><span class="sxs-lookup"><span data-stu-id="b3213-114">Value</span></span> | <span data-ttu-id="b3213-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b3213-115">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="b3213-116">0</span><span class="sxs-lookup"><span data-stu-id="b3213-116">0</span></span>     | <span data-ttu-id="b3213-117">Среда CLR использует новый 64-разрядный компилятор JIT, входящий в .NET Framework 4,6 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="b3213-117">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="b3213-118">1</span><span class="sxs-lookup"><span data-stu-id="b3213-118">1</span></span>     | <span data-ttu-id="b3213-119">Среда CLR использует устаревший 64-разрядный компилятор JIT.</span><span class="sxs-lookup"><span data-stu-id="b3213-119">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="b3213-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b3213-120">Child elements</span></span>

<span data-ttu-id="b3213-121">Нет</span><span class="sxs-lookup"><span data-stu-id="b3213-121">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="b3213-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b3213-122">Parent elements</span></span>  
  
| <span data-ttu-id="b3213-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="b3213-123">Element</span></span>         | <span data-ttu-id="b3213-124">Описание</span><span class="sxs-lookup"><span data-stu-id="b3213-124">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="b3213-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3213-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="b3213-126">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b3213-126">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="b3213-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="b3213-127">Remarks</span></span>  

<span data-ttu-id="b3213-128">Начиная с .NET Framework 4,6, среда CLR по умолчанию использует новый 64-разрядный компилятор для JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="b3213-128">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="b3213-129">В некоторых случаях это может привести к различию в поведении кода приложения, скомпилированного JIT-компилятором в предыдущей версии 64-разрядного компилятора JIT.</span><span class="sxs-lookup"><span data-stu-id="b3213-129">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="b3213-130">Установив `enabled` атрибут `<useLegacyJit>` элемента в значение `1` , вы можете отключить новый 64-разрядный компилятор JIT, а вместо этого скомпилировать приложение с помощью устаревшей версии JIT-компилятора с 64.</span><span class="sxs-lookup"><span data-stu-id="b3213-130">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3213-131">Этот `<useLegacyJit>` элемент влияет только на 64-разрядную КОМПИЛЯЦИЮ JIT.</span><span class="sxs-lookup"><span data-stu-id="b3213-131">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="b3213-132">Компиляция с 32-разрядным компилятором JIT не затрагивается.</span><span class="sxs-lookup"><span data-stu-id="b3213-132">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="b3213-133">Вместо использования параметра файла конфигурации можно включить устаревший 64-разрядный компилятор JIT в двух других случаях:</span><span class="sxs-lookup"><span data-stu-id="b3213-133">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="b3213-134">Задание переменной среды</span><span class="sxs-lookup"><span data-stu-id="b3213-134">Setting an environment variable</span></span>

  <span data-ttu-id="b3213-135">Задайте `COMPLUS_useLegacyJit` для переменной среды значение `0` (используйте новый 64-разрядный компилятор JIT) или `1` (используйте более старый 64-разрядный компилятор JIT):</span><span class="sxs-lookup"><span data-stu-id="b3213-135">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```env  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="b3213-136">Переменная среды имеет *глобальную область*, что означает влияние на все приложения, выполняемые на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b3213-136">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="b3213-137">Если значение задано, оно может быть переопределено параметром файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b3213-137">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="b3213-138">Имя переменной среды не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="b3213-138">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="b3213-139">Добавление раздела реестра</span><span class="sxs-lookup"><span data-stu-id="b3213-139">Adding a registry key</span></span>

  <span data-ttu-id="b3213-140">Можно включить устаревший 64-разрядный компилятор JIT, добавив `REG_DWORD` значение в `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` ключ или в реестре.</span><span class="sxs-lookup"><span data-stu-id="b3213-140">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="b3213-141">Значение имеет имя `useLegacyJit` .</span><span class="sxs-lookup"><span data-stu-id="b3213-141">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="b3213-142">Если значение равно 0, используется новый компилятор.</span><span class="sxs-lookup"><span data-stu-id="b3213-142">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="b3213-143">Если значение равно 1, то включен устаревший JIT-компилятор 64.</span><span class="sxs-lookup"><span data-stu-id="b3213-143">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="b3213-144">Имя значения реестра обрабатывается без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="b3213-144">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="b3213-145">Добавление значения в `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` ключ влияет на все приложения, выполняющиеся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b3213-145">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="b3213-146">Добавление значения в `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` ключ влияет на все приложения, запущенные текущим пользователем.</span><span class="sxs-lookup"><span data-stu-id="b3213-146">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="b3213-147">Если на компьютере настроено несколько учетных записей пользователей, затрагиваются только приложения, запущенные текущим пользователем, если только значение не будет добавлено в разделы реестра для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="b3213-147">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="b3213-148">Добавление `<useLegacyJit>` элемента в файл конфигурации переопределяет параметры реестра, если они есть.</span><span class="sxs-lookup"><span data-stu-id="b3213-148">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3213-149">Пример</span><span class="sxs-lookup"><span data-stu-id="b3213-149">Example</span></span>  

<span data-ttu-id="b3213-150">Следующий файл конфигурации отключает компиляцию с помощью нового 64-разрядного компилятора JIT, а вместо этого использует устаревший JIT-компилятор с 64.</span><span class="sxs-lookup"><span data-stu-id="b3213-150">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3213-151">См. также</span><span class="sxs-lookup"><span data-stu-id="b3213-151">See also</span></span>

- [<span data-ttu-id="b3213-152">\<runtime>Дерев</span><span class="sxs-lookup"><span data-stu-id="b3213-152">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="b3213-153">\<configuration>Дерев</span><span class="sxs-lookup"><span data-stu-id="b3213-153">\<configuration> Element</span></span>](../configuration-element.md)
- [<span data-ttu-id="b3213-154">Устранение рисков. Новый 64-разрядный JIT-компилятор</span><span class="sxs-lookup"><span data-stu-id="b3213-154">Mitigation: New 64-bit JIT Compiler</span></span>](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)

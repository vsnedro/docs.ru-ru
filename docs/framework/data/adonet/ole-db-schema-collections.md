---
title: Коллекции схемы OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 90899a123b3dafcd47a50ef8f6eb003938b22a03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186943"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="78ead-102">Коллекции схемы OLE DB</span><span class="sxs-lookup"><span data-stu-id="78ead-102">OLE DB Schema Collections</span></span>

<span data-ttu-id="78ead-103">В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="78ead-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="78ead-104">Поставщик OLE DB для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="78ead-104">Microsoft SQL Server OLE DB Provider</span></span>  

 <span data-ttu-id="78ead-105">Драйвер OLE DB для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="78ead-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="78ead-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="78ead-106">Tables</span></span>  
  
- <span data-ttu-id="78ead-107">Столбцы</span><span class="sxs-lookup"><span data-stu-id="78ead-107">Columns</span></span>  
  
- <span data-ttu-id="78ead-108">Процедуры</span><span class="sxs-lookup"><span data-stu-id="78ead-108">Procedures</span></span>  
  
- <span data-ttu-id="78ead-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="78ead-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="78ead-110">Каталог</span><span class="sxs-lookup"><span data-stu-id="78ead-110">Catalog</span></span>  
  
- <span data-ttu-id="78ead-111">Индексы</span><span class="sxs-lookup"><span data-stu-id="78ead-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="78ead-112">Таблицы</span><span class="sxs-lookup"><span data-stu-id="78ead-112">Tables</span></span>  
  
|<span data-ttu-id="78ead-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-113">ColumnName</span></span>|<span data-ttu-id="78ead-114">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-115">TABLE_CATALOG</span></span>|<span data-ttu-id="78ead-116">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-116">String</span></span>|  
|<span data-ttu-id="78ead-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="78ead-118">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-118">String</span></span>|  
|<span data-ttu-id="78ead-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-119">TABLE_NAME</span></span>|<span data-ttu-id="78ead-120">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-120">String</span></span>|  
|<span data-ttu-id="78ead-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-121">TABLE_TYPE</span></span>|<span data-ttu-id="78ead-122">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-122">String</span></span>|  
|<span data-ttu-id="78ead-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-123">TABLE_GUID</span></span>|<span data-ttu-id="78ead-124">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-124">Guid</span></span>|  
|<span data-ttu-id="78ead-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-125">DESCRIPTION</span></span>|<span data-ttu-id="78ead-126">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-126">String</span></span>|  
|<span data-ttu-id="78ead-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="78ead-127">TABLE_PROPID</span></span>|<span data-ttu-id="78ead-128">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-128">Int64</span></span>|  
|<span data-ttu-id="78ead-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="78ead-129">DATE_CREATED</span></span>|<span data-ttu-id="78ead-130">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-130">DateTime</span></span>|  
|<span data-ttu-id="78ead-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="78ead-131">DATE_MODIFIED</span></span>|<span data-ttu-id="78ead-132">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="78ead-133">Столбцы</span><span class="sxs-lookup"><span data-stu-id="78ead-133">Columns</span></span>  
  
|<span data-ttu-id="78ead-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-134">ColumnName</span></span>|<span data-ttu-id="78ead-135">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-136">TABLE_CATALOG</span></span>|<span data-ttu-id="78ead-137">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-137">String</span></span>|  
|<span data-ttu-id="78ead-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="78ead-139">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-139">String</span></span>|  
|<span data-ttu-id="78ead-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-140">TABLE_NAME</span></span>|<span data-ttu-id="78ead-141">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-141">String</span></span>|  
|<span data-ttu-id="78ead-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-142">COLUMN_NAME</span></span>|<span data-ttu-id="78ead-143">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-143">String</span></span>|  
|<span data-ttu-id="78ead-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-144">COLUMN_GUID</span></span>|<span data-ttu-id="78ead-145">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-145">Guid</span></span>|  
|<span data-ttu-id="78ead-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="78ead-146">COLUMN_PROPID</span></span>|<span data-ttu-id="78ead-147">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-147">Int64</span></span>|  
|<span data-ttu-id="78ead-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="78ead-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="78ead-149">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-149">Int64</span></span>|  
|<span data-ttu-id="78ead-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="78ead-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="78ead-151">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-151">Boolean</span></span>|  
|<span data-ttu-id="78ead-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="78ead-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="78ead-153">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-153">String</span></span>|  
|<span data-ttu-id="78ead-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="78ead-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="78ead-155">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-155">Int64</span></span>|  
|<span data-ttu-id="78ead-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="78ead-156">IS_NULLABLE</span></span>|<span data-ttu-id="78ead-157">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-157">Boolean</span></span>|  
|<span data-ttu-id="78ead-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-158">DATA_TYPE</span></span>|<span data-ttu-id="78ead-159">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-159">Int32</span></span>|  
|<span data-ttu-id="78ead-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-160">TYPE_GUID</span></span>|<span data-ttu-id="78ead-161">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-161">Guid</span></span>|  
|<span data-ttu-id="78ead-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="78ead-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="78ead-163">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-163">Int64</span></span>|  
|<span data-ttu-id="78ead-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="78ead-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="78ead-165">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-165">Int64</span></span>|  
|<span data-ttu-id="78ead-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="78ead-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="78ead-167">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-167">Int32</span></span>|  
|<span data-ttu-id="78ead-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="78ead-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="78ead-169">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-169">Int16</span></span>|  
|<span data-ttu-id="78ead-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="78ead-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="78ead-171">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-171">Int64</span></span>|  
|<span data-ttu-id="78ead-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="78ead-173">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-173">String</span></span>|  
|<span data-ttu-id="78ead-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="78ead-175">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-175">String</span></span>|  
|<span data-ttu-id="78ead-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="78ead-177">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-177">String</span></span>|  
|<span data-ttu-id="78ead-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="78ead-179">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-179">String</span></span>|  
|<span data-ttu-id="78ead-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="78ead-181">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-181">String</span></span>|  
|<span data-ttu-id="78ead-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-182">COLLATION_NAME</span></span>|<span data-ttu-id="78ead-183">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-183">String</span></span>|  
|<span data-ttu-id="78ead-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="78ead-185">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-185">String</span></span>|  
|<span data-ttu-id="78ead-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="78ead-187">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-187">String</span></span>|  
|<span data-ttu-id="78ead-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-188">DOMAIN_NAME</span></span>|<span data-ttu-id="78ead-189">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-189">String</span></span>|  
|<span data-ttu-id="78ead-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-190">DESCRIPTION</span></span>|<span data-ttu-id="78ead-191">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-191">String</span></span>|  
|<span data-ttu-id="78ead-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="78ead-192">COLUMN_LCID</span></span>|<span data-ttu-id="78ead-193">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-193">Int32</span></span>|  
|<span data-ttu-id="78ead-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="78ead-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="78ead-195">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-195">Int32</span></span>|  
|<span data-ttu-id="78ead-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="78ead-196">COLUMN_SORTID</span></span>|<span data-ttu-id="78ead-197">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-197">Int32</span></span>|  
|<span data-ttu-id="78ead-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="78ead-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="78ead-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="78ead-199">Byte[]</span></span>|  
|<span data-ttu-id="78ead-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="78ead-200">IS_COMPUTED</span></span>|<span data-ttu-id="78ead-201">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="78ead-202">Процедуры</span><span class="sxs-lookup"><span data-stu-id="78ead-202">Procedures</span></span>  
  
|<span data-ttu-id="78ead-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-203">ColumnName</span></span>|<span data-ttu-id="78ead-204">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="78ead-206">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-206">String</span></span>|  
|<span data-ttu-id="78ead-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="78ead-208">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-208">String</span></span>|  
|<span data-ttu-id="78ead-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="78ead-210">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-210">String</span></span>|  
|<span data-ttu-id="78ead-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="78ead-212">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-212">Int16</span></span>|  
|<span data-ttu-id="78ead-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="78ead-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="78ead-214">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-214">String</span></span>|  
|<span data-ttu-id="78ead-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-215">DESCRIPTION</span></span>|<span data-ttu-id="78ead-216">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-216">String</span></span>|  
|<span data-ttu-id="78ead-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="78ead-217">DATE_CREATED</span></span>|<span data-ttu-id="78ead-218">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-218">DateTime</span></span>|  
|<span data-ttu-id="78ead-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="78ead-219">DATE_MODIFIED</span></span>|<span data-ttu-id="78ead-220">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="78ead-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="78ead-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="78ead-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-222">ColumnName</span></span>|<span data-ttu-id="78ead-223">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="78ead-225">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-225">String</span></span>|  
|<span data-ttu-id="78ead-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="78ead-227">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-227">String</span></span>|  
|<span data-ttu-id="78ead-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="78ead-229">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-229">String</span></span>|  
|<span data-ttu-id="78ead-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-230">PARAMETER_NAME</span></span>|<span data-ttu-id="78ead-231">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-231">String</span></span>|  
|<span data-ttu-id="78ead-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="78ead-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="78ead-233">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-233">Int32</span></span>|  
|<span data-ttu-id="78ead-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="78ead-235">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-235">Int32</span></span>|  
|<span data-ttu-id="78ead-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="78ead-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="78ead-237">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-237">Boolean</span></span>|  
|<span data-ttu-id="78ead-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="78ead-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="78ead-239">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-239">String</span></span>|  
|<span data-ttu-id="78ead-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="78ead-240">IS_NULLABLE</span></span>|<span data-ttu-id="78ead-241">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-241">Boolean</span></span>|  
|<span data-ttu-id="78ead-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-242">DATA_TYPE</span></span>|<span data-ttu-id="78ead-243">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-243">Int32</span></span>|  
|<span data-ttu-id="78ead-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="78ead-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="78ead-245">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-245">Int64</span></span>|  
|<span data-ttu-id="78ead-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="78ead-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="78ead-247">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-247">Int64</span></span>|  
|<span data-ttu-id="78ead-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="78ead-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="78ead-249">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-249">Int32</span></span>|  
|<span data-ttu-id="78ead-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="78ead-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="78ead-251">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-251">Int16</span></span>|  
|<span data-ttu-id="78ead-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-252">DESCRIPTION</span></span>|<span data-ttu-id="78ead-253">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-253">String</span></span>|  
|<span data-ttu-id="78ead-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-254">TYPE_NAME</span></span>|<span data-ttu-id="78ead-255">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-255">String</span></span>|  
|<span data-ttu-id="78ead-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="78ead-257">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="78ead-258">Каталог</span><span class="sxs-lookup"><span data-stu-id="78ead-258">Catalog</span></span>  
  
|<span data-ttu-id="78ead-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-259">ColumnName</span></span>|<span data-ttu-id="78ead-260">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-261">CATALOG_NAME</span></span>|<span data-ttu-id="78ead-262">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-262">String</span></span>|  
|<span data-ttu-id="78ead-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-263">DESCRIPTION</span></span>|<span data-ttu-id="78ead-264">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="78ead-265">Индексы</span><span class="sxs-lookup"><span data-stu-id="78ead-265">Indexes</span></span>  
  
|<span data-ttu-id="78ead-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-266">ColumnName</span></span>|<span data-ttu-id="78ead-267">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-268">TABLE_CATALOG</span></span>|<span data-ttu-id="78ead-269">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-269">String</span></span>|  
|<span data-ttu-id="78ead-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="78ead-271">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-271">String</span></span>|  
|<span data-ttu-id="78ead-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-272">TABLE_NAME</span></span>|<span data-ttu-id="78ead-273">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-273">String</span></span>|  
|<span data-ttu-id="78ead-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-274">INDEX_CATALOG</span></span>|<span data-ttu-id="78ead-275">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-275">String</span></span>|  
|<span data-ttu-id="78ead-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="78ead-277">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-277">String</span></span>|  
|<span data-ttu-id="78ead-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-278">INDEX_NAME</span></span>|<span data-ttu-id="78ead-279">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-279">String</span></span>|  
|<span data-ttu-id="78ead-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="78ead-280">PRIMARY_KEY</span></span>|<span data-ttu-id="78ead-281">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-281">Boolean</span></span>|  
|<span data-ttu-id="78ead-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="78ead-282">UNIQUE</span></span>|<span data-ttu-id="78ead-283">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-283">Boolean</span></span>|  
|<span data-ttu-id="78ead-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="78ead-284">CLUSTERED</span></span>|<span data-ttu-id="78ead-285">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-285">Boolean</span></span>|  
|<span data-ttu-id="78ead-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-286">TYPE</span></span>|<span data-ttu-id="78ead-287">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-287">Int32</span></span>|  
|<span data-ttu-id="78ead-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="78ead-288">FILL_FACTOR</span></span>|<span data-ttu-id="78ead-289">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-289">Int32</span></span>|  
|<span data-ttu-id="78ead-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="78ead-290">INITIAL_SIZE</span></span>|<span data-ttu-id="78ead-291">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-291">Int32</span></span>|  
|<span data-ttu-id="78ead-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="78ead-292">NULLS</span></span>|<span data-ttu-id="78ead-293">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-293">Int32</span></span>|  
|<span data-ttu-id="78ead-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="78ead-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="78ead-295">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-295">Boolean</span></span>|  
|<span data-ttu-id="78ead-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="78ead-296">AUTO_UPDATE</span></span>|<span data-ttu-id="78ead-297">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-297">Boolean</span></span>|  
|<span data-ttu-id="78ead-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="78ead-298">NULL_COLLATION</span></span>|<span data-ttu-id="78ead-299">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-299">Int32</span></span>|  
|<span data-ttu-id="78ead-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="78ead-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="78ead-301">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-301">Int64</span></span>|  
|<span data-ttu-id="78ead-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-302">COLUMN_NAME</span></span>|<span data-ttu-id="78ead-303">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-303">String</span></span>|  
|<span data-ttu-id="78ead-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-304">COLUMN_GUID</span></span>|<span data-ttu-id="78ead-305">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-305">Guid</span></span>|  
|<span data-ttu-id="78ead-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="78ead-306">COLUMN_PROPID</span></span>|<span data-ttu-id="78ead-307">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-307">Int64</span></span>|  
|<span data-ttu-id="78ead-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="78ead-308">COLLATION</span></span>|<span data-ttu-id="78ead-309">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-309">Int16</span></span>|  
|<span data-ttu-id="78ead-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="78ead-310">CARDINALITY</span></span>|<span data-ttu-id="78ead-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="78ead-311">Decimal</span></span>|  
|<span data-ttu-id="78ead-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="78ead-312">PAGES</span></span>|<span data-ttu-id="78ead-313">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-313">Int32</span></span>|  
|<span data-ttu-id="78ead-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="78ead-314">FILTER_CONDITION</span></span>|<span data-ttu-id="78ead-315">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-315">String</span></span>|  
|<span data-ttu-id="78ead-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="78ead-316">INTEGRATED</span></span>|<span data-ttu-id="78ead-317">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="78ead-318">Поставщик Microsoft OLE DB для Oracle</span><span class="sxs-lookup"><span data-stu-id="78ead-318">Microsoft Oracle OLE DB Provider</span></span>  

 <span data-ttu-id="78ead-319">Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="78ead-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="78ead-320">Таблицы</span><span class="sxs-lookup"><span data-stu-id="78ead-320">Tables</span></span>  
  
- <span data-ttu-id="78ead-321">Столбцы</span><span class="sxs-lookup"><span data-stu-id="78ead-321">Columns</span></span>  
  
- <span data-ttu-id="78ead-322">Процедуры</span><span class="sxs-lookup"><span data-stu-id="78ead-322">Procedures</span></span>  
  
- <span data-ttu-id="78ead-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="78ead-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="78ead-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="78ead-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="78ead-325">Представления</span><span class="sxs-lookup"><span data-stu-id="78ead-325">Views</span></span>  
  
- <span data-ttu-id="78ead-326">Индексы</span><span class="sxs-lookup"><span data-stu-id="78ead-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="78ead-327">Таблицы</span><span class="sxs-lookup"><span data-stu-id="78ead-327">Tables</span></span>  
  
|<span data-ttu-id="78ead-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-328">ColumnName</span></span>|<span data-ttu-id="78ead-329">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-330">TABLE_CATALOG</span></span>|<span data-ttu-id="78ead-331">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-331">String</span></span>|  
|<span data-ttu-id="78ead-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="78ead-333">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-333">String</span></span>|  
|<span data-ttu-id="78ead-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-334">TABLE_NAME</span></span>|<span data-ttu-id="78ead-335">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-335">String</span></span>|  
|<span data-ttu-id="78ead-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-336">TABLE_TYPE</span></span>|<span data-ttu-id="78ead-337">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-337">String</span></span>|  
|<span data-ttu-id="78ead-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-338">TABLE_GUID</span></span>|<span data-ttu-id="78ead-339">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-339">Guid</span></span>|  
|<span data-ttu-id="78ead-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-340">DESCRIPTION</span></span>|<span data-ttu-id="78ead-341">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-341">String</span></span>|  
|<span data-ttu-id="78ead-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="78ead-342">TABLE_PROPID</span></span>|<span data-ttu-id="78ead-343">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-343">Int64</span></span>|  
|<span data-ttu-id="78ead-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="78ead-344">DATE_CREATED</span></span>|<span data-ttu-id="78ead-345">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-345">DateTime</span></span>|  
|<span data-ttu-id="78ead-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="78ead-346">DATE_MODIFIED</span></span>|<span data-ttu-id="78ead-347">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="78ead-348">Столбцы</span><span class="sxs-lookup"><span data-stu-id="78ead-348">Columns</span></span>  
  
|<span data-ttu-id="78ead-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-349">ColumnName</span></span>|<span data-ttu-id="78ead-350">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-351">TABLE_CATALOG</span></span>|<span data-ttu-id="78ead-352">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-352">String</span></span>|  
|<span data-ttu-id="78ead-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="78ead-354">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-354">String</span></span>|  
|<span data-ttu-id="78ead-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-355">TABLE_NAME</span></span>|<span data-ttu-id="78ead-356">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-356">String</span></span>|  
|<span data-ttu-id="78ead-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-357">COLUMN_NAME</span></span>|<span data-ttu-id="78ead-358">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-358">String</span></span>|  
|<span data-ttu-id="78ead-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-359">COLUMN_GUID</span></span>|<span data-ttu-id="78ead-360">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-360">Guid</span></span>|  
|<span data-ttu-id="78ead-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="78ead-361">COLUMN_PROPID</span></span>|<span data-ttu-id="78ead-362">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-362">Int64</span></span>|  
|<span data-ttu-id="78ead-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="78ead-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="78ead-364">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-364">Int64</span></span>|  
|<span data-ttu-id="78ead-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="78ead-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="78ead-366">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-366">Boolean</span></span>|  
|<span data-ttu-id="78ead-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="78ead-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="78ead-368">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-368">String</span></span>|  
|<span data-ttu-id="78ead-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="78ead-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="78ead-370">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-370">Int64</span></span>|  
|<span data-ttu-id="78ead-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="78ead-371">IS_NULLABLE</span></span>|<span data-ttu-id="78ead-372">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-372">Boolean</span></span>|  
|<span data-ttu-id="78ead-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-373">DATA_TYPE</span></span>|<span data-ttu-id="78ead-374">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-374">Int32</span></span>|  
|<span data-ttu-id="78ead-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-375">TYPE_GUID</span></span>|<span data-ttu-id="78ead-376">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-376">Guid</span></span>|  
|<span data-ttu-id="78ead-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="78ead-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="78ead-378">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-378">Int64</span></span>|  
|<span data-ttu-id="78ead-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="78ead-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="78ead-380">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-380">Int64</span></span>|  
|<span data-ttu-id="78ead-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="78ead-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="78ead-382">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-382">Int32</span></span>|  
|<span data-ttu-id="78ead-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="78ead-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="78ead-384">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-384">Int16</span></span>|  
|<span data-ttu-id="78ead-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="78ead-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="78ead-386">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-386">Int64</span></span>|  
|<span data-ttu-id="78ead-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="78ead-388">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-388">String</span></span>|  
|<span data-ttu-id="78ead-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="78ead-390">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-390">String</span></span>|  
|<span data-ttu-id="78ead-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="78ead-392">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-392">String</span></span>|  
|<span data-ttu-id="78ead-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="78ead-394">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-394">String</span></span>|  
|<span data-ttu-id="78ead-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="78ead-396">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-396">String</span></span>|  
|<span data-ttu-id="78ead-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-397">COLLATION_NAME</span></span>|<span data-ttu-id="78ead-398">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-398">String</span></span>|  
|<span data-ttu-id="78ead-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="78ead-400">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-400">String</span></span>|  
|<span data-ttu-id="78ead-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="78ead-402">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-402">String</span></span>|  
|<span data-ttu-id="78ead-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-403">DOMAIN_NAME</span></span>|<span data-ttu-id="78ead-404">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-404">String</span></span>|  
|<span data-ttu-id="78ead-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-405">DESCRIPTION</span></span>|<span data-ttu-id="78ead-406">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="78ead-407">Процедуры</span><span class="sxs-lookup"><span data-stu-id="78ead-407">Procedures</span></span>  
  
|<span data-ttu-id="78ead-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-408">ColumnName</span></span>|<span data-ttu-id="78ead-409">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="78ead-411">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-411">String</span></span>|  
|<span data-ttu-id="78ead-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="78ead-413">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-413">String</span></span>|  
|<span data-ttu-id="78ead-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="78ead-415">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-415">String</span></span>|  
|<span data-ttu-id="78ead-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="78ead-417">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-417">Int16</span></span>|  
|<span data-ttu-id="78ead-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="78ead-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="78ead-419">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-419">String</span></span>|  
|<span data-ttu-id="78ead-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-420">DESCRIPTION</span></span>|<span data-ttu-id="78ead-421">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-421">String</span></span>|  
|<span data-ttu-id="78ead-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="78ead-422">DATE_CREATED</span></span>|<span data-ttu-id="78ead-423">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-423">DateTime</span></span>|  
|<span data-ttu-id="78ead-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="78ead-424">DATE_MODIFIED</span></span>|<span data-ttu-id="78ead-425">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="78ead-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="78ead-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="78ead-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-427">ColumnName</span></span>|<span data-ttu-id="78ead-428">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="78ead-430">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-430">String</span></span>|  
|<span data-ttu-id="78ead-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="78ead-432">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-432">String</span></span>|  
|<span data-ttu-id="78ead-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="78ead-434">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-434">String</span></span>|  
|<span data-ttu-id="78ead-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-435">COLUMN_NAME</span></span>|<span data-ttu-id="78ead-436">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-436">String</span></span>|  
|<span data-ttu-id="78ead-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-437">COLUMN_GUID</span></span>|<span data-ttu-id="78ead-438">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-438">Guid</span></span>|  
|<span data-ttu-id="78ead-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="78ead-439">COLUMN_PROPID</span></span>|<span data-ttu-id="78ead-440">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-440">Int64</span></span>|  
|<span data-ttu-id="78ead-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="78ead-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="78ead-442">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-442">Int64</span></span>|  
|<span data-ttu-id="78ead-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="78ead-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="78ead-444">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-444">Int64</span></span>|  
|<span data-ttu-id="78ead-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="78ead-445">IS_NULLABLE</span></span>|<span data-ttu-id="78ead-446">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-446">Boolean</span></span>|  
|<span data-ttu-id="78ead-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-447">DATA_TYPE</span></span>|<span data-ttu-id="78ead-448">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-448">Int32</span></span>|  
|<span data-ttu-id="78ead-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-449">TYPE_GUID</span></span>|<span data-ttu-id="78ead-450">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-450">Guid</span></span>|  
|<span data-ttu-id="78ead-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="78ead-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="78ead-452">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-452">Int64</span></span>|  
|<span data-ttu-id="78ead-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="78ead-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="78ead-454">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-454">Int64</span></span>|  
|<span data-ttu-id="78ead-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="78ead-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="78ead-456">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-456">Int32</span></span>|  
|<span data-ttu-id="78ead-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="78ead-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="78ead-458">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-458">Int16</span></span>|  
|<span data-ttu-id="78ead-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-459">DESCRIPTION</span></span>|<span data-ttu-id="78ead-460">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-460">String</span></span>|  
|<span data-ttu-id="78ead-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="78ead-461">OVERLOAD</span></span>|<span data-ttu-id="78ead-462">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="78ead-463">Представления</span><span class="sxs-lookup"><span data-stu-id="78ead-463">Views</span></span>  
  
|<span data-ttu-id="78ead-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-464">ColumnName</span></span>|<span data-ttu-id="78ead-465">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-466">TABLE_CATALOG</span></span>|<span data-ttu-id="78ead-467">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-467">String</span></span>|  
|<span data-ttu-id="78ead-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="78ead-469">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-469">String</span></span>|  
|<span data-ttu-id="78ead-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-470">TABLE_NAME</span></span>|<span data-ttu-id="78ead-471">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-471">String</span></span>|  
|<span data-ttu-id="78ead-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="78ead-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="78ead-473">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-473">String</span></span>|  
|<span data-ttu-id="78ead-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-474">CHECK_OPTION</span></span>|<span data-ttu-id="78ead-475">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-475">Boolean</span></span>|  
|<span data-ttu-id="78ead-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="78ead-476">IS_UPDATABLE</span></span>|<span data-ttu-id="78ead-477">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-477">Boolean</span></span>|  
|<span data-ttu-id="78ead-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-478">DESCRIPTION</span></span>|<span data-ttu-id="78ead-479">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-479">String</span></span>|  
|<span data-ttu-id="78ead-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="78ead-480">DATE_CREATED</span></span>|<span data-ttu-id="78ead-481">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-481">DateTime</span></span>|  
|<span data-ttu-id="78ead-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="78ead-482">DATE_MODIFIED</span></span>|<span data-ttu-id="78ead-483">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="78ead-484">Индексы</span><span class="sxs-lookup"><span data-stu-id="78ead-484">Indexes</span></span>  
  
|<span data-ttu-id="78ead-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-485">ColumnName</span></span>|<span data-ttu-id="78ead-486">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-487">TABLE_CATALOG</span></span>|<span data-ttu-id="78ead-488">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-488">String</span></span>|  
|<span data-ttu-id="78ead-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="78ead-490">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-490">String</span></span>|  
|<span data-ttu-id="78ead-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-491">TABLE_NAME</span></span>|<span data-ttu-id="78ead-492">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-492">String</span></span>|  
|<span data-ttu-id="78ead-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-493">INDEX_CATALOG</span></span>|<span data-ttu-id="78ead-494">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-494">String</span></span>|  
|<span data-ttu-id="78ead-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="78ead-496">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-496">String</span></span>|  
|<span data-ttu-id="78ead-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-497">INDEX_NAME</span></span>|<span data-ttu-id="78ead-498">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-498">String</span></span>|  
|<span data-ttu-id="78ead-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="78ead-499">PRIMARY_KEY</span></span>|<span data-ttu-id="78ead-500">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-500">Boolean</span></span>|  
|<span data-ttu-id="78ead-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="78ead-501">UNIQUE</span></span>|<span data-ttu-id="78ead-502">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-502">Boolean</span></span>|  
|<span data-ttu-id="78ead-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="78ead-503">CLUSTERED</span></span>|<span data-ttu-id="78ead-504">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-504">Boolean</span></span>|  
|<span data-ttu-id="78ead-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-505">TYPE</span></span>|<span data-ttu-id="78ead-506">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-506">Int32</span></span>|  
|<span data-ttu-id="78ead-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="78ead-507">FILL_FACTOR</span></span>|<span data-ttu-id="78ead-508">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-508">Int32</span></span>|  
|<span data-ttu-id="78ead-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="78ead-509">INITIAL_SIZE</span></span>|<span data-ttu-id="78ead-510">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-510">Int32</span></span>|  
|<span data-ttu-id="78ead-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="78ead-511">NULLS</span></span>|<span data-ttu-id="78ead-512">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-512">Int32</span></span>|  
|<span data-ttu-id="78ead-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="78ead-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="78ead-514">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-514">Boolean</span></span>|  
|<span data-ttu-id="78ead-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="78ead-515">AUTO_UPDATE</span></span>|<span data-ttu-id="78ead-516">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-516">Boolean</span></span>|  
|<span data-ttu-id="78ead-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="78ead-517">NULL_COLLATION</span></span>|<span data-ttu-id="78ead-518">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-518">Int32</span></span>|  
|<span data-ttu-id="78ead-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="78ead-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="78ead-520">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-520">Int64</span></span>|  
|<span data-ttu-id="78ead-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-521">COLUMN_NAME</span></span>|<span data-ttu-id="78ead-522">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-522">String</span></span>|  
|<span data-ttu-id="78ead-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-523">COLUMN_GUID</span></span>|<span data-ttu-id="78ead-524">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-524">Guid</span></span>|  
|<span data-ttu-id="78ead-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="78ead-525">COLUMN_PROPID</span></span>|<span data-ttu-id="78ead-526">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-526">Int64</span></span>|  
|<span data-ttu-id="78ead-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="78ead-527">COLLATION</span></span>|<span data-ttu-id="78ead-528">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-528">Int16</span></span>|  
|<span data-ttu-id="78ead-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="78ead-529">CARDINALITY</span></span>|<span data-ttu-id="78ead-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="78ead-530">Decimal</span></span>|  
|<span data-ttu-id="78ead-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="78ead-531">PAGES</span></span>|<span data-ttu-id="78ead-532">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-532">Int32</span></span>|  
|<span data-ttu-id="78ead-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="78ead-533">FILTER_CONDITION</span></span>|<span data-ttu-id="78ead-534">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-534">String</span></span>|  
|<span data-ttu-id="78ead-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="78ead-535">INTEGRATED</span></span>|<span data-ttu-id="78ead-536">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="78ead-537">Поставщик OLE DB для Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="78ead-537">Microsoft Jet OLE DB Provider</span></span>  

 <span data-ttu-id="78ead-538">Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="78ead-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="78ead-539">Таблицы</span><span class="sxs-lookup"><span data-stu-id="78ead-539">Tables</span></span>  
  
- <span data-ttu-id="78ead-540">Столбцы</span><span class="sxs-lookup"><span data-stu-id="78ead-540">Columns</span></span>  
  
- <span data-ttu-id="78ead-541">Процедуры</span><span class="sxs-lookup"><span data-stu-id="78ead-541">Procedures</span></span>  
  
- <span data-ttu-id="78ead-542">Представления</span><span class="sxs-lookup"><span data-stu-id="78ead-542">Views</span></span>  
  
- <span data-ttu-id="78ead-543">Индексы</span><span class="sxs-lookup"><span data-stu-id="78ead-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="78ead-544">Таблицы</span><span class="sxs-lookup"><span data-stu-id="78ead-544">Tables</span></span>  
  
|<span data-ttu-id="78ead-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-545">ColumnName</span></span>|<span data-ttu-id="78ead-546">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-547">TABLE_CATALOG</span></span>|<span data-ttu-id="78ead-548">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-548">String</span></span>|  
|<span data-ttu-id="78ead-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="78ead-550">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-550">String</span></span>|  
|<span data-ttu-id="78ead-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-551">TABLE_NAME</span></span>|<span data-ttu-id="78ead-552">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-552">String</span></span>|  
|<span data-ttu-id="78ead-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-553">TABLE_TYPE</span></span>|<span data-ttu-id="78ead-554">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-554">String</span></span>|  
|<span data-ttu-id="78ead-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-555">TABLE_GUID</span></span>|<span data-ttu-id="78ead-556">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-556">Guid</span></span>|  
|<span data-ttu-id="78ead-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-557">DESCRIPTION</span></span>|<span data-ttu-id="78ead-558">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-558">String</span></span>|  
|<span data-ttu-id="78ead-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="78ead-559">TABLE_PROPID</span></span>|<span data-ttu-id="78ead-560">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-560">Int64</span></span>|  
|<span data-ttu-id="78ead-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="78ead-561">DATE_CREATED</span></span>|<span data-ttu-id="78ead-562">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-562">DateTime</span></span>|  
|<span data-ttu-id="78ead-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="78ead-563">DATE_MODIFIED</span></span>|<span data-ttu-id="78ead-564">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="78ead-565">Столбцы</span><span class="sxs-lookup"><span data-stu-id="78ead-565">Columns</span></span>  
  
|<span data-ttu-id="78ead-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-566">ColumnName</span></span>|<span data-ttu-id="78ead-567">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-568">TABLE_CATALOG</span></span>|<span data-ttu-id="78ead-569">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-569">String</span></span>|  
|<span data-ttu-id="78ead-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="78ead-571">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-571">String</span></span>|  
|<span data-ttu-id="78ead-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-572">TABLE_NAME</span></span>|<span data-ttu-id="78ead-573">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-573">String</span></span>|  
|<span data-ttu-id="78ead-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-574">COLUMN_NAME</span></span>|<span data-ttu-id="78ead-575">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-575">String</span></span>|  
|<span data-ttu-id="78ead-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-576">COLUMN_GUID</span></span>|<span data-ttu-id="78ead-577">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-577">Guid</span></span>|  
|<span data-ttu-id="78ead-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="78ead-578">COLUMN_PROPID</span></span>|<span data-ttu-id="78ead-579">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-579">Int64</span></span>|  
|<span data-ttu-id="78ead-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="78ead-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="78ead-581">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-581">Int64</span></span>|  
|<span data-ttu-id="78ead-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="78ead-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="78ead-583">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-583">Boolean</span></span>|  
|<span data-ttu-id="78ead-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="78ead-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="78ead-585">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-585">String</span></span>|  
|<span data-ttu-id="78ead-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="78ead-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="78ead-587">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-587">Int64</span></span>|  
|<span data-ttu-id="78ead-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="78ead-588">IS_NULLABLE</span></span>|<span data-ttu-id="78ead-589">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-589">Boolean</span></span>|  
|<span data-ttu-id="78ead-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-590">DATA_TYPE</span></span>|<span data-ttu-id="78ead-591">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-591">Int32</span></span>|  
|<span data-ttu-id="78ead-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-592">TYPE_GUID</span></span>|<span data-ttu-id="78ead-593">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-593">Guid</span></span>|  
|<span data-ttu-id="78ead-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="78ead-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="78ead-595">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-595">Int64</span></span>|  
|<span data-ttu-id="78ead-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="78ead-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="78ead-597">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-597">Int64</span></span>|  
|<span data-ttu-id="78ead-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="78ead-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="78ead-599">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-599">Int32</span></span>|  
|<span data-ttu-id="78ead-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="78ead-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="78ead-601">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-601">Int16</span></span>|  
|<span data-ttu-id="78ead-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="78ead-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="78ead-603">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-603">Int64</span></span>|  
|<span data-ttu-id="78ead-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="78ead-605">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-605">String</span></span>|  
|<span data-ttu-id="78ead-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="78ead-607">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-607">String</span></span>|  
|<span data-ttu-id="78ead-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="78ead-609">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-609">String</span></span>|  
|<span data-ttu-id="78ead-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="78ead-611">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-611">String</span></span>|  
|<span data-ttu-id="78ead-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="78ead-613">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-613">String</span></span>|  
|<span data-ttu-id="78ead-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-614">COLLATION_NAME</span></span>|<span data-ttu-id="78ead-615">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-615">String</span></span>|  
|<span data-ttu-id="78ead-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="78ead-617">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-617">String</span></span>|  
|<span data-ttu-id="78ead-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="78ead-619">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-619">String</span></span>|  
|<span data-ttu-id="78ead-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-620">DOMAIN_NAME</span></span>|<span data-ttu-id="78ead-621">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-621">String</span></span>|  
|<span data-ttu-id="78ead-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-622">DESCRIPTION</span></span>|<span data-ttu-id="78ead-623">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="78ead-624">Процедуры</span><span class="sxs-lookup"><span data-stu-id="78ead-624">Procedures</span></span>  
  
|<span data-ttu-id="78ead-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-625">ColumnName</span></span>|<span data-ttu-id="78ead-626">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="78ead-628">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-628">String</span></span>|  
|<span data-ttu-id="78ead-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="78ead-630">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-630">String</span></span>|  
|<span data-ttu-id="78ead-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="78ead-632">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-632">String</span></span>|  
|<span data-ttu-id="78ead-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="78ead-634">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-634">Int16</span></span>|  
|<span data-ttu-id="78ead-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="78ead-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="78ead-636">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-636">String</span></span>|  
|<span data-ttu-id="78ead-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-637">DESCRIPTION</span></span>|<span data-ttu-id="78ead-638">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-638">String</span></span>|  
|<span data-ttu-id="78ead-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="78ead-639">DATE_CREATED</span></span>|<span data-ttu-id="78ead-640">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-640">DateTime</span></span>|  
|<span data-ttu-id="78ead-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="78ead-641">DATE_MODIFIED</span></span>|<span data-ttu-id="78ead-642">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="78ead-643">Представления</span><span class="sxs-lookup"><span data-stu-id="78ead-643">Views</span></span>  
  
|<span data-ttu-id="78ead-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-644">ColumnName</span></span>|<span data-ttu-id="78ead-645">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-646">TABLE_CATALOG</span></span>|<span data-ttu-id="78ead-647">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-647">String</span></span>|  
|<span data-ttu-id="78ead-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="78ead-649">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-649">String</span></span>|  
|<span data-ttu-id="78ead-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-650">TABLE_NAME</span></span>|<span data-ttu-id="78ead-651">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-651">String</span></span>|  
|<span data-ttu-id="78ead-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="78ead-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="78ead-653">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-653">String</span></span>|  
|<span data-ttu-id="78ead-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-654">CHECK_OPTION</span></span>|<span data-ttu-id="78ead-655">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-655">Boolean</span></span>|  
|<span data-ttu-id="78ead-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="78ead-656">IS_UPDATABLE</span></span>|<span data-ttu-id="78ead-657">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-657">Boolean</span></span>|  
|<span data-ttu-id="78ead-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78ead-658">DESCRIPTION</span></span>|<span data-ttu-id="78ead-659">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-659">String</span></span>|  
|<span data-ttu-id="78ead-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="78ead-660">DATE_CREATED</span></span>|<span data-ttu-id="78ead-661">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-661">DateTime</span></span>|  
|<span data-ttu-id="78ead-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="78ead-662">DATE_MODIFIED</span></span>|<span data-ttu-id="78ead-663">Дата и время</span><span class="sxs-lookup"><span data-stu-id="78ead-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="78ead-664">Индексы</span><span class="sxs-lookup"><span data-stu-id="78ead-664">Indexes</span></span>  
  
|<span data-ttu-id="78ead-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="78ead-665">ColumnName</span></span>|<span data-ttu-id="78ead-666">DataType</span><span class="sxs-lookup"><span data-stu-id="78ead-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="78ead-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-667">TABLE_CATALOG</span></span>|<span data-ttu-id="78ead-668">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-668">String</span></span>|  
|<span data-ttu-id="78ead-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="78ead-670">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-670">String</span></span>|  
|<span data-ttu-id="78ead-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-671">TABLE_NAME</span></span>|<span data-ttu-id="78ead-672">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-672">String</span></span>|  
|<span data-ttu-id="78ead-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="78ead-673">INDEX_CATALOG</span></span>|<span data-ttu-id="78ead-674">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-674">String</span></span>|  
|<span data-ttu-id="78ead-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="78ead-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="78ead-676">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-676">String</span></span>|  
|<span data-ttu-id="78ead-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-677">INDEX_NAME</span></span>|<span data-ttu-id="78ead-678">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-678">String</span></span>|  
|<span data-ttu-id="78ead-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="78ead-679">PRIMARY_KEY</span></span>|<span data-ttu-id="78ead-680">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-680">Boolean</span></span>|  
|<span data-ttu-id="78ead-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="78ead-681">UNIQUE</span></span>|<span data-ttu-id="78ead-682">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-682">Boolean</span></span>|  
|<span data-ttu-id="78ead-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="78ead-683">CLUSTERED</span></span>|<span data-ttu-id="78ead-684">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-684">Boolean</span></span>|  
|<span data-ttu-id="78ead-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="78ead-685">TYPE</span></span>|<span data-ttu-id="78ead-686">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-686">Int32</span></span>|  
|<span data-ttu-id="78ead-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="78ead-687">FILL_FACTOR</span></span>|<span data-ttu-id="78ead-688">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-688">Int32</span></span>|  
|<span data-ttu-id="78ead-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="78ead-689">INITIAL_SIZE</span></span>|<span data-ttu-id="78ead-690">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-690">Int32</span></span>|  
|<span data-ttu-id="78ead-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="78ead-691">NULLS</span></span>|<span data-ttu-id="78ead-692">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-692">Int32</span></span>|  
|<span data-ttu-id="78ead-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="78ead-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="78ead-694">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-694">Boolean</span></span>|  
|<span data-ttu-id="78ead-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="78ead-695">AUTO_UPDATE</span></span>|<span data-ttu-id="78ead-696">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-696">Boolean</span></span>|  
|<span data-ttu-id="78ead-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="78ead-697">NULL_COLLATION</span></span>|<span data-ttu-id="78ead-698">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-698">Int32</span></span>|  
|<span data-ttu-id="78ead-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="78ead-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="78ead-700">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-700">Int64</span></span>|  
|<span data-ttu-id="78ead-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="78ead-701">COLUMN_NAME</span></span>|<span data-ttu-id="78ead-702">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-702">String</span></span>|  
|<span data-ttu-id="78ead-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="78ead-703">COLUMN_GUID</span></span>|<span data-ttu-id="78ead-704">Guid</span><span class="sxs-lookup"><span data-stu-id="78ead-704">Guid</span></span>|  
|<span data-ttu-id="78ead-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="78ead-705">COLUMN_PROPID</span></span>|<span data-ttu-id="78ead-706">Int64</span><span class="sxs-lookup"><span data-stu-id="78ead-706">Int64</span></span>|  
|<span data-ttu-id="78ead-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="78ead-707">COLLATION</span></span>|<span data-ttu-id="78ead-708">Int16</span><span class="sxs-lookup"><span data-stu-id="78ead-708">Int16</span></span>|  
|<span data-ttu-id="78ead-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="78ead-709">CARDINALITY</span></span>|<span data-ttu-id="78ead-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="78ead-710">Decimal</span></span>|  
|<span data-ttu-id="78ead-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="78ead-711">PAGES</span></span>|<span data-ttu-id="78ead-712">Int32</span><span class="sxs-lookup"><span data-stu-id="78ead-712">Int32</span></span>|  
|<span data-ttu-id="78ead-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="78ead-713">FILTER_CONDITION</span></span>|<span data-ttu-id="78ead-714">Строка</span><span class="sxs-lookup"><span data-stu-id="78ead-714">String</span></span>|  
|<span data-ttu-id="78ead-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="78ead-715">INTEGRATED</span></span>|<span data-ttu-id="78ead-716">Логическое</span><span class="sxs-lookup"><span data-stu-id="78ead-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78ead-717">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="78ead-717">See also</span></span>

- [<span data-ttu-id="78ead-718">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="78ead-718">ADO.NET Overview</span></span>](ado-net-overview.md)

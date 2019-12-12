---
title: sys.sysfiles (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysfiles
- sys.sysfiles_TSQL
- sys.sysfiles
- sysfiles_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysfiles system table
- sys.sysfiles compatibility view
ms.assetid: 3b47f38d-1cff-404d-89d3-9342c451c802
author: rothja
ms.author: jroth
ms.openlocfilehash: 2a3554e254be0623e36719fe76b2d811908a939d
ms.sourcegitcommit: b2464064c0566590e486a3aafae6d67ce2645cef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2019
ms.locfileid: "68053476"
---
# <a name="syssysfiles-transact-sql"></a>sys.sysfiles (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Содержит по одной строке для каждого файла базы данных.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**fileid**|**smallint**|Идентификационный номер файла, уникальный для каждой базы данных.|  
|**groupid**|**smallint**|Идентификационный номер файловой группы.|  
|**size**|**int**|Размер файла в страницах по 8 КБ.|  
|**maxsize**|**int**|Максимальный размер файла, в страницах по 8 КБ.<br /><br /> 0 = не возрастает.<br /><br /> -1 = размер файла может увеличиваться до полного заполнения диска.<br /><br /> 268435456 = файл журнала может увеличиваться до 2 ТБ.<br /><br /> Примечание. Базы данных, которые обновляются с размером файла журнала возвращают -1 для максимального размера файла журнала.|  
|**growth**|**int**|Предельный размер базы данных. Может быть либо число страниц, либо процент от размера файла, в зависимости от значения **состояние**.<br /><br /> 0 = не возрастает.|  
|**status**|**int**|Биты состояния **рост** значение в мегабайтах (МБ) или в килобайтах (КБ).<br /><br /> 0x2 = дисковый файл.<br /><br /> 0x40 = файл журнала.<br /><br /> 0x100000 = масштаб увеличения базы данных. Это значение определяет увеличение в процентах, а не в количестве страниц.|  
|**perf**|**int**|Зарезервировано.|  
|**name**|**sysname**|Логическое имя файла.|  
|**filename**|**nvarchar(260)**|Имя физического устройства. Включает полный путь к файлу.|  
  
## <a name="see-also"></a>См. также  
 [Сопоставление системных таблиц с системными представлениями &#40;Transact-SQL&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Представления совместимости (Transact-SQL)](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  

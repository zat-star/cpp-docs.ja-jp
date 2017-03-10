---
title: "検索と並べ替え | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- sorting data
- data [CRT], searching
- searching [C++], CRT search functions
- searching [C++]
ms.assetid: 15e984f0-e155-46f5-8542-51c458792f54
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 5ba605d61ddcf1ae6bd2adc24c41737536fa2ce9
ms.lasthandoff: 02/24/2017

---
# <a name="searching-and-sorting"></a>検索と並べ替え
検索と並べ替えには、次の関数を使用します。  
  
### <a name="searching-and-sorting-functions"></a>検索と並べ替えの関数  
  
|関数|検索または並べ替え|同等の .NET Framework 関数|  
|--------------|--------------------|-------------------------------|  
|[bsearch](../c-runtime-library/reference/bsearch.md)|バイナリ検索|[System::Collections::ArrayList::BinarySearch](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)|  
|[bsearch_s](../c-runtime-library/reference/bsearch-s.md)|より安全なバージョンの `bsearch`。|[System::Collections::ArrayList::BinarySearch](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)|  
|[_lfind](../c-runtime-library/reference/lfind.md)|指定された値の線形探索|[System::Collections::ArrayList::Contains](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)|  
|[_lfind_s](../c-runtime-library/reference/lfind-s.md)|より安全なバージョンの `_lfind`|[System::Collections::ArrayList::Contains](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)|  
|[_lsearch](../c-runtime-library/reference/lsearch.md)|指定された値の線形探索。見つからない場合は配列に追加されます|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[_lsearch_s](../c-runtime-library/reference/lsearch-s.md)|より安全なバージョンの `_lsearch`|該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。|  
|[qsort](../c-runtime-library/reference/qsort.md)|クイック並べ替え|[System::Collections::ArrayList::Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)|  
|[qsort_s](../c-runtime-library/reference/qsort-s.md)|より安全なバージョンの `qsort`|[System::Collections::ArrayList::Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)|  
  
## <a name="see-also"></a>関連項目  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)

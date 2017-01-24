---
title: "検索と並べ替え | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "データ [CRT], 検索"
  - "検索 [C++]"
  - "検索 [C++], CRT 検索関数"
  - "並べ替え (データの)"
ms.assetid: 15e984f0-e155-46f5-8542-51c458792f54
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 検索と並べ替え
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

検索および並べ替えるために次の関数を使用します。  
  
### 関数を検索し、並べ替えます  
  
|関数|検索または並べ替え|同等の .NET Framework 関数|  
|--------|---------------|---------------------------|  
|[bsearch](../c-runtime-library/reference/bsearch.md)|バイナリ サーチ|[\<caps:sentence id\="tgt8" sentenceid\="07fe7161f1b3ff07a50d0fdb13bc8ade" class\="tgtSentence"\>System::Collections::ArrayList::BinarySearch\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)|  
|[bsearch\_s](../c-runtime-library/reference/bsearch-s.md)|`bsearch`のセキュリティが強化されたバージョンです。|[\<caps:sentence id\="tgt10" sentenceid\="07fe7161f1b3ff07a50d0fdb13bc8ade" class\="tgtSentence"\>System::Collections::ArrayList::BinarySearch\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)|  
|[\_lfind](../c-runtime-library/reference/lfind.md)|指定された値のリニア サーチ|[\<caps:sentence id\="tgt13" sentenceid\="2b0a5c761626afecd7137a4eab4525f0" class\="tgtSentence"\>System::Collections::ArrayList::Contains\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)|  
|[\_lfind\_s](../Topic/_lfind_s.md)|`_lfind`のセキュリティを強化したバージョン|[\<caps:sentence id\="tgt15" sentenceid\="2b0a5c761626afecd7137a4eab4525f0" class\="tgtSentence"\>System::Collections::ArrayList::Contains\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)|  
|[\_lsearch](../c-runtime-library/reference/lsearch.md)|配置するときに追加される指定値のリニア サーチ、見つからない場合|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_lsearch\_s](../c-runtime-library/reference/lsearch-s.md)|`_lsearch`のセキュリティを強化したバージョン|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[qsort](../c-runtime-library/reference/qsort.md)|クイック ソート|[\<caps:sentence id\="tgt27" sentenceid\="f0305a177c6971f2c3c37537da538229" class\="tgtSentence"\>System::Collections::ArrayList::Sort\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)|  
|[qsort\_s](../c-runtime-library/reference/qsort-s.md)|`qsort`のセキュリティを強化したバージョン|[\<caps:sentence id\="tgt29" sentenceid\="f0305a177c6971f2c3c37537da538229" class\="tgtSentence"\>System::Collections::ArrayList::Sort\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)|  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
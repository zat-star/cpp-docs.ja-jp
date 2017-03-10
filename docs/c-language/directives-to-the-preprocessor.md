---
title: "プリプロセッサへのディレクティブ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.openlocfilehash: 0c3e8919083d3f5f3ab6345de0a2a6817b93205e
ms.lasthandoff: 02/24/2017

---
# <a name="directives-to-the-preprocessor"></a>プリプロセッサへのディレクティブ
"ディレクティブ" は、コンパイル前にプログラムのテキストに特定の操作を行うように C プリプロセッサに指示します。 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)の詳細については、「*プリプロセッサ リファレンス*」を参照してください。 `#define` プリプロセッサ ディレクティブの使用例を次に示します。  
  
```  
#define MAX 100  
```  
  
 このステートメントは、コンパイル前に `MAX` で `100` を置き換えるようコンパイラに指示します。 C コンパイラのプリプロセッサ ディレクティブは次のとおりです。  
  
|#define|#endif|#ifdef|#線|  
|--------------|-------------|-------------|------------|  
|`#elif`|`#error`|**#ifndef**|**#pragma**|  
|`#else`|`#if`|`#include`|`#undef`|  
  
## <a name="see-also"></a>関連項目  
 [ソース ファイルとソース プログラム](../c-language/source-files-and-source-programs.md)

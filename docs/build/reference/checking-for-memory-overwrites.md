---
title: "メモリ上書きのチェック | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メモリ, 上書き"
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# メモリ上書きのチェック
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヒープ操作関数の呼び出しでアクセス違反が発生した場合は、プログラムがヒープを壊している可能性があります。  この状況に共通する現象は、次のとおりです。  
  
```  
Access Violation in _searchseg  
```  
  
 [\_heapchk](../../c-runtime-library/reference/heapchk.md) 関数は、デバッグ ビルドとリリース ビルドの両方 \(Windows NT のみ\) で、ランタイム ライブラリ ヒープの整合性の検証に使用できます。  `AfxCheckMemory` 関数とほぼ同じで方法で `_heapchk` を使用し、ヒープの上書きを特定できます。たとえば、次のように記述します。  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 この関数でエラーが発生する場合は、ヒープが壊れた場所を特定する必要があります。  
  
## 参照  
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)
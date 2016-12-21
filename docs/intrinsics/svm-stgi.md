---
title: "__svm_stgi | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_stgi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_stgi 組み込み"
  - "STGI 命令"
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __svm_stgi
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 グローバルな割り込みフラグを設定します。  
  
## 構文  
  
```  
void __svm_stgi(void);  
```  
  
## 解説  
 `__svm_stgi` の関数は `STGI` のマシン語命令と同じです。  グローバルな割り込みフラグはマイクロプロセッサになるかまたは I\/O 完了ハードウェアからの警告およびデバッグの例外などのイベントによる割り込みを無視し延期するかどうかを処理します。  
  
 この関数はゲスト オペレーティング システムとアプリケーションのホスト仮想マシンのモニターの相互作用をサポートします。  詳細については文書の検索「 AMD64 アーキテクチャのプログラマの Manual Volume 2: システム」24593 番目のプログラミングのリビジョン 3.11 [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) を返します。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__svm_stgi`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## Microsoft 固有の仕様→を終了  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_clgi](../intrinsics/svm-clgi.md)
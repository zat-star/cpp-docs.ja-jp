---
title: "__svm_clgi | Microsoft Docs"
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
  - "__svm_clgi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLGI 命令"
  - "__svm_clgi 組み込み"
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __svm_clgi
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 グローバルな割り込みフラグをクリアします。  
  
## 構文  
  
```  
void __svm_clgi( void );  
```  
  
## 解説  
 `__svm_clgi` の関数は `CLGI` のマシン語命令と同じです。  グローバルな割り込みフラグはマイクロプロセッサになるかまたは I\/O 完了ハードウェアからの警告およびデバッグの例外などのイベントによる割り込みを無視し延期するかどうかを処理します。  
  
 この関数はゲスト オペレーティング システムとアプリケーションのホスト仮想マシンのモニターの相互作用をサポートします。  詳細については文書の検索「 AMD64 アーキテクチャのプログラマの Manual Volume 2: システム」24593 番目のプログラミングのリビジョン 3.11 [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) を返します。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__svm_clgi`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_stgi](../intrinsics/svm-stgi.md)
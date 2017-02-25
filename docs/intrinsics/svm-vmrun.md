---
title: "__svm_vmrun | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_vmrun"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_vmrun 組み込み"
  - "VMRUN 命令"
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_vmrun
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 指定された仮想マシンのコントロール ブロックに対応する仮想マシンのゲスト コードの実行を開始 \(VMCB\) します。  
  
## 構文  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### パラメーター  
  
|パラメーター|Description|  
|------------|-----------------|  
|\[入力\] `VmcbPhysicalAddress`|VMCB の物理アドレス。|  
  
## 解説  
 `__svm_vmrun` の関数は VMCB で仮想マシンのゲスト コードを実行するには最小限の情報を使用します。  詳細については複雑な割り込みを処理したり他のゲストに切り替える必要がある場合 [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md) または [\_\_svm\_vmload](../intrinsics/svm-vmload.md) の関数を使用します。  
  
 `__svm_vmrun` の関数は `VMRUN` のマシン語命令と同じです。  この関数はゲスト オペレーティング システムとアプリケーションのホスト仮想マシンのモニターの相互作用をサポートします。  詳細については" " の 「 AMD64 アーキテクチャのプログラマの Manual Volume 2: 探します。24593 番目のシステム サイトのリビジョン 3.11 以降ではプログラミング」 [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746)。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__svm_vmrun`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md)   
 [\_\_svm\_vmload](../intrinsics/svm-vmload.md)
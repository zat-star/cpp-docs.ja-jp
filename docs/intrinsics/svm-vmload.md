---
title: "__svm_vmload | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_vmload"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_vmload 組み込み"
  - "VMLOAD 命令"
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_vmload
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 指定された仮想マシンのコントロール ブロック状態のプロセッサのサブセットを読み込みます \(VMCB\)。  
  
## 構文  
  
```  
void __svm_vmload(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### パラメーター  
  
|パラメーター|Description|  
|------------|-----------------|  
|\[入力\] `VmcbPhysicalAddress`|VMCB の物理アドレス。|  
  
## 解説  
 `__svm_vmload` の関数は `VMLOAD` のマシン語命令と同じです。  この関数はゲスト オペレーティング システムとアプリケーションのホスト仮想マシンのモニターの相互作用をサポートします。  詳細については文書の検索「 AMD64 アーキテクチャのプログラマの Manual Volume 2: システム」24593 番目のプログラミングのリビジョン 3.11 [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) を返します。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__svm_vmload`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_vmrun](../intrinsics/svm-vmrun.md)   
 [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md)
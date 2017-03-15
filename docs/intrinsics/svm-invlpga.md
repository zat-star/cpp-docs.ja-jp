---
title: "__svm_invlpga | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_invlpga"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_invlpga 組み込み"
  - "INVLPGA 命令"
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_invlpga
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 翻訳コンピューターの外観 Buffer\) のアドレス マップのエントリを無効にします。  パラメーターが無効になるようにページのアドレスと仮想アドレス空間の識別子を指定します。  
  
## 構文  
  
```  
void __svm_invlpga(  
     void *Va,  
     int ASID);  
```  
  
#### パラメーター  
  
|パラメーター|Description|  
|------------|-----------------|  
|\[入力\] `Va`|無効にするページの仮想アドレス。|  
|\[入力\] `ASID`|無効にするページの \(ASID\) アドレス空間識別子。|  
  
## 解説  
 `__svm_invlpga` の関数は `INVLPGA` のマシン語命令と同じです。  この関数はゲスト オペレーティング システムとアプリケーションのホスト仮想マシンのモニターの相互作用をサポートします。  詳細については文書の検索「 AMD64 アーキテクチャのプログラマの Manual Volume 2: システム」24593 番目のプログラミングのリビジョン 3.11 [AMD corporation](http://go.microsoft.com/fwlink/?LinkId=23746) を返します。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__svm_invlpga`|x86[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)
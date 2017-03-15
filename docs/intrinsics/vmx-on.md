---
title: "__vmx_on | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_on"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMXON 命令"
  - "__vmx_on 組み込み"
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __vmx_on
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 プロセッサの仮想マシンの拡張機能 \(\) VMX 操作をアクティブにします。  
  
## 構文  
  
```  
unsigned char __vmx_on(  
   unsigned __int64 *VmsSupportPhysicalAddress  
);  
```  
  
#### パラメーター  
 \[入力\] `VmsSupportPhysicalAddress`  
 仮想マシンの制御構造を指す 64 ビットの物理アドレスへのポインター \(VMCS\)。  
  
## 戻り値  
  
|値|説明|  
|-------|--------|  
|0|操作が成功しました。|  
|1|操作は現在 VMCS の `VM-instruction error field` に展開状態が利用可能に失敗しました。|  
|2|操作は状態が利用可能なしに失敗しました。|  
  
## 解説  
 `__vmx_on` の関数は `VMXON` のマシン語命令に対応します。  この関数はゲスト オペレーティング システムとアプリケーションのホスト仮想マシンのモニターの相互作用をサポートします。  詳細については文書の検索「 IA\-32 Intel アーキテクチャの Intel 仮想化テクノロジ固有」サイトのパブリック文書番号 C97063\-002 [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127)。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__vmx_on`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)
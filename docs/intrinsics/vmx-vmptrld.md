---
title: "__vmx_vmptrld | Microsoft Docs"
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
  - "__vmx_vmptrld"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmptrld 組み込み"
  - "VMPTRLD 命令"
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmptrld
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 指定されたアドレスから現在の仮想マシンの制御構造 \(VMCS\) へのポインターを読み込みます。  
  
## 構文  
  
```  
int __vmx_vmptrld(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### パラメーター  
 \[入力\] \*`VmcsPhysicalAddress`  
 VMCS のポインターが格納されているアドレス。  
  
## 戻り値  
 0  
 操作が成功しました。  
  
 1  
 操作は現在 VMCS の `VM-instruction error field` に展開状態が利用可能に失敗しました。  
  
 2  
 操作は状態が利用可能なしに失敗しました。  
  
## 解説  
 VMCS のポインターは64 ビットの物理アドレスです。  
  
 `__vmx_vmptrld` の関数は `VMPTRLD` のマシン語命令と同じです。  この関数はゲスト オペレーティング システムとアプリケーションのホスト仮想マシンのモニターの相互作用をサポートします。  詳細については文書の検索「 IA\-32 Intel アーキテクチャの Intel 仮想化テクノロジ固有」サイトのパブリック文書番号 C97063\-002 [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127)。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__vmx_vmptrld`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmptrst](../intrinsics/vmx-vmptrst.md)
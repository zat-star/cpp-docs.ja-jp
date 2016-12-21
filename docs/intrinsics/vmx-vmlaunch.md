---
title: "__vmx_vmlaunch | Microsoft Docs"
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
  - "__vmx_vmlaunch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMLAUNCH 命令"
  - "__vmx_vmlaunch 組み込み"
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmlaunch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 現在の仮想マシンの制御構造を使用してルート VMX 操作の状態に呼び出し元のアプリケーション \(VM\) が格納されます \(VMCS\)。  
  
## 構文  
  
```  
unsigned char __vmx_vmlaunch(  
   void);  
```  
  
## 戻り値  
  
|値|説明|  
|-------|--------|  
|0|操作が成功しました。|  
|1|操作は現在 VMCS の `VM-instruction error field` に展開状態が利用可能に失敗しました。|  
|2|操作は状態が利用可能なしに失敗しました。|  
  
## 解説  
 アプリケーションは [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) または [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) の関数を使用してVM 送信操作を実行できます。  [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) の関数は `Clear` の状態がである [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) の関数は `Launched` の状態がである VMCS でのみ使用できます VMCS でのみ使用します。  その結果`Clear` に VMCS の開始状態を設定するに [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md) の関数を使用し1 番目のトポロジ用に [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) の関数を VM Enter 操作に使用する場合それ以降の [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) の関数は演算に VM なります。  
  
 `__vmx_vmlaunch` の関数は `VMLAUNCH` のマシン語命令と同じです。  この関数はゲスト オペレーティング システムとアプリケーションのホスト仮想マシンのモニターの相互作用をサポートします。  詳細については文書の検索「 IA\-32 Intel アーキテクチャの Intel 仮想化テクノロジ固有」サイトのパブリック文書番号 C97063\-002 [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127)。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__vmx_vmlaunch`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)   
 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)
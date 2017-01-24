---
title: "__vmx_vmclear | Microsoft Docs"
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
  - "__vmx_vmclear"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMCLEAR 命令"
  - "__vmx_vmclear 組み込み"
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmclear
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 指定された仮想マシンの制御構造体を初期化 \(VMCS\) して `Clear`スタートアップ状態を設定します。  
  
## 構文  
  
```  
unsigned char __vmx_vmclear(  
   unsigned __int64 *VmcsPhysicalAddress  
);  
```  
  
#### パラメーター  
  
|パラメーター|Description|  
|------------|-----------------|  
|\[入力\] `VmcsPhysicalAddress`|削除する VMCS の物理アドレスを含む 64 ビットのメモリ位置へのポインター。|  
  
## 戻り値  
  
|値|説明|  
|-------|--------|  
|0|操作が成功しました。|  
|1|操作は現在 VMCS の `VM-instruction error field` に展開状態が利用可能に失敗しました。|  
|2|操作は状態が利用可能なしに失敗しました。|  
  
## 解説  
 アプリケーションは [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) または [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) の関数を使用してVM 送信操作を実行できます。  [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) の関数は `Clear` の状態がである [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) の関数は `Launched` の状態がである VMCS でのみ使用できます VMCS でのみ使用します。  その結果`Clear` に VMCS の開始状態を設定するに [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md) の関数を使用します。  1 番目のトポロジ用に [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) の関数を VM Enter 操作に使用する場合それ以降の [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) の関数は演算に VM なります。  
  
 `__vmx_vmclear` の関数は `VMCLEAR` のマシン語命令と同じです。  この関数はゲスト オペレーティング システムとアプリケーションのホスト仮想マシンのモニターの相互作用をサポートします。  詳細については文書の検索「 IA\-32 Intel アーキテクチャの Intel 仮想化テクノロジ固有」サイトのパブリック文書番号 C97063\-002 [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127)。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__vmx_vmclear`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)
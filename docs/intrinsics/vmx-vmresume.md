---
title: "__vmx_vmresume | Microsoft Docs"
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
  - "__vmx_vmresume"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmresume 組み込み"
  - "VMRESUME 命令"
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmresume
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様**  
  
 現在の仮想マシンの制御構造 \(VMCS\) を使用することで、VMX の非ルート操作を再開します。  
  
## 構文  
  
```  
unsigned char __vmx_vmresume(  
   void);  
```  
  
## 戻り値  
  
|値|説明|  
|-------|--------|  
|0|操作が成功しました。|  
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|  
|2|有効な状態がないため操作は失敗しました。|  
  
## 解説  
 アプリケーションは、[\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) 関数または `__vmx_vmresume` 関数を使用して VM 入力操作を実行できます。`__vmx_vmlaunch` 関数は起動状態が `Clear` の VMCS でのみ使用できます。`__vmx_vmresume` 関数は起動状態が `Launched` の VMCS でのみ使用できます。 そのため、[\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md) 関数を使用して VMCS の起動状態を `Clear` に設定し、その後で、最初の VM 入力操作に `__vmx_vmlaunch` 関数を使用し、後続の VM 入力操作に `__vmx_vmresume` 関数を使用します。  
  
 `__vmx_vmresume` 関数は `VMRESUME` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、[Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) のサイトで、PDF ドキュメント「IA\-32 Intel アーキテクチャ向け Intel 仮想化テクノロジ仕様」\(ドキュメント番号 C97063\-002\) を参照してください。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__vmx_vmresume`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)
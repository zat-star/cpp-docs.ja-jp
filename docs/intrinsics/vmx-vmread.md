---
title: "__vmx_vmread | Microsoft Docs"
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
  - "__vmx_vmread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMREAD 命令"
  - "__vmx_vmread 組み込み"
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 現在の仮想マシンの制御構造と場所から \(VMCS\) 指定されたフィールドに指定された場所に置きます読み取ります。  
  
## 構文  
  
```  
unsigned char __vmx_vmread(  
   size_t Field,  
   size_t *FieldValue  
);  
```  
  
#### パラメーター  
  
|パラメーター|Description|  
|------------|-----------------|  
|\[入力\] `Field`|読み取るフィールドの VMCS。|  
|\[入力\] `FieldValue`|値を `Field` のパラメーターで指定された VMCS のフィールドから格納する場所へのポインターはいます。|  
  
## 戻り値  
  
|値|説明|  
|-------|--------|  
|0|操作が成功しました。|  
|1|操作は現在 VMCS の `VM-instruction error field` に展開状態が利用可能に失敗しました。|  
|2|操作は状態が利用可能なしに失敗しました。|  
  
## 解説  
 `__vmx_vmread` の関数は `VMREAD` のマシン語命令と同じです。  `Field` のパラメーターの値はのドキュメントに記述されているエンコードしたフィールドのインデックスです。  詳細については文書の検索は「 IA\-32 Intel アーキテクチャの Intel 仮想化テクノロジ固有のパブリック」" C97063\-002 番号[Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) サイトでそのドキュメントの付録 C を参照します。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__vmx_vmread`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmwrite](../intrinsics/vmx-vmwrite.md)
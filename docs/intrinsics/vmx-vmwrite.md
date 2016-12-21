---
title: "__vmx_vmwrite | Microsoft Docs"
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
  - "__vmx_vmwrite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmwrite 組み込み"
  - "VMWRITE 命令"
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmwrite
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 現在の仮想マシンの制御構造で指定されたフィールドに指定された値を書き込みます \(VMCS\)。  
  
## 構文  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### パラメーター  
  
|パラメーター|Description|  
|------------|-----------------|  
|\[入力\] `Field`|書き込む VMCS のフィールド。|  
|\[入力\] `FieldValue`|VMCS のフィールドに書き込む値。|  
  
## 戻り値  
 0  
 操作が成功しました。  
  
 1  
 操作は現在 VMCS の `VM-instruction error field` に展開状態が利用可能に失敗しました。  
  
 2  
 操作は状態が利用可能なしに失敗しました。  
  
## 解説  
 `__vmx_vmwrite` の関数は `VMWRITE` のマシン語命令と同じです。  `Field` のパラメーターの値はのドキュメントに記述されているエンコードしたフィールドのインデックスです。  詳細については文書の検索「 IA\-32 Intel アーキテクチャの Intel 仮想化テクノロジ固有のパブリック」" C97063\-002 番号はサイト [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) とそのドキュメントの付録 C を参照します。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|  
|----------|-------------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmread](../intrinsics/vmx-vmread.md)
---
title: "CMemoryState 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMemoryState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMemoryState 構造体"
  - "検出 (メモリ リークを)"
  - "メモリ リーク, 検出"
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CMemoryState 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラムのメモリ リークを検出するための便利な方法を提供します。  
  
## 構文  
  
```  
struct CMemoryState  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMemoryState::CMemoryState](../Topic/CMemoryState::CMemoryState.md)|クラスと同様の構造をそのコントロールのメモリのチェックポイント構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMemoryState::Checkpoint](../Topic/CMemoryState::Checkpoint.md)|現在のメモリ状態のスナップショット \(チェックポイント\) を取得します。|  
|[CMemoryState::Difference](../Topic/CMemoryState::Difference.md)|型 `CMemoryState`の 2 種類のオブジェクト間の相違点を計算します。|  
|[CMemoryState::DumpAllObjectsSince](../Topic/CMemoryState::DumpAllObjectsSince.md)|前のチェックポイント以降のすべての現在割り当てられているオブジェクトの概要をダンプします。|  
|[CMemoryState::DumpStatistics](../Topic/CMemoryState::DumpStatistics.md)|`CMemoryState` のオブジェクトの印刷のメモリ割り当ての統計情報。|  
  
## 解説  
 `CMemoryState` は構造体で、基本クラスはありません。  
  
 オブジェクトのメモリをヒープに割り当てられますが、それがいつ不要な場合に解放されない「と」メモリ リークが発生します。  このようなメモリ リークは、メモリ不足のあるエラーの原因となる可能性があります。  プログラムのメモリを割り当ておよび解放する方法はいくつかあります:  
  
-   ランタイム ライブラリの関数の `malloc`\/**free** のファミリを使用します。  
  
-   Windows API のメモリ管理関数、**LocalAlloc**\/**LocalFree** と **GlobalAlloc**\/**GlobalFree**を使用します。  
  
-   C\+\+ **new** と **\[削除\]** の演算子を使用します。  
  
 **new** の演算子を使用して割り当てられたメモリが **\[削除\]**を使用して解放されていない場合 `CMemoryState` の診断のヘルプのみ発生するメモリ リークを検出します。  管理機能の他の 2 種類のグループは非 C\+\+ プログラム用であり、**new** とそれらと同じプログラムの **\[削除\]** 両方を使用することはお勧めしません。  メモリ割り当てのファイルと行番号追跡を必要とするときに追加のマクロ、`DEBUG_NEW`は、**new** の演算子を置き換えるために用意されています。  `DEBUG_NEW` は、通常、**new** 演算子を使用する場合にも使用されます。  
  
 他の診断と同様に、`CMemoryState` の診断は、プログラムのデバッグ バージョンでのみ利用できます。  デバッグ バージョンは、定義された **デバッグ\(\_D\)** の定数が必要です。  
  
 疑えば、プログラムでメモリ リークが、`Checkpoint`**\[差分\]**と、プログラム実行の 2 種類の時点でのメモリ状態 \(割り当てられたオブジェクト\) の違いを検出するために `DumpStatistics` 関数を使用しています。  この情報は、関数によって割り当てられたすべてのオブジェクトをクリーンアップしているかどうかの判断に便利です。  
  
 割り当ておよび解放のバランスがどこで発生したかだけを知ることが十分な情報を提供するため、`Checkpoint`前の呼び出しで割り当てられたすべてのオブジェクトをダンプするために `DumpAllObjectsSince` 関数を使用できます。  このダンプは、代入の順序、オブジェクト \(割り当てに `DEBUG_NEW` を使用している場合\)、割り当てられたと、派生オブジェクトのアドレスとサイズを示しますソース ファイルと行。  `DumpAllObjectsSince` は、各状態に関する情報を提供するオブジェクトの `Dump` 関数を呼び出します。  
  
 `CMemoryState` および他の診断を使用する方法の詳細については、[MFC アプリケーションのデバッグ](../Topic/MFC%20Debugging%20Techniques.md)を参照してください。  
  
> [!NOTE]
>  メンバー関数の型 `CMemoryState` および呼び出しのオブジェクトの宣言は `#if defined(_DEBUG)/#endif`ディレクティブでかっこと入力します。  これは、メモリ診断を、プログラムのデバッグ ビルドにのみ含まれています。  
  
## 継承階層  
 `CMemoryState`  
  
## 必要条件  
 **ヘッダー:** afx.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)
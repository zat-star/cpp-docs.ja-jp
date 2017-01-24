---
title: "2.7.1 threadprivate Directive | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 08e0b70f-5359-4607-b0ca-38c2d570d7b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.1 threadprivate Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`threadprivate` のディレクティブはスレッドが  *リストの*  プライベート  *変数*  で指定された名前付き範囲ファイル名前空間スコープまたは静的なブロック スコープの変数を作成します。   *可変リストは*  不完全な型ではない変数のコンマ区切りのリストです。  `threadprivate` のディレクティブの構文は次のとおりです :  
  
```  
#pragma omp threadprivate(variable-list) new-line  
```  
  
 `threadprivate` 変数の各コピーが同時にそのコピーが最初に参照される前にマスター コピーがプログラムのシリアル実行で初期化されるため\)プログラムの未指定の位置に通常の方法 \(つまり初期化します。  動作が指定されていないオブジェクトが `threadprivate` 変数の明示的な初期化子内で参照されオブジェクトの値が変数のコピーが最初に参照される前に変更することに注意してください。  
  
 すべてのプライベート変数と同様にスレッドが別のスレッドの `threadprivate` オブジェクトのコピーを参照する必要があります。  プログラムのシリアル領域とマスター領域では参照はマスター スレッド オブジェクトのコピーにあります。  
  
 最初の並列領域を実行すると`threadprivate` オブジェクトのデータを永続化するために動的スレッド機能が無効になっている場合にのみスレッドの数がすべての並列領域では変更されずに残っている場合は限りません。  
  
 `threadprivate` のディレクティブに制限 : は次のとおりです。  
  
-   ファイル スコープまたは名前空間スコープの変数の `threadprivate` のディレクティブは定義または宣言の外側に表示される構文によってリストの変数のいずれかへのすべての参照を付ける必要があります。  
  
-   ファイルまたは名前空間スコープ `threadprivate` のディレクティブの  *可変リスト*  の各変数は構文的にはディレクティブの前にある名前空間スコープまたはファイルに変数を宣言する必要があります。  
  
-   静的なブロック スコープの変数の `threadprivate` のディレクティブは変数のスコープ内ではなく入れ子になったスコープで使用する必要があります。  ディレクティブは構文的にリストの変数のいずれかへのすべての参照を付ける必要があります。  
  
-   ブロック スコープの `threadprivate` のディレクティブの  *可変リスト*  の各変数は構文的にはディレクティブの前にある同じスコープの変数を指定する必要があります。  変数宣言では静的なストレージ クラス指定子を使用する必要があります。  
  
-   変数が 1 台の翻訳単位の `threadprivate` のディレクティブに指定されている宣言された変換単位の `threadprivate` のディレクティブで指定する必要があります。  
  
-   `threadprivate` の変数は `copyin``copyprivate``schedule``num_threads`または **If** の句を除く任意の句に含める必要があります。  
  
-   `threadprivate` 変数のアドレスを指す定数ではありません。  
  
-   `threadprivate` の変数は不完全な型または参照型はありません。  
  
-   非 POD のクラス型で `threadprivate` の変数は明示的な初期化子で宣言されているアクセスでき明確なコピー コンストラクターが必要です。  
  
 初期化子に表示される変数を変更すると未定義の動作を引き起こす可能性のある補助オブジェクトとコピー コンストラクターを使用してこの問題を回避する方法を説明する方法を次の例に示します。  
  
```  
int x = 1;  
T a(x);  
const T b_aux(x); /* Capture value of x = 1 */  
T b(b_aux);  
#pragma omp threadprivate(a, b)  
  
void f(int n) {  
   x++;  
   #pragma omp parallel for  
   /* In each thread:  
   * Object a is constructed from x (with value 1 or 2?)  
   * Object b is copy-constructed from b_aux  
   */  
   for (int i=0; i<n; i++) {  
      g(a, b); /* Value of a is unspecified. */  
   }  
}  
```  
  
## cref:  
  
-   動的なスレッドはページの 39 [セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) が表示されます。  
  
-   `OMP_DYNAMIC` の環境変数はページの 49 [セクション 4.3](../../parallel/openmp/4-3-omp-dynamic.md) が表示されます。
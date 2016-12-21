---
title: "2.7.2.6 reduction | Microsoft Docs"
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
ms.assetid: e7630a15-2978-4dbe-a29b-3a46371a0151
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.6 reduction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この句は操作と演算子の一覧に表示される  *変数*  はスカラー変数の低減を実行します。  `reduction` 句の構文は次のとおりです。:  
  
```  
  
reduction(  
op  
:  
variable-list  
)  
  
```  
  
 縮小は次の 1 種類のステートメントに通常指定されています :  
  
```  
  
        x     =  x     op     expr  
x     binop=  expr  
x     =  expr     op     x            (except for subtraction)  
x++  
++x  
x--  
--x  
```  
  
 それぞれの文字について以下に説明します。  
  
 *x*  
 `list` で指定されたリダクション変数の 1 つが。  
  
 *可変リスト。*  
 スカラー リダクション変数のコンマ区切りのリスト。  
  
 *expr*  
 *x. を*  参照しないスカラー型の式です *。*  
  
 `op`  
 オーバーロードされた演算子はない 1 個の \*\+\- ^ &#124; または &#124;&#124;。  
  
 `binop`  
 オーバーロードされた演算子はない 1 個の \*\+\- または ^ &#124;。  
  
 次の例の句は `reduction` です :  
  
```  
#pragma omp parallel for reduction(+: a, y) reduction(||: am)  
for (i=0; i<n; i++) {  
   a += b[i];  
   y = sum(y, c[i]);  
   am = am || b[i] == c[i];  
}  
```  
  
 例に示すように演算子は関数呼び出しの中で非表示になる場合があります。  演算子が `reduction` 句の一致で縮小操作を指定したユーザーは注意が必要です。  
  
 の右オペランドは &#124;&#124; 演算子はこの例に副作用がない許可されていますが慎重に行う必要があります。  ここでは順次ループの実行時に実行されないことが保証されます。副作用は並列実行中に発生することがあります。  この違いはイテレーションの実行順序は予測できないことがあります。  
  
 リダクションのように演算子がコンパイラによって使用されるすべてのプライベート変数の初期値を決定し終了の演算子を確認するために使用されます。  演算子を明示的に指定するとリダクションのステートメントが構文構造体の範囲外になるようにします。  `reduction` の句のディレクティブで指定した変数はそのディレクティブの最大で 1 `reduction` の二つの句で表示されることがあります。  
  
 *可変リスト*  の各変数のプライベート コピーが `private` の句が使用されるようにスレッドごとに 1 回作成されます。  プライベート コピーが演算子によって初期化されます \(次の表を参照してください。  
  
 指定された演算子を使用してプライベート コピーの最終値と元の値を組み合わせた結果を反映するように `reduction` 句で指定した領域のエッジに元のオブジェクトが更新されます。  リダクション演算子はすべて連想 \(を除く\) 減算されコンパイラは自由に最終値の計算がある場合は再度する場合があります。  \(最終値の差を作成するにはリダクションの部分的な結果が追加されます\)。  
  
 元のオブジェクトの値は最初のスレッドに含まれる句に到達しリダクションの計算が完了するまでそのままと不確定になります。  通常計算は構造体の最後に完了しています ; ただし`reduction` の句が `nowait` も適用されている構造体で使用すると元のオブジェクトの値はすべてのスレッドが完了した `reduction` 句であることを確認するためにバリアの同期が呼び出されるまで実行されません。  
  
 次の表は有効であると標準の初期値を示す演算子。  実際の初期値は減少変数のデータ型と一致しています。  
  
|\[演算子\]|初期化|  
|-------------|---------|  
|\+|0|  
|\*|1|  
|\-|0|  
|&|~0|  
|&#124;|0|  
|^|0|  
|&&|1|  
|&#124;&#124;|0|  
  
 `reduction` の句に制限 : は次のとおりです。  
  
-   `reduction` の句の変数の型にはリダクション演算子に対して有効である必要がありますがポインター型と参照型では使用できません。  
  
-   `reduction` の句で指定された変数は修飾される  **定数**  でない場合があります。  
  
-   並列領域内でプライベートにするか **並列**  のディレクティブの `reduction` の句に表示される変数はparallel コンストラクトにバインドする共有作業のディレクティブで `reduction` の句で指定することはできません。  
  
    ```  
    #pragma omp parallel private(y)  
    { /* ERROR - private variable y cannot be specified  
                 in a reduction clause */  
       #pragma omp for reduction(+: y)  
       for (i=0; i<n; i++)  
          y += b[i];  
    }  
  
    /* ERROR - variable x cannot be specified in both  
               a shared and a reduction clause */  
    #pragma omp parallel for shared(x) reduction(+: x)  
    ```
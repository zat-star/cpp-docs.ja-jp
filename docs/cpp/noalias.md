---
title: "noalias | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noalias"
  - "noalias_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec キーワード [C++], noalias"
  - "noalias __declspec キーワード"
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# noalias
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `noalias` は関数呼び出しが表示されると、グローバル状態変更せず、参照されず、を変更しないポインター パラメーター \(第 1 レベルの間接指定\) によって `directly` が指すメモリしかを意味します。  
  
 関数が `noalias` として注釈が指定されている場合、オプティマイザーはパラメーター自体に加えてポインター パラメーターの第 1 レベルの間接指定のみが関数内で参照または変更されると仮定します。  表示されるグローバル状態は、コンパイルのスコープ外では、アドレスは取られません定義または参照されていないすべてのデータの設定です。  コンパイル スコープは、すべてのソース ファイル \([\/LTCG \(リンク時のコード生成\)](../build/reference/ltcg-link-time-code-generation.md) のビルド\) または 1 つのソース ファイル \(**\/LTCG** の非ビルド\) です。  
  
## 使用例  
 `__declspec(restrict)` および `__declspec(noalias)` を使用したサンプル コードを次に示します。  通常、CRT ヘッダーは適切に装飾されているので、`malloc` から返されるメモリは `restrict` および `noalias` です。  
  
 ただしこの例では、`mempool` ポインターおよび `memptr`  ポインターはグローバルであるため、コンパイラではメモリにエイリアスが適用されることを確認できません。  `__declspec(restrict)` でポインターを返す関数を装飾することによって、戻り値で参照されるメモリがエイリアス化されていないことをコンパイラに指示します。  
  
 `__declspec(noalias)` によりメモリにアクセスするこの例の関数を装飾して、この関数がパラメーター リストでポインターを経由する場合を除いてグローバル状態と干渉しないことをコンパイラに指示します。  
  
```  
// declspec_noalias.c   
#include <stdio.h>  
#include <stdlib.h>  
  
#define M 800  
#define N 600  
#define P 700  
  
float * mempool, * memptr;  
  
__declspec(restrict) float * ma(int size)  
{  
    float * retval;  
    retval = memptr;  
    memptr += size;  
    return retval;  
}  
  
__declspec(restrict) float * init(int m, int n)  
{  
    float * a;  
    int i, j;  
    int k=1;  
  
    a = ma(m * n);  
    if (!a) exit(1);  
    for (i=0; i<m; i++)  
        for (j=0; j<n; j++)  
            a[i*n+j] = 0.1/k++;  
    return a;  
}  
  
__declspec(noalias) void multiply(float * a, float * b, float * c)  
{  
    int i, j, k;  
  
    for (j=0; j<P; j++)  
        for (i=0; i<M; i++)  
            for (k=0; k<N; k++)  
                c[i * P + j] =   
                          a[i * N + k] *   
                          b[k * P + j];  
}  
  
int main()  
{  
    float * a, * b, * c;  
  
    mempool = (float *) malloc(sizeof(float) * (M*N + N*P + M*P));  
  
    if (!mempool)   
    {  
        puts("ERROR: Malloc returned null");  
        exit(1);  
    }  
  
    memptr = mempool;  
    a = init(M, N);  
    b = init(N, P);  
    c = init(M, P);  
  
    multiply(a, b, c);  
}  
```  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)
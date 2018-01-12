---
title: "noalias |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noalias_cpp
dev_langs: C++
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92e96ce931ea5bc44e03a5803865daa66f960e92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="noalias"></a>noalias

**Microsoft 固有の仕様**

`noalias`関数呼び出しの変更または表示されるグローバル状態の参照はないことを意味が指すメモリのみを変更し、*直接*ポインター パラメーター (第 1 レベルの間接指定)。

関数が `noalias` として注釈が指定されている場合、オプティマイザーはパラメーター自体に加えてポインター パラメーターの第 1 レベルの間接指定のみが関数内で参照または変更されると仮定します。 表示されるグローバル状態は、コンパイルのスコープ外では、アドレスは取られません定義または参照されていないすべてのデータの設定です。 コンパイルのスコープは、すべてのソース ファイル ([/LTCG (リンク時コード生成)](../build/reference/ltcg-link-time-code-generation.md)ビルド) または 1 つのソース ファイル (非**/LTCG**ビルド)。

## <a name="example"></a>例

`__declspec(restrict)` および `__declspec(noalias)` を使用したサンプル コードを次に示します。 通常から返されるメモリ`malloc`は`restrict`CRT ヘッダーが適切に装飾されているためです。

ただし、この例では、ポインターでは、`mempool`と`memptr`は、コンパイラは、メモリがエイリアスの対象ができないことを保証するを持たないために、グローバルです。 `__declspec(restrict)` でポインターを返す関数を装飾することによって、戻り値で参照されるメモリがエイリアス化されていないことをコンパイラに指示します。

`__declspec(noalias)` によりメモリにアクセスするこの例の関数を装飾して、この関数がパラメーター リストでポインターを経由する場合を除いてグローバル状態と干渉しないことをコンパイラに指示します。

```C
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

## <a name="see-also"></a>参照

[__declspec](../cpp/declspec.md)  
[キーワード](../cpp/keywords-cpp.md)
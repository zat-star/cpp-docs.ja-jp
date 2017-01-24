---
title: "2.6.4 atomic コンストラクト | Microsoft Docs"
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
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.4 atomic コンストラクト
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

 `atomic` ディレクティブは、特定のメモリ位置に複数の可能性に公開するのではなく、アトミックに反映されることにより、同時スレッドを作成します。 構文、 `atomic` ディレクティブは、次のようにします。  
  
```  
#pragma omp atomic new-lineexpression-stmt  
```  
  
 式ステートメントは、次の形式のいずれかが必要です。  
  
 *x binop*= *expr*  
  
 x++  
  
 ++x  
  
 x--  
  
 --x  
  
 上記の式では。  
  
-   *x* スカラー型の左辺値式を指定します。  
  
-   *expr* がスカラー型の式、によって指定されたオブジェクトを参照しない *x*です。  
  
-   `binop` オーバー ロードされた演算子ではなくの 1 つ +、*、-、/、&、^、&#124;、<\<、または >> です。  
  
 実装定義されているかどうか、実装をすべて置き換えます `atomic` ディレクティブを **重要な** が同じ一意であるディレクティブ *名前*, 、 `atomic` ディレクティブことが許可される最適化の向上します。 多くの場合、ハードウェアの手順については、最小限のオーバーヘッドでアトミックな更新プログラムを実行することができます。  
  
 負荷とによって指定されたオブジェクトのストアのみ *x* がアトミック; の評価 *expr* アトミックではないです。 競合状態を避けるためには、並列の場所のすべての更新プログラムで保護する必要があります、 `atomic` ディレクティブは、競合状態のフリーであることがわかっているものを除く。  
  
 制限を `atomic` ディレクティブが次に示します。  
  
-   プログラム全体で x 記憶域の場所へのすべての分割不可能な参照は、互換性のある型である必要があります。  
  
## <a name="examples"></a>次に例を示します。  
  
```  
extern float a[], *p = a, b;  
/* Protect against races among multiple updates. */  
#pragma omp atomic  
a[index[i]] += b;  
/* Protect against races with updates through a. */  
#pragma omp atomic  
p[i] -= 1.0f;  
  
extern union {int n; float x;} u;  
/* ERROR - References through incompatible types. */  
#pragma omp atomic  
u.n++;  
#pragma omp atomic  
u.x -= 1.0f;  
```
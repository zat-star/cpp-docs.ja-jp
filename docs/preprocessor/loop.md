---
title: "ループ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- loop_CPP
- vc-pragma.loop
dev_langs:
- C++
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f3e076c48b512c6059a2f574a07f6e77acfaca22
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="loop"></a>ループ
ループのコードを自動並列化によって処理する方法を制御します。また、ループを自動ベクター化の対象から除外します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma loop( hint_parallel(n) )  
```  
  
```  
  
#pragma loop( no_vector )  
```  
  
```  
  
#pragma loop( ivdep )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hint_parallel(` `n` `)`  
 `n` 個のスレッドにまたがってこのループを並列化するようにコンパイラにヒントを与えます。ここで `n` は、正の整数リテラルまたはゼロです。 `n` がゼロの場合、スレッドの最大数が実行時に使用されます。 これはコンパイラに対するヒントであり、ループが並列化される保証はありません。 ループにデータ間の依存関係、つまり構造上の問題 (たとえばループが、ループ本体を超えて使用されるスカラーに格納するなど) がある場合、ループは並列化されません。  
  
 しない限り、コンパイラはこのオプションを無視、 [/Qpar](../build/reference/qpar-auto-parallelizer.md)コンパイラ スイッチを指定します。  
  
 `no_vector`  
 自動ベクター化は既定でオンになっており、必要と評価されたすべてのループのベクター化が試みられます。 このプラグマは、後続のループの自動ベクター化を無効にする場合に指定します。  
  
 `ivdep`  
 このループでベクターの依存関係を無視するようにコンパイラにヒントを与えます。 このプラグマは、`hint_parallel` と共に使用します。  
  
## <a name="remarks"></a>コメント  
 `loop` プラグマを使用するには、ループ定義の中ではなく直前にプラグマを置きます。 プラグマは後続のループのスコープ内で有効です。 1 つのループに複数のプラグマを任意の順序で適用できますが、プラグマを 1 つずつ個別のステートメントで指定する必要があります。  
  
## <a name="see-also"></a>参照  
 [自動並行化と自動ベクター化](../parallel/auto-parallelization-and-auto-vectorization.md)   
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
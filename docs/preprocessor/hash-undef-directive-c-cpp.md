---
title: "#undef ディレクティブ (C/C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#undef'
dev_langs:
- C++
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 428831b2718009fc0b471d238cff965f74528a2f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="undef-directive-cc"></a>#undef ディレクティブ (C/C++)
`#define` で作成された名前を削除 (定義解除) します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#undef   
identifier  
  
```  
  
## <a name="remarks"></a>コメント  
 `#undef`ディレクティブの現在の定義を削除する*識別子*です。 その結果、それ以降の出現箇所の*識別子*はプリプロセッサによって無視されます。 使用してをマクロ定義を削除する`#undef`、マクロのみを与える*識別子*; パラメーター リストを提供しないでください。  
  
 `#undef` ディレクティブは事前の定義を持たない識別子にも適用できます。 これにより、その識別子が未定義であることが保証されます。 `#undef` ステートメント内では、マクロ置換は実行されません。  
  
 `#undef` ディレクティブ、通常は `#define` ディレクティブと対で使用され、識別子が特別な意味を持つ領域をソース プログラム内に作成します。 たとえば、ソース プログラムの特定の関数でマニフェスト定数を使用すると、プログラムの残り部分に影響を与えない環境固有の値を定義できます。 また `#undef` ディレクティブは、`#if` ディレクティブをソース プログラムの条件付きコンパイルを制御します。 参照してください[#if、#elif、#else、および #endif ディレクティブ](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)詳細についてはします。  
  
 次の例は、`#undef` ディレクティブを使用して、シンボリック定数およびマクロの定義を削除しています。 マクロの識別子のみが指定されていることに注意してください。  
  
```  
#define WIDTH 80  
#define ADD( X, Y ) ((X) + (Y))  
.  
.  
.  
#undef WIDTH  
#undef ADD  
```  
  
 **Microsoft 固有の仕様**  
  
 マクロは、コマンド ラインで /U オプションを使用し、その後ろに定義解除する識別子を指定して定義を解除できます。 このコマンドを発行の効果のシーケンスに相当`#undef`*マクロ名*ステートメントをファイルの先頭にします。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)
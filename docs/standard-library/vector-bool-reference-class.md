---
title: "vector&lt;bool&gt;::reference クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vector/vector<bool>::reference
dev_langs:
- C++
helpviewer_keywords:
- vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 56101a717c56a3999ad32648de8f9ae75d7439d0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="vectorltboolgtreference-class"></a>vector&lt;bool&gt;::reference クラス
`vector<bool>::reference` クラスは `bool&` をシミュレートするために [vector\<bool> クラス](../standard-library/vector-bool-class.md)によって提供されるプロキシ クラスです。  
  
## <a name="remarks"></a>コメント  
 C++ では、ネイティブにビットを直接参照しないため、シミュレートされた参照が必要です。 `vector<bool>` は、要素ごとに 1 ビットだけ使用します。このビットは、このプロキシ クラスを使用して参照できます。 ただし、参照のシミュレーションは、特定の代入が有効でないため、完全ではありません。 たとえば、`vector<bool>::reference` オブジェクトのアドレスを受け取ることができないため、[vector\<bool>::operator&#91;&#93;](http://msdn.microsoft.com/Library/97738633-690d-4069-b2d9-8c54104fbfdd) を使用する次のコードは正しくありません。  
  
```cpp  
vector<bool> vb;  
// ...  
bool* pb = &vb[1]; // conversion error - do not use  
bool& refb = vb[1];   // conversion error - do not use  
```  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[flip](../standard-library/vector-bool-reference-flip.md)|vector 要素のブール値を反転します。|  
|[operator bool](../standard-library/vector-bool-reference-operator-bool.md)|`vector<bool>::reference` から `bool` への暗黙の変換を提供します。|  
|[operator=](../standard-library/vector-bool-reference-operator-assign.md)|ブール値をビットに割り当てます。または参照先の要素が保持している値をビットに割り当てます。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー**: \<vector>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [\<vector>](../standard-library/vector.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)


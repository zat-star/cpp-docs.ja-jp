---
title: "vector&lt;bool&gt;::reference クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vector/vector<bool>::reference
dev_langs: C++
helpviewer_keywords: vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5ebca8cefef2aa53d2726d734932363d54426247
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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


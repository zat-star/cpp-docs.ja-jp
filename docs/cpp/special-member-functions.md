---
title: "特殊なメンバー関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/06/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- special member functions [C++]
- constructors [C++]
- destructors [C++]
- copy operators [C++]
- move operators [C++]
- assignment operators [C++]
ms.assetid: 017d6817-b012-44f0-b153-f3076c251ea7
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 460e6e2ba25566cb4a2295ca4b35590405b51eb3
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="special-member-functions"></a>特殊なメンバー関数  
  
*特殊なメンバー関数*クラス (または構造体) が、場合によっては、コンパイラを自動的に生成するためのメンバー関数。 これらの関数は、[既定のコンス トラクター](constructors-cpp.md#default_constructors)、[デストラクター](destructors-cpp.md)、[コピー コンス トラクターとコピー代入演算子](copy-constructors-and-copy-assignment-operators-cpp.md)、および[移動コンス トラクターと移動代入演算子](move-constructors-and-move-assignment-operators-cpp.md)です。 クラスは、1 つ以上の特殊なメンバー関数は定義されていない場合、コンパイラ可能性があります暗黙的に宣言し、使用される関数を定義します。 コンパイラによって生成された実装が呼び出されます、*既定*特殊なメンバー関数。 必要でない場合、コンパイラは関数を生成できません。  
  
使用して既定の特殊なメンバー関数を明示的に宣言することができます、`= default`キーワード。 これは、コンパイラで必要な場合のみ、同じ方法で関数がすべての宣言されていない場合、関数を定義します。 

場合によっては、コンパイラが生成可能性があります*削除*定義され、したがっていない呼び出し可能ではない特殊なメンバー関数。 これは、クラスの特定の特殊なメンバー関数への呼び出しをなさない、クラスの他のプロパティを指定した場合に起こります。 特殊なメンバー関数の自動生成を明示的に防ぐためには、宣言できます。 これを使用して削除された、`= delete`キーワード。  
  
コンパイラが生成されます、*既定のコンス トラクター*、他の任意のコンス トラクターを宣言していない場合にのみ、引数を受け取らないコンス トラクターです。 パラメーターを受け取るコンス トラクターのみを宣言した場合は、エラー メッセージを生成するためにコンパイラを既定のコンス トラクターを呼び出そうとするコードになります。 実行の単純なコンパイラにより生成された既定のコンス トラクターはメンバーごと[既定の初期化](initializers.md#default_initialization)のオブジェクト。 既定の初期化、不定状態ですべてのメンバー変数のままにします。  
  
既定のデストラクターでは、オブジェクトのメンバーごとの破棄を実行します。 これは、基底クラスのデストラクターが仮想である場合にのみ仮想です。  
  
既定のコピーと移動の構築や代入演算メンバーごとのビット パターンを実行します。 コピーするか、または非静的データ メンバーの移動します。 デストラクターまたは移動またはコピー操作が宣言されていない場合に、操作が生成のみに移動します。 既定のコピー コンス トラクターは、コピー コンス トラクターが宣言されていない場合にのみ生成されます。 移動操作が宣言されている場合に暗黙的に削除されます。 コピー代入演算子が明示的に宣言されていない場合にのみ、既定のコピー代入演算子が生成されます。 移動操作が宣言されている場合に暗黙的に削除されます。  
  
## <a name="see-also"></a>関連項目  
[C++ 言語リファレンス](cpp-language-reference.md)  



 


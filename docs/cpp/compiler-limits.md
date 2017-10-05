---
title: "コンパイラの制限 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
caps.latest.revision: 9
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
ms.openlocfilehash: 986a158ea74e56a0e52c1ffff77f83b8ede71ef5
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="compiler-limits"></a>コンパイラの制限
C++ 標準は、さまざまな言語構成体の制限を勧告しています。 以下は、Visual C++ コンパイラが推奨される制限を実装しない場合のリストです。 最初の数字は ISO C++ 11 標準 (INCITS/ISO/IEC 14882-2011[2012], Annex B) で規定されている制限であり、2 番目の数字は Visual C++ で実装されている制限です。  
  
-   入れ子レベルの複合ステートメント、イテレーション制御構造、および選択制御構造の C++ 標準: 256、Visual C コンパイラ: 入れ子になっているステートメントが一般的に、100 と 110 の間の組み合わせによって決まります。  
  
-   パラメーターの 1 つのマクロ定義の C++ 標準: 256、Visual C コンパイラ: 127 です。  
  
-   引数の 1 つのマクロ呼び出しの C++ 標準: 256、Visual C コンパイラ 127 です。  
  
-   文字数では、リテラルまたはワイド文字列リテラルを文字列 (連結後)、C++ 標準: 65536、Visual C コンパイラ: 65535 1 バイト文字を含む文字、`null`終端記号、および 32767 2 バイト文字を含む文字、 `null`ターミネータです。  
  
-   入れ子になったクラス、構造体、共用体の定義で、1 つのレベル`struct-declaration-list`の C++ 標準: 256、Visual C コンパイラ: 16。  
  
-   メンバーの初期化子コンス トラクターの定義の C++ 標準: 6144、Visual C コンパイラ: 最低 6144 です。  
  
-   スコープ修飾の 1 つの識別子の C++ 標準: 256、Visual C コンパイラ: 127 です。  
  
-   入れ子になった`extern`仕様の C++ 標準: 1024、Visual C コンパイラ: 9 (暗黙をカウントせず`extern`グローバル スコープ、または 10 の暗黙的なをカウントする場合、仕様`extern`グローバル スコープ内の指定..  
  
-   テンプレートの宣言では、C++ 標準にテンプレート引数: 1024、Visual C コンパイラ: 2046 です。  
  
## <a name="see-also"></a>関連項目  
 [非標準動作](../cpp/nonstandard-behavior.md)

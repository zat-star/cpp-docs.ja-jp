---
title: "マクロ (C/C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- preprocessor, macros
- Visual C++, preprocessor macros
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a230abc768b23afd74d1af8a9c178d39d453536a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="macros-cc"></a>マクロ (C/C++)
プリプロセッサ ディレクティブではないすべての行でマクロを展開の前処理 (がない行、  **#** 最初の空白以外の文字として) の一部としてがスキップされない一部のディレクティブの部分で、条件付きコンパイルします。 "条件付きコンパイル" ディレクティブは、定数式または識別子をテストすることによってソース ファイルの一部のコンパイルを抑制して、コンパイラに渡されたテキスト ブロックおよびプリプロセス時にソース ファイルから削除されたテキスト ブロックを判断できるようにします。  
  
 `#define` ディレクティブは、通常、有意な識別子を定数、キーワード、および一般的に使用されるステートメントや式に関連付けるために使用されます。 定数を表す識別子は、"記号定数" または "マニフェスト定数" と呼ばれることがあります。 ステートメントまたは式を表す識別子は "マクロ" と呼ばれます。 このプリプロセッサのドキュメントでは、"マクロ" という用語のみ使用されます。  
  
 マクロの名前が、プログラムのソース テキストまたはその他のプリプロセッサ コマンドの引数で認識されると、そのマクロの呼び出しとして扱われます。 マクロ名はマクロ本体のコピーに置き換えられます。 マクロが引数を受け入れる場合、マクロの本体の仮パラメーターが、マクロ名とその後に続く実際の引数名に置き換えられます。 本体の処理済みのコピーでマクロ呼び出しを置き換えるプロセスは、マクロ呼び出しの「拡張」と呼ばれます。  
  
 実際には、2 種類のマクロがあります。 "オブジェクトのような" マクロは引数を受け取りませんが、"関数のような" マクロは、関数呼び出しと同じように引数を受け取るように定義できます。 マクロは実際の関数呼び出しを生成しないため、関数呼び出しをマクロと置き換えることで、プログラムをより高速で実行できることがあります  (C++ では、多くの場合にインライン関数は適切なメソッドです)。ただし、マクロは注意して定義および使用しないと、問題が生じることがあります。 引数のあるマクロ定義でかっこを使用して、式での適切な優先順位を維持することが必要な場合があります。 また、マクロが正しく副作用のある式を処理しない場合があります。 参照してください、`getrandom`の例で[、#define ディレクティブ](../preprocessor/hash-define-directive-c-cpp.md)詳細についてはします。  
  
 マクロを定義すると、元の定義を最初に削除しない限り、異なる値に再定義できません。 ただし、まったく同じ定義のマクロを再定義することができます。 したがって、同じ定義をプログラムで複数回使用できます。  
  
 #**Undef**ディレクティブは、マクロの定義を削除します。 定義を削除すると、そのマクロを異なる値に再定義できます。 [#Define ディレクティブ](../preprocessor/hash-define-directive-c-cpp.md)と[#undef ディレクティブ](../preprocessor/hash-undef-directive-c-cpp.md)説明、`#define`と`#undef`ディレクティブは、それぞれします。  
  
 詳細については、次のトピックを参照してください。  
  
-   [マクロと C++](../preprocessor/macros-and-cpp.md)  
  
-   [可変個引数マクロ](../preprocessor/variadic-macros.md)  
  
-   [定義済みマクロ](../preprocessor/predefined-macros.md)  
  
## <a name="see-also"></a>参照  
 [C/C++ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)
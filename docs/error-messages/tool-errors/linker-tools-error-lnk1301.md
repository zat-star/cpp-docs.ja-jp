---
title: "リンカ ツール エラー LNK1301 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1301
dev_langs:
- C++
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
caps.latest.revision: 6
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3694841447a83f02821aa260cdfdceaf7bd2ec5b
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk1301"></a>リンカ ツール エラー LNK1301
LTCG clr モジュールが見つかると、/LTCG:parameter と互換性がありません。  
  
 /Clr、/GL でコンパイルされたモジュールは、/LTCG の (PGO) パラメーターをプロファイル ガイド付き最適化のいずれかと共にリンカーに渡されました。  
  
 /Clr のモジュールは、最適化のガイド付きプロファイルはサポートされていません。  
  
 詳細については次を参照してください:  
  
-   [/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [プロファイル ガイド付き最適化](../../build/reference/profile-guided-optimizations.md)  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  /Clr でコンパイルされないまたは/LTCG PGO パラメーターのいずれかでリンクされていません。  
  
## <a name="example"></a>例  
 次の例では、LNK1301 が生成されます。  
  
```  
// LNK1301.cpp  
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj  
// LNK1301 expected  
class MyClass {  
public:  
   int i;  
};  
```

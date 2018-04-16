---
title: "リンカ ツール エラー LNK1301 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1301
dev_langs:
- C++
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cfcdb90b967ce5f0e9eda8dded9b93db5bdcc268
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1301"></a>リンカ ツール エラー LNK1301
LTCG clr モジュールが見つかると、/LTCG:parameter と互換性がありません。  
  
 /Clr:pure および/GL でコンパイルされたモジュールは、/LTCG の (PGO) パラメーターをプロファイル ガイド付き最適化のいずれかと共にリンカーに渡されました。  
  
 /Clr:pure モジュールでは、プロファイル ガイド付き最適化はサポートされていません。  
  
 詳細については次を参照してください:  
  
-   [/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  /Clr でコンパイルしないでまたは/LTCG を PGO パラメーターのいずれかとリンクしません。  
  
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
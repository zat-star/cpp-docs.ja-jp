---
title: "コンパイラの警告 (レベル 1) C4274 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: fbba1e6dde180e77afe7ed8960849ee8cc0fd108
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4274"></a>コンパイラの警告 (レベル 1) C4274
\#ident が無視されます。#pragma コメント (exestr, 'string') のマニュアルを参照してください。  
  
 `#ident`ディレクティブで、ユーザー指定の文字列を挿入すると、オブジェクトまたは実行可能ファイルで、これは推奨されなくなりました。 その結果、コンパイラでは、ディレクティブは無視されます。  
  
> [!CAUTION]
>  警告 C4274 では、使用するように指示、 [#pragma コメント (exestr, 'string')](../../preprocessor/comment-c-cpp.md)ディレクティブです。 ただし、このアドバイスは廃止されており、コンパイラの将来のリリースで変更されます。 使用する場合、`#pragma`ディレクティブは、リンカー ツール (LINK.exe)、ディレクティブによって生成された、このコメント レコードを無視し、警告[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)します。 代わりに、`#ident`ディレクティブをお勧め、アプリケーションでは、ファイルのバージョンのリソース文字列を使用することです。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   削除、 `#ident "`*文字列*`"`ディレクティブです。  
  
## <a name="see-also"></a>関連項目  
 [コメント (C/C++)](../../preprocessor/comment-c-cpp.md)   
 [リンカー ツールの警告 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [リソース ファイルの操作](../../windows/working-with-resource-files.md)

---
title: "コンパイラの警告 (レベル 1) C4274 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4519258a10937ad96528f34484a44d398a0cd0ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4274"></a>コンパイラの警告 (レベル 1) C4274
\#ident が無視されます。#pragma comment (exestr, 'string') のマニュアルを参照してください。  
  
 `#ident`ディレクティブで、オブジェクトまたは実行可能ファイルで、ユーザー指定の文字列を挿入します。 これは推奨されなくなりました。 その結果、コンパイラは、ディレクティブを無視します。  
  
> [!CAUTION]
>  使用するにように勧める警告 C4274、 [#pragma comment (exestr, 'string')](../../preprocessor/comment-c-cpp.md)ディレクティブです。 ただし、このアドバイスは廃止されており、コンパイラの将来のリリースで変更されます。 使用する場合、`#pragma`ディレクティブ、リンカー ツール (LINK.exe) ディレクティブによって生成される、このコメント レコードを無視し、警告を発行[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)です。 代わりに、`#ident`ディレクティブ、ことをお勧め、アプリケーションでは、ファイル バージョン リソース文字列を使用することです。  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   削除、 `#ident "`*文字列*`"`ディレクティブです。  
  
## <a name="see-also"></a>参照  
 [コメント (C/C++)](../../preprocessor/comment-c-cpp.md)   
 [リンカー ツールの警告 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [リソース ファイルの操作](../../windows/working-with-resource-files.md)
---
title: "コンパイラの警告 (レベル 4) C4001 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: bbcf2db5f6650bd9118b28c8bbfe921d13306410
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4001"></a>コンパイラの警告 (レベル 4) C4001
標準外の言語拡張 (単一行コメント) が行われています。  
  
 単一行コメントは、C++ の標準および C の非標準厳密な ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))、単一行コメントを含む C ファイルでは、標準の拡張機能の使用状況により C4001 を生成します。 単一行コメントが C++ の標準的なので、単一行コメントを含む C ファイルは生成されません C4001 Microsoft 拡張機能 (/Ze) でコンパイルする場合。  
  
## <a name="example"></a>例  
 警告を無効にするのには、 [#pragma warning(disable:4001)](../../preprocessor/warning.md)します。  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```

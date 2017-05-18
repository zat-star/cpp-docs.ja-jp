---
title: "NMAKE の致命的なエラー U1033 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1033
dev_langs:
- C++
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e8cd0591a1b2fac4ac8837f53ac576eb1eae7ed7
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="nmake-fatal-error-u1033"></a>NMAKE の致命的なエラー U1033
構文エラー: 予期しない ' string'  
  
 文字列は、メイクファイルの有効な構文の一部ではありません。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  山かっこ閉じる設定されている場合 (**<<**) のインライン ファイル行の先頭には、次のエラーが発生しました。  
  
    ```  
    syntax error : 'EOF' unexpected  
    ```  
  
2.  メイクファイルのマクロ定義に等号 (=) が含まれているかどうか (**=**)、次のエラーが発生する、前の名前または名前が定義されている場合に何も展開されるマクロ、なし。  
  
    ```  
    syntax error : '=' unexpected  
    ```  
  
3.  場合は、セミコロン (**;**) ツール内のコメント行にします。INI は、行の先頭に次のエラーが発生しました。  
  
    ```  
    syntax error : ';' unexpected  
    ```  
  
4.  メイクファイルはワード プロセッサで書式設定されている、次のエラーが発生することができます。  
  
    ```  
    syntax error : ':' unexpected  
    ```

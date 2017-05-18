---
title: "致命的なエラー C1071 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1071
dev_langs:
- C++
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
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
ms.openlocfilehash: a804a858d625c4e787c1202182e275ec9bee3af1
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1071"></a>致命的なエラー C1071
コメント内で予期しない EOF が見つかりました。  
  
 コンパイラでは、コメントのスキャン中に、ファイルの末尾に達しています。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  コメントの終端記号がありません (*/)。  
  
2.  ソース ファイルの最後の行のコメントの後ろに改行文字がありません。  
  
 次の例では、C1071 が生成されます。  
  
```  
// C1071.cpp  
int main() {  
}  
  
/* this comment is fine */  
/* forgot the closing tag        // C1071  
```

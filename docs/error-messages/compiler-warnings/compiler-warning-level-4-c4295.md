---
title: "コンパイラの警告 (レベル 4) C4295 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: 5
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
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: b831b8e7b838ef25679d49a132c66d4b378fdcd7
ms.contentlocale: ja-jp
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4295"></a>コンパイラの警告 (レベル 4) C4295
  
> '*配列*': 配列が小さすぎるため、終端の null 文字を含める  
  
 配列の初期化が、配列の最後の文字は、null ではありません。配列にアクセスすると、予期しない結果が生じる場合があります。  
  
## <a name="example"></a>例  
  
 次の例では、C4295 が生成されます。 この問題を解決する可能性がありますを宣言する配列のサイズ終端を保持するために、大規模な初期化子から null です。  
  
```C  
// C4295.c  
// compile with: /W4  
  
int main() {  
   char a[3] = "abc";   // C4295  
}  
```

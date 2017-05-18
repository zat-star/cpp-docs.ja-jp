---
title: "コンパイラの警告 (レベル 3) C4159 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4159
dev_langs:
- C++
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
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
ms.openlocfilehash: 874264f7e8b3820fadb8fa866ac5a05913530ec3
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4159"></a>コンパイラの警告 (レベル 3) C4159
\#プラグマ pragma(pop,...): 以前にプッシュされた識別子 'identifier' がポップされます。  
  
 ソース コードに含まれる、**プッシュ**命令、プラグマの識別子を後に、 **pop**識別子のない命令します。 その結果、***識別子***、表示されたとそれ以降で使用していたの***識別子***予期しない動作が発生する可能性があります。  
  
 この警告を回避するで識別子を指定、 **pop**命令します。 例:  
  
```  
// C4159.cpp  
// compile with: /W3  
#pragma pack(push, f)  
#pragma pack(pop)   // C4159  
  
// using the identifier resolves the warning  
// #pragma pack(pop, f)  
  
int main()  
{  
}  
```

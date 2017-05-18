---
title: "コンパイラ エラー C2166 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2166
dev_langs:
- C++
helpviewer_keywords:
- C2166
ms.assetid: 12789c3a-cc76-48bb-ae2e-64283e0964ed
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 67ea0926cf1d42287c1bfad7ad50743e8c16cd44
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2166"></a>コンパイラ エラー C2166
左辺値は const オブジェクトに指定されています。  
  
 コードが、 `const`宣言した項目を変更しようとしています。  
  
 次の例では C2166 が生成されます。  
  
```  
// C2166.cpp  
int f();  
int main() {  
   ( (const int&) 1 ) = 5;   // C2166  
}  
```

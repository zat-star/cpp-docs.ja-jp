---
title: "コンパイラ エラー C3279 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3279
dev_langs:
- C++
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
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
ms.openlocfilehash: cd0e6c10a544cf9b23edd93a4268122135adb6af
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3279"></a>コンパイラ エラー C3279
cli 名前空間で宣言されたクラス テンプレートの明示的なインスタンス生成と同様に、部分的または明示的な特殊化は許可されていません  
  
 `cli` 名前空間は、Microsoft によって定義され、擬似テンプレートが含まれています。 Visual C++ コンパイラでは、この名前空間におけるユーザー定義、部分的、および明示的な特殊化は許可されず、クラス テンプレートの明示的なインスタンス化も許可されません。  
  
 次の例では C3279 が生成されます。  
  
```  
// C3279.cpp  
// compile with: /clr  
namespace cli {  
   template <> ref class array<int> {};   // C3279  
   template <typename T> ref class array<T, 2> {};   // C3279  
}  
```

---
title: "コンパイラ エラー C2870 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2870
dev_langs:
- C++
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 75b9189795c7351745e9624cfb9cc11259834b76
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2870"></a>コンパイラ エラー C2870
'name': 名前空間の定義は、ファイル スコープ、またはすぐに別の名前空間の定義内に表示される必要があります  
  
 名前空間を定義した`name`が正しくないです。 名前空間を (すべてのブロックとクラス) の外部のファイル スコープで定義する必要がありますまたは別の名前空間内ですぐにします。  
  
 次の例では、C2870 が生成されます。  
  
```  
// C2870.cpp  
// compile with: /c  
int main() {  
   namespace A { int i; };   // C2870  
}  
```

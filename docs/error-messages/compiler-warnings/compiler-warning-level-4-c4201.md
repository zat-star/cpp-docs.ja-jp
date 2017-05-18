---
title: "コンパイラの警告 (レベル 4) C4201 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4201
dev_langs:
- C++
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
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
ms.openlocfilehash: 6c0953963ab384dc1b6ec47056768ca3655c63a7
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4201"></a>コンパイラの警告 (レベル 4) C4201
非標準の拡張機能が使用されています : 無名の構造体または共用体です。  
  
 Microsoft 拡張機能 (/Ze)、別の構造体または共用体のメンバーとして、宣言子なしの構造を指定できます。 これらの構造体は、ANSI 互換のエラーを生成 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。  
  
## <a name="example"></a>例  
  
```  
// C4201.cpp  
// compile with: /W4  
struct S  
{  
   float y;  
   struct  
   {  
      int a, b, c;  // C4201  
   };  
} *p_s;  
  
int main()  
{  
}  
```

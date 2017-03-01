---
title: "コンパイラの警告 (レベル 3) C4240 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4240
dev_langs:
- C++
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0539f8892d017a58d224fdb5afe5037c29917702
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4240"></a>コンパイラの警告 (レベル 3) C4240
使用される標準の拡張機能: 'アクセス指定子' を 'classname' 'アクセス指定子' を以前のバージョンで現在定義へのアクセスが定義されました  
  
 ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))、入れ子になったクラスに、アクセスを変更することはできません。 既定の Microsoft 拡張 (/Ze) では、この警告をできます。  
  
## <a name="example"></a>例  
  
```  
// C4240.cpp  
// compile with: /W3  
class X  
{  
private:  
   class N;  
public:  
   class N  
   {   // C4240  
   };  
};  
  
int main()  
{  
}  
```

---
title: "リンカー ツールの警告 LNK4078 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4078
dev_langs:
- C++
helpviewer_keywords:
- LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
caps.latest.revision: 10
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
ms.openlocfilehash: 81f5c9e42d05bbc5646ad0b3fd27fd39408301b1
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4078"></a>リンカー ツールの警告 LNK4078
複数の 'セクション名' セクションが別の属性が見つかりました  
  
 2 つのリンクが見つかったら、または名前が同じである他のセクションで異なる属性です。  
  
 この警告は、リンクまたは LIB の以前のバージョンで作成されたインポート ライブラリまたはエクスポート ファイルによって可能性があります。  
  
 ファイルと再リンクを再作成します。  
  
## <a name="example"></a>例  
 LNK4078 は、互換性に影響する変更点によって発生することも: で指定されるセクション[init_seg](../../preprocessor/init-seg.md) x86 が読み取り/書き込み、読み取り専用ようになりました。  
  
 次の例では、LNK4078 を生成します。  
  
```  
// LNK4078.cpp  
// compile with: /W1  
// LNK4078 expected  
#include <stdio.h>  
#pragma warning(disable : 4075)  
typedef void (__cdecl *PF)(void);  
int cxpf = 0;   // number of destructors to call  
PF pfx[200];   // pointers to destructors.  
  
struct A { A() {} };  
  
int myexit (PF pf) { return 0; }  
  
#pragma section(".mine$a", read, write)  
// try the following line instead  
// #pragma section(".mine$a", read)  
__declspec(allocate(".mine$a")) int ii = 1;  
  
#pragma section(".mine$z", read, write)  
// try the following line instead  
// #pragma section(".mine$z", read)  
__declspec(allocate(".mine$z")) int i = 1;  
  
#pragma data_seg()  
#pragma init_seg(".mine$m", myexit)  
A bbbb;   
A cccc;  
int main() {}  
```

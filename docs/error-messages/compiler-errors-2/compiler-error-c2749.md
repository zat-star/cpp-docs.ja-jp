---
title: "コンパイラ エラー C2749 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2749
dev_langs: C++
helpviewer_keywords: C2749
ms.assetid: a81aef36-cdca-4d78-89d5-b72eff2500b2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 23eb174bd161f14351fae18ae4aba72f427da4ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2749"></a>コンパイラ エラー C2749
'type': のみスローまたは/clr:safe を伴うマネージ クラスへのハンドルをキャッチできます  
  
 使用する場合**/clr:safe**、のみをスローまたは参照型をキャッチできます。  
  
 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C2749 が生成されます。  
  
```  
// C2749.cpp  
// compile with: /clr:safe  
ref struct MyStruct {  
public:  
   int i;  
};  
  
int main() {  
   MyStruct ^x = gcnew MyStruct;  
  
   // Delete the following 4 lines to resolve.  
   try {   
      throw (1);   // C2749  
   }  
   catch(int){}  
  
   // OK  
   try {  
      throw (x);  
   }  
   catch(MyStruct ^){}   
}  
```
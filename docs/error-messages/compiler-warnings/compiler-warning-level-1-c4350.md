---
title: "コンパイラの警告 (レベル 1) C4350 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4350
dev_langs:
- C++
helpviewer_keywords:
- C4350
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c3a5411475d898562b8cba62ddeffcaf1dfec095
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4350"></a>コンパイラの警告 (レベル 1) C4350
動作変更: 'member1' が 'member2' の代わりに呼び出されました。  
  
 右辺値は、非定数の参照にバインドすることはできません。 Visual C の以前のバージョンでは、直接の初期化で非定数の参照を右辺値をバインドすることでした。 これで、このコードには、警告が得られます。  
  
 旧バージョンとの互換性のために非 const 参照を右辺値をバインドすることも可能ですが、可能な限り、標準変換は優先的に使用。  
  
 この警告は、Visual C .NET 2002 コンパイラの動作の変更を表します。 有効な場合、この警告は正しいコードの可能性がある与え可能性があります。 たとえば、そのことがあるを使用する場合、 **std::auto_ptr**クラス テンプレートです。  
  
 この警告が発生した場合は、非定数の参照を右辺値をバインドに依存しているかどうかをコードをチェックします。 参照に定数を追加するか、追加の定数参照のオーバー ロードを提供するには、問題を解決できます。  
  
 既定では、この警告はオフに設定されています。 詳細については、次を参照してください。[コンパイラの警告ことは既定で無効](../../preprocessor/compiler-warnings-that-are-off-by-default.md)します。  
  
 次の例では、C4350 が生成されます。  
  
```  
// C4350.cpp  
// compile with: /W1  
#pragma warning (default : 4350)  
class A {};  
  
class B  
{  
public:  
   B(B&){}  
   // try the following instead  
   // B(const B&){}  
  
   B(A){}  
   operator A(){ return A();}  
};  
  
B source() { return A(); }  
  
int main()  
{  
   B ap(source());   // C4350  
}  
```

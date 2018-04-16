---
title: "リンカー ツールの警告 LNK4248 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4248
dev_langs:
- C++
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01053ddbbb0c7d234f6b465392f5bbe991ea329c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4248"></a>リンカー ツールの警告 LNK4248
'type' の未解決の typeref トークン (トークン)イメージは動作しない可能性があります。  
  
 MSIL のメタデータに型の定義がありません。  
  
 LNK4248 は、MSIL モジュール内の型の事前宣言のみがある場合に発生することができます (でコンパイルされた**/clr**)、MSIL モジュールの種類を参照し、その MSIL モジュールの定義を保持しているネイティブ モジュールとリンクしています。型。  
  
 このような状況では、リンカーはメタデータでは MSIL、ネイティブ型定義を提供し、これは、正しい動作を提供します。  
  
 ただし、事前の型宣言が、CLR 型の場合は、し、リンカーのネイティブな型定義できません。  
  
 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  MSIL モジュールの種類の定義を提供します。  
  
## <a name="example"></a>例  
 次の例では、LNK4248 が生成されます。 解決するのには struct A を定義します。  
  
```  
// LNK4248.cpp  
// compile with: /clr /W1  
// LNK4248 expected  
struct A;  
void Test(A*){}  
  
int main() {  
   Test(0);  
}  
```  
  
## <a name="example"></a>例  
 次の例では、型の転送の定義がします。  
  
```  
// LNK4248_2.cpp  
// compile with: /clr /c  
class A;   // provide a definition for A here to resolve  
A * newA();  
int valueA(A * a);  
  
int main() {  
   A * a = newA();  
   return valueA(a);  
}  
```  
  
## <a name="example"></a>例  
 次の例では、LNK4248 が生成されます。  
  
```  
// LNK4248_3.cpp  
// compile with: /c  
// post-build command: link LNK4248_2.obj LNK4248_3.obj  
class A {  
public:   
   int b;  
};  
  
A* newA() {  
   return new A;  
}  
  
int valueA(A * a) {  
   return (int)a;  
}  
```
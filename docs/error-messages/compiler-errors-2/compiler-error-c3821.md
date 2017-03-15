---
title: "コンパイラ エラー C3821 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3821
dev_langs:
- C++
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
caps.latest.revision: 12
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 24212b0df7b665f8c8ab2614b9a23e66f19586af
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3821"></a>コンパイラ エラー C3821
'function': マネージ型または関数は、アンマネージ関数で使用できません  
  
 インライン アセンブリでの関数または[setjmp](../../c-runtime-library/reference/setjmp.md)値の型またはマネージ クラスを含めることはできません。 このエラーを解決するには、インライン アセンブリを削除し、`setjmp`またはマネージ オブジェクトを削除します。  
  
 C3821 エラーは、自動ストレージ vararg 関数で使用しようとする場合にも発生します。  詳細については、次を参照してください[可変個引数リスト (...)。(C + +/CLI)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)と[参照型の C++ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)します。  
  
## <a name="example"></a>例  
 次の例では、c3821 エラーが生成されます。  
  
```  
// C3821a.cpp  
// compile with: /clr /c  
public ref struct R {};  
void test1(...) {  
   R r;   // C3821  
}  
```  
  
## <a name="example"></a>例  
 次の例では、c3821 エラーが生成されます。  
  
```  
// C3821b.cpp  
// compile with: /clr  
// processor: /x86  
ref class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A ^a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```  


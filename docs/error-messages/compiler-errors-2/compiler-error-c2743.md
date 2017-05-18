---
title: "コンパイラ エラー C2743 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2743
dev_langs:
- C++
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: 8
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 7420231e64515b556cfe81fc695eda5f75231506
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2743"></a>コンパイラ エラー C2743
'type': _ _clrcall デストラクターまたはコピー コンス トラクターを持つネイティブ型をキャッチすることはできません  
  
 コンパイルされたモジュール**/clr**のネイティブ型と型のデストラクターまたはコピー コンス トラクターが使用して例外をキャッチしようとしています。`__clrcall`呼び出し規約です。  
  
 コンパイルされたときに**/clr**、例外処理メンバー関数を必要とするネイティブ型[_ _cdecl](../../cpp/cdecl.md)および not [_ _clrcall](../../cpp/clrcall.md)します。 ネイティブ型を使用してメンバー関数と`__clrcall`でコンパイルされたモジュールの呼び出し規約をキャッチできません**/clr**します。  
  
 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、c2743 エラーを生成します。  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```

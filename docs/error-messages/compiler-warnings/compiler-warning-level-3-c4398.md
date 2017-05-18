---
title: "コンパイラの警告 (レベル 3) C4398 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: 6
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
ms.openlocfilehash: 18270bb89bcc5d1855750c572a5b6fb9e51c2ba3
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4398"></a>コンパイラの警告 (レベル 3) C4398
'variable': 複数の appdomain でプロセスごとのグローバル オブジェクトが正しく機能しません。__declspec(appdomain) の使用を検討してください。  
  
 仮想関数を[_ _clrcall](../../cpp/clrcall.md)の作成ネイティブ型で規則を呼び出すと、アプリケーション ドメインの vtable ごとです。 複数のアプリケーション ドメインで使用する場合は、このような変数が適切に修正されない場合があります。  
  
 この警告を解決するには、変数を明示的にマークすることによって`__declspec(appdomain)`します。 コンパイルしてこの警告を解決するバージョンの Visual Studio 2017 する前に Visual Studio で**/clr: 純粋な**、appdomain ごとのグローバル変数は既定では、これです。  
  
 詳細については、次を参照してください。 [appdomain](../../cpp/appdomain.md)と[アプリケーション ドメインと Visual c](../../dotnet/application-domains-and-visual-cpp.md)します。  
  
## <a name="example"></a>例  
 次の例では、C4398 を生成します。  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```

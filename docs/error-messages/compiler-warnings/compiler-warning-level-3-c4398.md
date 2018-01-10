---
title: "コンパイラの警告 (レベル 3) C4398 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4398
dev_langs: C++
helpviewer_keywords: C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d5ce6355e50c1ea2594820388edc34c69ea0e899
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4398"></a>コンパイラの警告 (レベル 3) C4398
'variable': プロセスごとのグローバル オブジェクトは複数の appdomain と共に動作しない可能性があります__declspec(appdomain) を使用してください。  
  
 仮想関数と[_ _clrcall](../../cpp/clrcall.md)の作成をネイティブ型に規則を呼び出すと、アプリケーション ドメインの vtable ごとです。 複数のアプリケーション ドメインで使用する場合は、このような変数が適切に修正されない場合があります。  
  
 この警告を解決するには、変数を明示的にマークすることによって`__declspec(appdomain)`です。 Visual Studio 2017 より前に、の Visual Studio のバージョンは、この警告を解決でコンパイルすると**/clr: 純粋な**、これにより、appdomain ごとのグローバル変数既定値です。  
  
 詳細については、次を参照してください。 [appdomain](../../cpp/appdomain.md)と[アプリケーション ドメインと Visual c](../../dotnet/application-domains-and-visual-cpp.md)です。  
  
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
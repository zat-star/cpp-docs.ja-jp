---
title: "コンパイラの警告 (レベル 1) C4486 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4486
dev_langs:
- C++
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 086e74947753ddbb801a46c3d7918591cf83cee0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4486"></a>コンパイラの警告 (レベル 1) C4486
'function': ref クラスまたは値クラスのプライベート仮想メソッドは、'sealed' マークする必要があります  
  
 マークする必要がありますので、マネージ クラスまたは構造体のプライベート仮想メンバー関数はアクセスできないか、またはオーバーライドして、[シール](../../windows/sealed-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C4486 を生成します。  
  
```  
// C4486.cpp  
// compile with: /clr /c /W1  
ref class B {  
private:  
   virtual void f() {}   // C4486  
   virtual void f1() sealed {}   // OK  
};  
```  
  
## <a name="example"></a>例  
 次の例では、プライベート、シールされた仮想関数の用途の 1 つを示します。  
  
```  
// C4486_b.cpp  
// compile with: /clr /c  
ref class B {};  
  
ref class D : B {};  
  
interface class I {  
   B^ mf();  
};  
  
ref class E : I {  
private:  
   virtual B^ g() sealed = I::mf {  
      return gcnew B;  
   }  
  
public:  
   virtual D^ mf() {  
      return gcnew D;  
   }  
};  
```
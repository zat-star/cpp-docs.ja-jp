---
title: "コンパイラ エラー C3771 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3771
dev_langs: C++
helpviewer_keywords: C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d1f552eee7ac20c086240a4ce79fd3616127268b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3771"></a>コンパイラ エラー C3771
"identifier" : フレンド宣言が一番近い名前空間スコープに見つかりませんでした  
  
指定したテンプレート *identifier* のクラス テンプレート宣言が、現在の名前空間内に見つかりません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   テンプレート識別子のクラス テンプレート宣言が現在の名前空間で定義されていること、またはテンプレート識別子が完全修飾名であることを確認します。  
  
## <a name="example"></a>例  
次のコード例では、名前空間 `NA`でクラス テンプレートと関数を宣言しますが、名前空間 `NB`でフレンド関数テンプレートを宣言しようとします。  
  
```cpp  
// C3771.cpp   
// compile with: /c  
  
namespace NA {  
template<class T> class A {  
    void aFunction(T t) {};  
    };  
}  
// using namespace NA;  
namespace NB {  
    class X {  
        template<class T> friend void A<T>::aFunction(T); // C3771  
// try the following line instead  
//      template<class T> friend void NA::A<T>::aFunction(T);  
// or try "using namespace NA;" instead.  
    };  
}  
```  
  
## <a name="see-also"></a>参照  
[テンプレート](../../cpp/templates-cpp.md)  
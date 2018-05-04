---
title: 保護された (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- protected_cpp
dev_langs:
- C++
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be866cda09ddc1770cf8d4b1ac0433e3c2701520
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="protected-c"></a>protected (C++)
## <a name="syntax"></a>構文  
  
```  
protected:  
   [member-list]  
protected base-class  
```  
  
## <a name="remarks"></a>コメント  
 `protected`キーワードをクラス メンバーへのアクセスを指定します、*メンバー リスト*まで、次のアクセス指定子 (**パブリック**または`private`) またはクラス定義の末尾。 `protected` として宣言されたクラス メンバーは、次でのみ使用することができます。  
  
-   これらのメンバーを最初に宣言したクラスのメンバー関数。  
  
-   これらのメンバーを最初に宣言したクラスのフレンド。  
  
-   これらのメンバーを最初に宣言したクラスからパブリックまたはプロテクトのアクセス レベルで派生したクラス。  
  
-   プロテクト メンバーへのプライベート アクセスもできる、プライベートとして設定した直接派生クラス。  
  
 基底クラスの名前を指定すると、`protected` キーワードは、基底クラスのパブリック、プロテクト メンバーが派生クラスのプロテクト メンバーであることを指定します。  
  
 プロテクト メンバーがプライベートでとしてではありません`private`は、宣言されているが、ほどパブリックでは、クラスのメンバーだけにアクセスできるメンバー**パブリック**は、すべての関数でアクセスできるメンバー。  
  
 プロテクト メンバーとしても宣言されている**静的**は、派生クラスのフレンドまたはメンバー関数にアクセスします。 プロテクト メンバーとして宣言されていない**静的**は、友人とへのポインター、参照、または、派生クラスのオブジェクトからのみ派生クラスでメンバー関数にアクセスします。  
  
 関連情報については、次を参照してください[フレンド](../cpp/friend-cpp.md)、[パブリック](../cpp/public-cpp.md)、[プライベート](../cpp/private-cpp.md)、とでメンバー アクセス テーブル[クラス メンバーへのアクセスの制御](member-access-control-cpp.md).  
  
## <a name="clr-specific"></a>/clr 固有  
 CLR 型では、C++ アクセス指定子のキーワード (**パブリック**、 `private`、および`protected`) 型とアセンブリに関連メソッドの可視性に影響を与えることができます。 詳細については、次を参照してください。[メンバー アクセス コントロール](member-access-control-cpp.md)です。  
  
> [!NOTE]
>  コンパイルされるファイル[/LN](../build/reference/ln-create-msil-module.md)この動作の影響は受けません。 この場合、すべてのマネージ クラス (パブリックかプライベート) が表示されます。  
  
## <a name="end-clr-specific"></a>END /clr 固有  
  
## <a name="example"></a>例  
  
```  
// keyword_protected.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class X {  
public:  
   void setProtMemb( int i ) { m_protMemb = i; }  
   void Display() { cout << m_protMemb << endl; }  
protected:  
   int  m_protMemb;  
   void Protfunc() { cout << "\nAccess allowed\n"; }  
} x;  
  
class Y : public X {  
public:  
   void useProtfunc() { Protfunc(); }  
} y;  
  
int main() {  
   // x.m_protMemb;         error, m_protMemb is protected  
   x.setProtMemb( 0 );   // OK, uses public access function  
   x.Display();  
   y.setProtMemb( 5 );   // OK, uses public access function  
   y.Display();  
   // x.Protfunc();         error, Protfunc() is protected  
   y.useProtfunc();      // OK, uses public access function  
                        // in derived class  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス メンバーへのアクセスを制御します。](member-access-control-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)
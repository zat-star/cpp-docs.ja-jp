---
title: "friend (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Friend"
  - "friend_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "フレンド クラス"
  - "friend キーワード [C++]"
  - "メンバー アクセス, フレンド関数から"
ms.assetid: 8fe9ee55-d56f-40cd-9075-d9fb1375aff4
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# friend (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

場合によっては、クラスのメンバーでない関数や別のクラスのすべての関数に、メンバー レベルのアクセスを許可する方が便利です。  クラスの実装側が自分のフレンドを宣言することだけが可能です。  関数またはクラスが自分自身をいずれかのクラスのフレンドとして宣言することはできません。  クラス宣言では、`friend` キーワードと、非メンバー関数または他のクラスの名前を使用して、クラスのプライベートおよびプロテクト メンバーへのアクセスを許可します。  
  
## 構文  
  
```  
  
        friend class-name;  
friend function-declarator;  
```  
  
## フレンド宣言  
 以前に宣言されなかったフレンド関数を宣言すると、その関数は外側の非クラス スコープにエクスポートされます。  
  
 フレンド宣言で宣言された関数は、`extern` キーワードを使って宣言されたものとして扱われます   \(`extern` の詳細については、「[静的ストレージ クラス指定子](http://msdn.microsoft.com/ja-jp/3ba9289a-a412-4a17-b319-ceb2c087df48)」を参照してください\)。  
  
 グローバル スコープの関数はプロトタイプの前にフレンドとして宣言できますが、メンバー関数は、完全なクラス宣言の前にフレンドとして宣言することはできません。  次のコードは、なぜこれが失敗するかを示します。  
  
```  
class ForwardDeclared;   // Class name is known.  
class HasFriends  
{  
    friend int ForwardDeclared::IsAFriend();   // C2039 error expected  
};  
```  
  
 前の例では、スコープにクラス名 `ForwardDeclared` を入力しますが、宣言全体、特に関数 `IsAFriend` を宣言する部分は不明です。  したがって、`friend` クラスの `HasFriends` 宣言はエラーを生成します。  
  
 相互にフレンドである 2 つのクラスを宣言するには、2 番目のクラス全体が最初のクラスのフレンドとして指定される必要があります。  この制限の理由は、2 番目のクラスが宣言された位置でのみコンパイラは個々のフレンド関数を宣言するために十分な情報を得られるためです。  
  
> [!NOTE]
>  2 番目のクラス全体は最初のクラスへのフレンドである必要がありますが、最初のクラスのどの関数が 2 番目のクラスのフレンドであるかを選択できます。  
  
## friend 関数  
 `friend` 関数は、クラスのメンバーではないが、クラスのプライベート メンバーとプロテクト メンバーにアクセスできる関数です。  friend 関数はクラス メンバーと見なされません。これらの関数は、特別なアクセス特権が付与されている標準の外部関数です。  friend はクラスのスコープ内に含まれません。また、別のクラスのメンバーでない限り、メンバー選択演算子 \(**.** および –**\>**\) を使用して呼び出されません。  `friend` 関数はアクセスを付与しているクラスで宣言されます。  `friend` 宣言はクラス宣言内の任意の場所に配置できます。  アクセス制御キーワードによる影響はありません。  
  
 次に、`Point` クラスと `ChangePrivate` フレンド関数の例を示します。  この `friend` 関数は、自身がパラメーターとして受け取る `Point` オブジェクトのプライベート データ メンバーにアクセスできます。  
  
```  
// friend_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Point  
{  
    friend void ChangePrivate( Point & );  
public:  
    Point( void ) : m_i(0) {}  
    void PrintPrivate( void ){cout << m_i << endl; }  
  
private:  
    int m_i;  
};  
  
void ChangePrivate ( Point &i ) { i.m_i++; }  
  
int main()  
{  
   Point sPoint;  
   sPoint.PrintPrivate();  
   ChangePrivate(sPoint);  
   sPoint.PrintPrivate();  
// Output: 0  
           1  
}  
```  
  
## フレンドとしてのクラス メンバー  
 クラス メンバー関数は他のクラスのフレンドとして宣言できます。  次に例を示します。  
  
```  
// classes_as_friends1.cpp  
// compile with: /c  
class B;  
  
class A {  
public:  
   int Func1( B& b );  
  
private:  
   int Func2( B& b );  
};  
  
class B {  
private:  
   int _b;  
  
   // A::Func1 is a friend function to class B  
   // so A::Func1 has access to all members of B  
   friend int A::Func1( B& );  
};  
  
int A::Func1( B& b ) { return b._b; }   // OK  
int A::Func2( B& b ) { return b._b; }   // C2248  
```  
  
 この例では、`A::Func1( B& )` 関数に `B` クラスへのフレンド アクセスのみ許可されます。  したがって、プライベート メンバー `_b` へのアクセスは、`Func1` クラスの `A` では正しく、`Func2` では正しくありません。  
  
 `friend` クラスは、すべてのメンバー関数が、クラスのその他のプライベート メンバーとプロテクト メンバーにアクセスできるメンバー関数を持つ、クラスのフレンド関数であるクラスです。  `friend` クラスの `B` 宣言が次のようになっていたとします。  
  
```  
friend class A;  
```  
  
 その場合、`A` クラスのすべてのメンバー関数に `B` クラスへのフレンド アクセスが許可されます。  次に、フレンド クラスの例を示します。  
  
```  
// classes_as_friends2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class YourClass {  
friend class YourOtherClass;  // Declare a friend class  
public:  
   YourClass() : topSecret(0){}  
   void printMember() { cout << topSecret << endl; }  
private:  
   int topSecret;  
};  
  
class YourOtherClass {  
public:  
   void change( YourClass& yc, int x ){yc.topSecret = x;}  
};  
  
int main() {  
   YourClass yc1;  
   YourOtherClass yoc1;  
   yc1.printMember();  
   yoc1.change( yc1, 5 );  
   yc1.printMember();  
}  
```  
  
 明示的に指定されていない限り、フレンド関係は相互関係ではありません。  上の例では、`YourClass` のメンバー関数は `YourOtherClass` のプライベート メンバーにアクセスできません。  
  
 マネージ型に、フレンド関数、フレンド クラス、またはフレンド インターフェイスを含めることはできません。  
  
 フレンド関係は継承されません。つまり、`YourOtherClass` から派生したクラスは `YourClass` のプライベート メンバーにアクセスできません。  フレンド関係は推移的ではないため、`YourOtherClass` のフレンドであるクラスは `YourClass` にアクセスできません。  
  
 次の図は、4 つのクラス宣言 \(`Base`、`Derived`、`aFriend`、`anotherFriend`\) を示しています。  `aFriend` のプライベート メンバー \(および `Base` が継承した可能性があるすべてのメンバー\) に直接アクセスできるのは、`Base` クラスだけです。  
  
 ![フレンド関係の包含](../cpp/media/vc38v41.png "vc38V41")  
フレンド関係の包含  
  
## インラインのフレンドの定義  
 friend 関数は、クラス宣言内で定義できます。  これらの関数はインライン関数であり、メンバーのインライン関数のように、すべてのクラス メンバーが発生した直後、クラス スコープが閉じる前に定義されているように動作します \(クラス宣言の末尾\)。  
  
 クラス宣言内で定義された friend 関数は、それを囲んでいるクラスのスコープ内にあるとは見なされません。それらはファイル スコープ内にあると見なされます。  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)
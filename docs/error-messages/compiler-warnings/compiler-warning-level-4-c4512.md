---
title: "コンパイラの警告 (レベル 4) C4512 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4512"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4512"
ms.assetid: afb68995-684a-4be5-a73a-38d7a16dc030
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4512
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'クラス' : 代入演算子を生成できません。  
  
 コンパイラは、指定されたクラスに対する代入演算子を生成できません。  代入演算子は作成されませんでした。  
  
 派生クラスでアクセスできない基本クラスの代入演算子がある場合に、この警告が発生することがあります。  
  
 この警告を回避するには、クラスに対してユーザー定義の代入演算子を指定します。  
  
 代入演算子の関数が定義されていないクラスに対しても、代入演算子の関数がコンパイラによって生成されます。  この代入演算子は、オブジェクトのデータ メンバーのメンバーごとのコピーです。  クラスに `const` が含まれている場合は、`const` データ項目を初期化後に変更することができないため、既定の代入演算子は機能しません。  C4512 警告のもう 1 つの原因は、参照型の非静的データ メンバーの宣言です。  コピー可能でない型を作成するには、既定のコピー コンス トラクターも作成する必要があります。  
  
 コードの C4512 警告は、次の 3 つのうちのいずれかの方法で解決できます。  
  
-   クラスに対する代入演算子を明示的に定義します。  
  
-   クラスのデータ項目から **const** または参照演算子を削除します。  
  
-   \#pragma [warning](../../preprocessor/warning.md) ステートメントを使用して警告を抑制します。  
  
## 使用例  
 次の例では C4512 エラーが生成されます。  
  
```  
// C4512.cpp  
// compile with: /EHsc /W4  
// processor: x86  
  
class Base {  
private:  
   const int a;  
  
public:  
   Base(int val = 0) : a(val) {}  
   int get_a() { return a; }  
};   // C4512 warning  
  
class Base2 {  
private:  
   const int a;  
  
public:  
   Base2(int val = 0) : a(val) {}  
   Base2 & operator=( const Base2 & ) { return *this; }  
   int get_a() { return a; }  
};  
  
// Type designer intends this to be non-copyable because it has a   
// reference member  
class Base3  
{  
private:  
   char& cr;  
  
public:  
   Base3(char& r) : cr(r) {}  
   // Uncomment the following line to explicitly disable copying:  
   // Base3(const Base3&) = delete;   
};   // C4512 warning  
  
int main() {  
   Base first;  
   Base second;  
  
   // OK  
   Base2 first2;  
   Base2 second2;  
  
   char c = 'x';  
   Base3 first3(c);  
   Base3 second3 = first3; // C2280 if no default copy ctor  
}  
  
```
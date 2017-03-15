---
title: "コンパイラ エラー C2146 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2146"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2146"
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# コンパイラ エラー C2146
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

構文エラー : 'token' が、識別子 'identifier' の前に必要です。  
  
 `token` を置く必要がある場所で `identifier` を検出しました。以下の原因が考えられます。  
  
1.  スペルの誤りまたは大文字小文字の入力ミスがあります。  
  
2.  識別子の宣言に型指定子がありません。  
  
 このエラーは、誤字が原因で発生する場合があります。  通常、このエラーは [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) エラーの前に発生します。  
  
## 使用例  
 次の例では C2146 エラーが生成されます。  
  
```  
// C2146.cpp  
class CDeclaredClass {};  
  
class CMyClass {  
   CUndeclared m_myClass;   // C2146  
   CDeclaredClass m_myClass2;   // OK  
};  
  
int main() {  
   int x;  
   int t x;   // C2146 : missing semicolon before 'x'  
}  
```  
  
## 使用例  
 このエラーは、`typename` キーワードがない Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成されることもあります。  
  
 次のコード例は、Visual Studio .NET 2002 ではコンパイルされますが、Visual Studio .NET 2003 ではエラーになります。  
  
```  
// C2146b.cpp  
// compile with: /c  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
  
template <typename T>  
X<T>::Y func() { }   // C2146  
  
// OK  
template <typename T>  
typename X<T>::Y func() { }  
```  
  
## 使用例  
 このエラーは、プライマリ パラメーターからテンプレート パラメーターを、明示的に特殊化された形式で検出できない Visual Studio .NET 2003 で行った、コンパイラ準拠作業の結果として表示されることもあります。  
  
 明示的に特殊化された形式では、プライマリ テンプレートから `T` を使用できません。  Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C\+\+ でコードを有効にするには、特殊化されたテンプレート パラメーターのすべてのインスタンスを明示的に特殊化された型に置換します。  
  
 次のコード例は、Visual Studio .NET ではコンパイルされますが、Visual Studio .NET 2003 ではエラーになります。  
  
```  
// C2146_c.cpp  
// compile with: /c  
template <class T>   
struct S;  
  
template <>   
struct S<int> {  
   T m_t;   // C2146  
   int m_t2;   // OK  
};  
```
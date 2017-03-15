---
title: "コンパイラの警告 (レベル 1) C4383 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4383"
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'instance\_dereference\_operator' : ユーザー定義された '演算子' 演算子が存在するときに、ハンドルを逆参照する意味が変更する可能性があります。演算子がオペランドに対して明示的になるように、演算子をスタティック関数として書き込んでください  
  
 マネージ型の逆参照演算子のユーザー定義のインスタンス オーバーライドを追加するときに、その型の逆参照演算子がハンドルのオブジェクトを返す機能をオーバーライドする可能性があります。  スタティックなユーザー定義の逆参照演算子を記述することを検討してください。  
  
 詳細については、「[オブジェクト演算子 \(^\) へのハンドル](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md)」および「[Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md)」を参照してください。  
  
 また、インスタンス演算子を、参照されるメタデータを経由して他の言語のコンパイラで利用することはできません。  詳細については、「[ユーザー定義の演算子](../../dotnet/user-defined-operators-cpp-cli.md)」を参照してください。  
  
## 使用例  
 次の例では C4383 エラーが生成されます。  
  
```  
// C4383.cpp  
// compile with: /clr /W1  
  
ref struct S {  
   int operator*() { return 0; }   // C4383  
};  
  
ref struct T {  
   static int operator*(T%) { return 0; }  
};   
  
int main() {  
   S s;  
   S^ pS = %s;  
  
   T t;  
   T^ pT = %t;  
   T% rT = *pT;  
}  
```
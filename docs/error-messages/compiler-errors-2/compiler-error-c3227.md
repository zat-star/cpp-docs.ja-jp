---
title: "コンパイラ エラー C3227 | Microsoft Docs"
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
  - "C3227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3227"
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'パラメーター' : ジェネリック型を割り当てるために 'キーワード' を使用することはできません  
  
 型のインスタンスを生成するには、適切なコンストラクターが必要です。  しかし、適切なコンストラクターを使用できるかどうかをコンパイラでは確認できません。  
  
 このエラーを解決するには、ジェネリックの代わりにテンプレートを使用します。または、いずれかのメソッドを使用して、型のインスタンスを作成することもできます。  
  
## 使用例  
 次の例では C3227 エラーが生成されます。  
  
```  
// C3227.cpp  
// compile with: /clr /c  
generic<class T> interface class ICreate {  
   static T Create();  
};  
  
generic <class T>  
where T : ICreate<T>  
ref class C {  
   void f() {  
      T t = new T;   // C3227  
  
      // OK  
      T t2 = ICreate<T>::Create();  
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );  
   }  
};  
```
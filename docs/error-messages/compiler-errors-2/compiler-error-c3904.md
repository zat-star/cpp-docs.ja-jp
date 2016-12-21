---
title: "コンパイラ エラー C3904 | Microsoft Docs"
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
  - "C3904"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3904"
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3904
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property\_accessor': '数値' つのパラメーターを指定しなければなりません  
  
 プロパティの次元に対する `get` メソッドと `set` メソッドのパラメーターの数を確認してください。  
  
-   `get` メソッドのパラメーターの数は、プロパティの次元数と同じであることが必要です。また、インデックス化されていないプロパティに対しては 0 であることが必要です。  
  
-   `set` メソッドのパラメーターの数は、プロパティの次元数よりも 1 つ大きい数であることが必要です。  
  
 詳細については、「[プロパティ](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3904 エラーが生成されます。  
  
```  
// C3904.cpp  
// compile with: /clr /c  
ref class X {  
   property int P {  
      // set  
      void set();   // C3904  
      // try the following line instead  
      // void set(int);  
  
      // get  
      int get(int, int);   // C3904  
      // try the following line instead  
      // int get();  
   };  
};  
```  
  
## 使用例  
 次の例では C3904 エラーが生成されます。  
  
```  
// C3904b.cpp  
// compile with: /clr /c  
ref struct X {  
   property int Q[double, double, float, float, void*, int] {  
      // set  
      void set(double, void*);   // C3904  
      // try the following line instead  
      // void set(double, double, float, float, void*, int, int);  
  
      // get  
      int get();   // C3904  
      // try the following line instead  
      // int get(double, double, float, float, void*, int);  
   }  
};  
```
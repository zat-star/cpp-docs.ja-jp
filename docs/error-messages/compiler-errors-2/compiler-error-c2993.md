---
title: "コンパイラ エラー C2993 | Microsoft Docs"
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
  - "C2993"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2993"
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2993
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 非型テンプレート パラメーター 'parameter' に対する無効な型です。  
  
 構造体または共用体の引数ではテンプレートを宣言できません。  構造体や共用体をテンプレートのパラメーターとして渡すには、ポインターを使用してください。  
  
 次の例では警告 C2993 が生成されます。  
  
```  
// C2993.cpp  
// compile with: /c  
// C2993 expected  
struct MyStruct {  
   int a;char b;  
};  
  
template <class T, struct MyStruct S>   // C2993  
  
// try the following line instead  
// template <class T, struct MyStruct * S>  
class CMyClass {};  
```  
  
 このエラーは、浮動小数点非型テンプレート パラメーターが使用できなくなった Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成されることもあります。  C\+\+ の標準では、浮動小数点非型テンプレート パラメーターを許可していません。  
  
 関数テンプレートの場合は、関数引数を使用して、浮動小数点非型テンプレート パラメーターを渡します。このコードは、Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C\+\+ で有効です。  クラス テンプレートの場合、簡単な代替手段はありません。  
  
```  
// C2993b.cpp  
// compile with: /c  
template<class T, float f> void func(T) {}   // C2993  
  
// OK  
template<class T>   void func2(T, float) {}  
```
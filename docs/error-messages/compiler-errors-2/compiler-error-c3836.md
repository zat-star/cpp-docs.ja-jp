---
title: "コンパイラ エラー C3836 | Microsoft Docs"
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
  - "C3836"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3836"
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3836
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スタティック コンストラクターに、メンバー初期化子一覧を含めることはできません。  
  
 マネージ クラスには、メンバーの初期化リストを持つ静的コンストラクターを含めることはできません。  静的クラスのコンストラクターは、クラスの初期化を行うために共通言語ランタイムにより呼び出されて、静的データ メンバーを初期化します。  
  
 次の例では警告 C3836 が生成されます。  
  
```  
// C3836a.cpp  
// compile with: /clr  
ref class M  
{  
   static int s_i;  
  
public:  
   static M() :  s_i(1234)   // C3836, delete initializer to resolve  
   {  
   }  
};  
  
int main()  
{  
}  
```  
  
 次の例では警告 C3836 が生成されます。  
  
```  
// C3836b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class M  
{  
   static int s_i;  
  
public:  
   static M() :  s_i(1234)   // C3836, delete initializer to resolve  
   {  
   }  
};  
  
int main()  
{  
}  
```
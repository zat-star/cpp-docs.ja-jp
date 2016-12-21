---
title: "コンパイラの警告 (レベル 4) C4256 | Microsoft Docs"
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
  - "C4256"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4256"
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4256
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 仮想基本クラスを含むクラス用コンストラクターは '...' を含んでいます; 呼び出しは以前のバージョンの Visual C\+\+ と互換性がない可能性があります。  
  
 互換性がない場合もあります。  
  
 次のコード例について考えます。  コンストラクター S2::S2 \(int i、…の定義\) バージョン 7 以前のバージョンの Visual C\+\+ コンパイラを使用してコンパイルされ、次の例では、S3 の現在のバージョンを、コンストラクターへの呼び出しを使用して、特殊な呼び出し規約の変更について、正しくコンパイルされます。  両方とも Visual C\+\+ 6.0 を使用してコンパイルされた場合、呼び出しはパラメーターが省略記号に渡されなかった場合、アクセス許可が大幅には機能しません。  
  
 この警告を解決するには、次の方法があります。  
  
1.  コンストラクターに省略記号を使用しない。  
  
2.  プロジェクト内のすべてのコンポーネントが、このクラスを定義または参照するライブラリを含めて、現在のバージョンでビルドされていることを確認してから、[warning](../../preprocessor/warning.md) プラグマを使用して、この警告を無効にする。  
  
 次の例では警告 C4256 が生成されます。  
  
```  
// C4256.cpp  
// compile with: /W4  
// #pragma warning(disable : 4256)  
struct S1  
{  
};  
  
struct S2: virtual public S1  
{  
   S2( int i, ... )    // C4256  
   {  
      i = 0;  
   }  
   /*  
   // try the following line instead  
   S2( int i)  
   {  
      i = 0;  
   }  
   */  
};  
  
void func1()  
{  
   S2 S3( 2, 1, 2 );   // C4256  
   // try the following line instead  
   // S2 S3( 2 );  
}  
  
int main()  
{  
}  
```
---
title: "コンパイラの警告 (レベル 3) C4414 | Microsoft Docs"
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
  - "C4414"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4414"
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 3) C4414
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 短いジャンプは、1 バイトの命令を作成します。  
  
 短いジャンプでは、命令から限定範囲内のアドレスに分岐する小さいサイズの命令が生成されます。  命令には、ジャンプとターゲット アドレス、関数定義の間の距離を表す短いオフセットが含まれています。  リンク中に、関数が移動されたり、リンク時最適化の対象となったりすることがあり、それにより短いオフセットから到達可能な範囲外に移動されることがあります。  ジャンプ用の特別なレコードを作成する必要があるため、jmp 命令を NEAR か FAR にする必要があります。  コンパイラが変換を実行しました。  
  
 たとえば、次のコードでは C4414 警告が生成されます。  
  
```  
// C4414.cpp  
// compile with: /W3 /c  
// processor: x86  
int DoParityEven();  
int DoParityOdd();  
unsigned char global;  
int __declspec(naked) DoParityEither()  
{  
   __asm  
   {  
      test global,0  
      jpe SHORT DoParityEven  // C4414  
      jmp SHORT DoParityOdd   // C4414  
   }  
}  
```
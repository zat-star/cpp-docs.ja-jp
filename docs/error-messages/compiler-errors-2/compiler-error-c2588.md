---
title: "コンパイラ エラー C2588 | Microsoft Docs"
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
  - "C2588"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2588"
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2588
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'::~identifier' : 無効なグローバル デストラクターです。  
  
 デストラクターが、クラス、構造体、または共用体以外に対して定義されています。  これは認められていません。  
  
 このエラーは、スコープ解決演算子 \(`::`\) の左側にクラス、構造体、または共用体の名前が記述されていないことが原因で発生する場合があります。  
  
 次の例では警告 C2588 が生成されます。  
  
```  
// C2588.cpp  
~F();   // C2588  
```
---
title: "コンパイラの警告 (レベル 1) C4103 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4103"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4103"
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4103
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' : ヘッダーを含めた後に配置が変更しました。\#pragma pack\(pop\) がないためである可能性があります  
  
 クラスのレイアウトがパッキングによる影響を受けています。一般的に、パッキングによって複数のヘッダー ファイルにわたる変更が行われている場合は問題が発生する可能性があります。  
  
 この警告を解決するには、既存のヘッダー ファイルを終了する前に \#pragma [pack](../../preprocessor/pack.md)\(pop\) を使用します。  
  
 次の例では警告 C4103 が生成されます。  
  
```  
// C4103.h  
#pragma pack(push, 4)  
  
// defintions and declarations  
  
// uncomment the following line to resolve  
// #pragma pack(pop)  
```  
  
 次に、以下のコードを実行します。  
  
```  
// C4103.cpp  
// compile with: /LD /W1  
#include "c4103.h"   // C4103  
```
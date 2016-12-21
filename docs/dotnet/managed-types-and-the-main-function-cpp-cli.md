---
title: "マネージ型と main 関数 (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main 関数, マネージ アプリケーションで"
  - "マネージ コード, main() 関数"
ms.assetid: 9d0e9620-58c4-4dac-a0e1-ffeb95f80fa5
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# マネージ型と main 関数 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\/clr** を使用してアプリケーションを作成するときに、**main\(\)** 関数の引数をマネージ型にすることはできません。  
  
 適切なシグネチャの例を次に示します。  
  
```  
// managed_types_and_main.cpp  
// compile with: /clr  
int main(int, char*[], char*[]) {}  
```  
  
## 参照  
 [マネージ型](../Topic/Managed%20Types%20\(C++-CLI\).md)
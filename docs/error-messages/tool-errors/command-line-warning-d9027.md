---
title: "コマンド ラインの警告 D9027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9027"
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コマンド ラインの警告 D9027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

無視 '\<されるソース ファイル名\>'  
  
 入力ソース ファイルが無視されました。  
  
 この警告は、\/c オプションを指定したコマンド ラインで、\/Fo オプションと出力ファイル名との間に空白があることが原因で発生する場合があります。  たとえば、次のようになります。  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 \/Fo オプションと `output.obj` との間にスペースがあるため、`output.obj` は入力ファイルの名前と解釈されます。  この問題を解決するには、次のようにスペースを削除します。  
  
```  
cl /c /Fooutput.obj input.c   
```
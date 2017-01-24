---
title: "リンカー ツールの警告 LNK4237 | Microsoft Docs"
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
  - "LNK4237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4237"
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'dll' からインポート中に \/SUBSYSTEM:NATIVE が指定されました。\/SUBSYSTEM:CONSOLE か \/SUBSYSTEM:WINDOWS を使ってください。  
  
 次の 1 つ以上を直接使用する Windows \(Win32\) アプリケーションをビルドするときに、[\/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) が指定されました。  
  
-   kernel32.dll  
  
-   gdi32.dll  
  
-   user32.dll  
  
-   msvcrt\* dll の 1 つ  
  
 **\/SUBSYSTEM:NATIVE** を指定しない場合、この警告は発生しません。
---
title: "マルチスレッド アプリケーションで別のスレッド内の MFC DLL にアクセスする方法 | Microsoft Docs"
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
  - "DLL [C++], マルチスレッド"
  - "MFC DLL [C++], マルチスレッド"
  - "マルチスレッド処理 [C++], DLL"
  - "スレッド処理 [MFC], DLL"
ms.assetid: e3452e62-021e-4d23-9cce-cff41eb8b46b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# マルチスレッド アプリケーションで別のスレッド内の MFC DLL にアクセスする方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マルチスレッド アプリケーションでは、MFC に動的にリンクするレギュラー DLL および拡張 DLL に各スレッドからアクセスできます。  また、Visual C\+\+ 4.2 以降では、アプリケーション内の複数のスレッドから、MFC に静的にリンクしているレギュラー DLL にアクセスできます。  
  
 以前の Visual C\+\+ では、MFC に静的にリンクされているレギュラー DLL にアタッチできるのは、1 つの外部スレッドだけでした。  MFC に静的にリンクされているレギュラー DLL に複数のスレッドからアクセスするときの制約 \(Visual C\+\+ 4.1 以前\) については、サポート技術情報の「Multiple Threads and MFC \_USRDLLs \(Q122676\)」を参照してください。  
  
 USRDLL という用語は、Visual C\+\+ ドキュメントでは使用されなくなりました。  MFC に静的にリンクしたライブラリが以前の USRDLL に相当します。  
  
## 参照  
 [DLL に関してよく寄せられる質問](../build/dll-frequently-asked-questions.md)
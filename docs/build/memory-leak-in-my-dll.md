---
title: "独自のコードには問題が見つからなくても標準 DLL でメモリ リークが発生する場合に、メモリ リークを検出する方法 | Microsoft Docs"
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
  - "DLL [C++], メモリ リーク"
  - "メモリ リーク [C++], DLL"
ms.assetid: a5d76573-b567-4b6a-8303-dafeeed9204d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 独自のコードには問題が見つからなくても標準 DLL でメモリ リークが発生する場合に、メモリ リークを検出する方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メッセージ ハンドラー関数の中で使用する一時オブジェクトを MFC で作成すると、メモリ リークが発生することがあります。  レギュラー DLL では、このオブジェクトに割り当てたメモリが MFC によって自動的に解放されないからです。  詳細については、「[メモリ管理とデバッグ ヒープ](http://msdn.microsoft.com/ja-jp/34dc6ef6-31c9-460e-a2a7-15e7f8e3334b)」、またはサポート技術情報の「HOWTO: Clean Up Temporary MFC Object in \_USRDLL DLLs \(Q105286\)」を参照してください。  
  
 USRDLL という用語は、Visual C\+\+ ドキュメントでは使用されなくなりました。  MFC に静的にリンクしたライブラリが以前の USRDLL に相当します。  ただし、サポート技術情報の説明は、MFC に動的にリンクするレギュラー DLL にも適用されます。  上に示した サポート技術情報の内容は、MFC に静的にリンクしたレギュラー DLL と動的にリンクするレギュラー DLL の両方に該当します。  
  
## 参照  
 [DLL に関してよく寄せられる質問](../build/dll-frequently-asked-questions.md)
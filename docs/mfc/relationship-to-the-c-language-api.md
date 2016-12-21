---
title: "C 言語 API との関係 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "書籍 [C++]"
  - "書籍 [C++], MFC と Windows SDK に関する"
  - "MFC [C++], Windows API"
  - "Visual C, Windows API の呼び出し"
  - "Windows API [C++], および MFC"
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 言語 API との関係
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows の他のクラス ライブラリとは Microsoft Foundation Class \(MFC\) ライブラリを設定する単一の特性を C 言語で記述された Windows API と非常に近いマップします。  さらに、Windows API に直接呼び出しとクラス ライブラリに一般的に呼び出しを自由に使用できます。  ただし、この直接アクセスはクラスがその API の完全な置換であることを意味しません。  開発者は、Windows 関数、たとえば、それでもときどき直接呼び出しを、[SetCursor](http://msdn.microsoft.com/library/windows/desktop/ms648393) と [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385)などがあります。  この関数は、クラスのメンバー関数で明確な利点がそれにある場合にのみラップされます。  
  
 、ネイティブの Windows 関数呼び出しを行う必要があるため、C 言語の Windows API ドキュメントへのアクセスが必要です。  このドキュメントでは、Microsoft Visual C\+\+ に含まれています。  
  
> [!NOTE]
>  概要については、MFC ライブラリ フレームワークがどのように動作するか、[Windows アプリケーションの作成クラスを使用します。](../Topic/Using%20the%20Classes%20to%20Write%20Applications%20for%20Windows.md)を参照してください。  
  
## 参照  
 [一般的なクラス デザインの考え方](../mfc/general-class-design-philosophy.md)
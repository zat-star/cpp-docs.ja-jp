---
title: "文字セットにおける移植性の利点 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "文字セット [C++], 利点"
  - "移植性 [C++], 文字セット"
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# 文字セットにおける移植性の利点
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現時点ではアプリケーションを国際化対応させる予定がない場合でも、MFC と C ランタイムの移植性を高める機能を使用することで、次のような利点が得られます。  
  
-   移植性を考慮してコーディングすると、コードの基盤が柔軟性に富みます。  また、プログラム コードを後から簡単に Unicode や MBCS に対応させることができます。  
  
-   Unicode を使うと、Windows 2000 対応のアプリケーションの効率がよくなります。  Windows 2000 では Unicode を使用しているため、オペレーティング システムとの間で Unicode 以外の文字列を受け渡しするには、文字列の変換が必要となり、オーバーヘッドが発生します。  
  
-   MBCS を使うと、Windows 95 や Windows 98 など、Windows 2000 以外の Win32 プラットフォームでも国際市場をターゲットにすることができるようになります。  
  
## 参照  
 [Unicode と MBCS](../text/unicode-and-mbcs.md)   
 [Unicode のサポート](../text/support-for-unicode.md)
---
title: "LIB の出力ファイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "出力ファイル, LIB"
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# LIB の出力ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB からの出力ファイルは、モードによって異なります。次の表は、モード別の出力ファイルを示したものです。  
  
|モード|出力|  
|---------|--------|  
|既定 \(ライブラリのビルドまたは変更\)|COFF ライブラリ \(.lib\)|  
|メンバーの抽出 \(\/EXTRACT\)|オブジェクト \(.obj\) ファイル|  
|エクスポート ファイルとインポート ライブラリのビルド \(\/DEF\)|インポート ライブラリ \(.lib\)、エクスポート \(.exp\) ファイル|  
  
## 参照  
 [LIB の概要](../../build/reference/overview-of-lib.md)
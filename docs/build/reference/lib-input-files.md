---
title: "LIB の入力ファイル | Microsoft Docs"
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
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "入力ファイル, LIB"
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LIB の入力ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB で扱う入力ファイルは、モードによって異なります。次の表は、モード別の入力ファイルを示したものです。  
  
|モード|入力|  
|---------|--------|  
|既定 \(ライブラリのビルドまたは変更\)|COFF オブジェクト \(.obj\) ファイル、COFF ライブラリ \(.lib\)、32 ビット OMF オブジェクト \(.obj\) ファイル|  
|メンバーの抽出 \(\/EXTRACT\)|COFF ライブラリ \(.lib\)|  
|エクスポート ファイルとインポート ライブラリのビルド \(\/DEF\)|モジュール定義 \(.def\) ファイル、COFF オブジェクト \(.obj\) ファイル、COFF ライブラリ \(.lib\)、32 ビット OMF オブジェクト \(.obj\) ファイル|  
  
> [!NOTE]
>  16 ビット版の LIB で作成した OMF ライブラリは、32 ビット版の LIB の入力ファイルとしては使用できません。  
  
## 参照  
 [LIB の概要](../../build/reference/overview-of-lib.md)
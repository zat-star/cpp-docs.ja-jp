---
title: "コンパイラ エラー C2857 | Microsoft Docs"
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
  - "C2857"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2857"
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2857
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/Yc コマンド ライン オプションで指定したインクルード ファイル filename はソース ファイルに含まれていません。  
  
 [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) オプションでインクルード ファイルの名前が指定されていますが、指定されたファイルは、コンパイルしているソース ファイルではインクルードされていません。  
  
 このエラーは、コンパイルされていない条件付きコンパイル ブロックにある `#include` ステートメントが原因で発生する場合があります。
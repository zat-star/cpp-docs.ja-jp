---
title: "NMAKE の致命的なエラー U1059 | Microsoft Docs"
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
  - "U1059"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1059"
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の致命的なエラー U1059
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

内部エラー : 依存行に '}' がありません。  
  
 依存ファイルの検索パスが正しく指定されていません。  パスの中に空白が含まれているか、右中かっこ \(**{**\) が省略されています。  
  
 依存ファイルのフォルダーを指定する構文は次のとおりです。  
  
 **{**   
 ***directories* }dependent**  
  
 ここで `directories` には 1 つ以上のパスを指定します。各パスはセミコロン \(**;**\) で区切ります。  空白を入れることはできません。  
  
 検索パスの一部あるいは全部をマクロで置き換える場合、展開後のマクロにスペースが入っていないかどうかを確認してください。
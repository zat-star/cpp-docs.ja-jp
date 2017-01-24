---
title: "NMAKE の致命的なエラー U1035 | Microsoft Docs"
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
  - "U1035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1035"
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の致命的なエラー U1035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

構文エラー : ':' か '\=' セパレーターが必要  
  
 コロン \(**:**\) か等号 \(**\=**\) が必要です。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  ターゲットの後ろにコロンがありません。  
  
2.  1 文字のターゲットとコロンの間にスペースがありません。たとえば、"a:" となっています。  これは NMAKE ではドライブの指定と見なされます。  
  
3.  推論規則の後ろにコロンがありません。  
  
4.  マクロ定義の後ろに等号がありません。  
  
5.  コマンド ラインを次の行まで継続させる円記号 \(**\\**\) の後ろに文字が置かれています。  
  
6.  NMAKE の構文規則に従っていない文字列があります。  
  
7.  メイクファイルがワード プロセッサで書式化されています。
---
title: "コンパイラ エラー C3173 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3173"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3173"
ms.assetid: edf79e10-e8cf-4f76-8d33-ab9d05e974e9
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3173
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

idl マージでバージョンがあっていません。  
  
 このエラーが発生するのは、旧バージョンのコンパイラで生成された埋め込み idl がオブジェクト ファイルに含まれている場合です。  コンパイラは、.obj ファイルに埋め込まれる idl の内容を生成するのに使用されるコンパイラと、埋め込み idl のマージに使用されるコンパイラが同じになるように、バージョン番号をエンコードします。  
  
 すべてのツールが最新リリース バージョンのものになるように、Visual C\+\+ のインストール内容を更新してください。
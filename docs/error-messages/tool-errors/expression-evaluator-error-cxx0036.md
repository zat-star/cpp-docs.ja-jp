---
title: "式エバリュエーター エラー CXX0036 | Microsoft Docs"
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
  - "CXX0036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0036"
  - "CXX0036"
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 式エバリュエーター エラー CXX0036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

不正なコンテキスト {...} が指定されています  
  
 このメッセージは、コンテキスト演算子 \(**{}**\) の使用におけるいくつかの間違いのいずれかによって生成されます。  
  
-   コンテキスト演算子 \(**{}**\) の構文が間違って指定されました。  
  
     コンテキスト演算子の構文は次のとおりです。  
  
     {*関数*,*モジュール*,*dll*} *式*  
  
     この構文によってコンテキスト*式*が指定されます。  コンテキスト演算子の優先順位と使い方は型キャストと同じです。  
  
     末尾のコンマは省略できます。  *関数*,*モジュール*,*dll* の中にコンマ \(,\) が含まれているときは、名前全体をかっこで囲んでください。  
  
-   関数名が正しく指定されていないか、使用するモジュールや DLL の中に関数が存在しません。  
  
     C では大文字、小文字は区別して扱われます。定義と同じように関数名を記述してください。  
  
-   モジュールや DLL が見つかりません。  
  
     モジュールや DLL の完全パス名を確認してください。  
  
 このエラーは CAN0036 と同じものです。
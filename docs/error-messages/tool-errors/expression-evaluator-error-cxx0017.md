---
title: "式エバリュエーター エラー CXX0017 | Microsoft Docs"
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
  - "CXX0017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0017"
  - "CXX0017"
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 式エバリュエーター エラー CXX0017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

シンボルが見つかりません  
  
 式中で使用されているシンボルが存在しません。  
  
 このエラーの原因として、シンボル名の不一致が考えられます。  C や C\+\+ では大文字と小文字は区別されるため、シンボル名はソース内で定義した名前と大文字、小文字の区別まで一致させてください。  
  
 このエラーは、デバッグ中に変数を監視しようとして変数の型キャストを試みると発生することがあります。  `typedef` は型に対して新しい名前を宣言しますが、新しい型は定義しません。  デバッガーで試みる型キャストには、定義される型の名前が必要です。  
  
 このエラーは CAN0017 と同じものです。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  シンボルが、プログラムで使用中の箇所で既に宣言されていることを確認します。  
  
2.  `typedef` で定義した名前ではなく、実際の型名を使ってデバッガーで変数をキャストします。
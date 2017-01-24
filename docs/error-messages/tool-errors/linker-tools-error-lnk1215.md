---
title: "リンカ ツール エラー LNK1215 | Microsoft Docs"
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
  - "LNK1215"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1215"
ms.assetid: 0774d8e6-f0c1-4efb-8723-7e1be6863d81
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1215
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メタデータの操作に失敗しました。\(HRESULT\) : error  
  
 リンカーは .NET ランタイムを通じてメタデータの更新を試みましたが、.NET ランタイムからエラーを受け取りました。  
  
 `HRESULT` は .NET ランタイム メソッドからの HRESULT です。  `error` は .NET が用意したテキストです。  
  
 リンカーと .NET ランタイムが一致していない可能性があります。Visual C\+\+ を再インストールしてください。
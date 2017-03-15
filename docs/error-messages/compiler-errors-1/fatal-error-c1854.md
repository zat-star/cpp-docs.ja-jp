---
title: "致命的なエラー C1854 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1854"
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 致命的なエラー C1854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

オブジェクト ファイルでプリコンパイル済みヘッダーの作成中は、情報を上書きできません : 'filename'  
  
 **\/Yc** \(プリコンパイル済みヘッダーの作成\) オプションを指定して作成したファイルを **\/Yu** \(プリコンパイル済みヘッダーの使用\) オプションで指定しました。  特定の宣言 \(`__declspec` `dllexport` を含む宣言など\) では、この指定は無効です。
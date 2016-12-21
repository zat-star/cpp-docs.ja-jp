---
title: "致命的なエラー C1033 | Microsoft Docs"
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
  - "C1033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1033"
ms.assetid: 09976c03-8450-4cf7-8b43-1b91c2c2b9f9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラム データベース pdb を開けません。  
  
 このエラーは、ディスク エラーが原因で発生する場合があります。  
  
 Visual C\+\+ .NET 2002 では、ファイル名 \(またはファイル名のディレクトリ パス\) に MBCS 文字が含まれている場合に、ユーザー ロケールを正しく設定する必要があります。  システム ロケールを設定するだけでは、不十分です。MBCS 文字を処理するには、ユーザー ロケールを設定する必要があります。  
  
 詳細については、参照します [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;246007](http://support.microsoft.com/default.aspx?scid=kb;en-us;246007)。
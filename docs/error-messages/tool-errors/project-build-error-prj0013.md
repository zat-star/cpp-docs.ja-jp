---
title: "プロジェクト ビルド エラー PRJ0013 | Microsoft Docs"
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
  - "PRJ0013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0013"
ms.assetid: 95e7bafd-63c8-4b2d-b778-f19cdf9ba36c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プロジェクト ビルド エラー PRJ0013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

システム リソースが非常に少ない可能性があります。ビルドの起動に必要なパイプを作成できません。  
  
 このエラーは、システム リソースが少ないことを示しています。  このエラーを解決するには、他のプロセス\/アプリケーションによるシステム リソースの使用を減らします。  
  
 このエラーは、セキュリティ レベルが不十分でパイプを作成できない場合にも発生することがあります \(「[CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)」を参照\)。
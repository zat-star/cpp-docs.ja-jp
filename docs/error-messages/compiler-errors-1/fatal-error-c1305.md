---
title: "致命的なエラー C1305 | Microsoft Docs"
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
  - "C1305"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1305"
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1305
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロファイル データベース 'pgd\_fil' は異なるアーキテクチャ用です。  
  
 別のプラットフォーム用に \/LTCG:PGINSTRUMENT 操作で生成された .pgd ファイルが [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) に渡されました。  [ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)は x86 および [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] プラットフォームに使用できます。  ただし、あるプラットフォーム用に \/LTCG:PGINSTRUMENT 操作によって生成された .pgd ファイルを、別のプラットフォームの \/LTCG:PGOPTIMIZE への入力として使用することはできません。  
  
 このエラーを解決するには、\/LTCG:PGINSTRUMENT で作成された .pgd ファイルを同じプラットフォームの \/LTCG:PGOPTIMIZE に渡します。
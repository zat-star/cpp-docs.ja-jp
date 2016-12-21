---
title: "リンカ ツール エラー LNK1188 | Microsoft Docs"
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
  - "LNK1188"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1188"
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1188
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BADFIXUPSECTION:: 無効なフィックスアップ ターゲット 'symbol' です。長さがゼロのセクションが考えられます。  
  
 VxD リンク時に、再配置のターゲットにセクションがありませんでした。  LINK386 \(以前のバージョン\) を使用している場合は、MASM GROUP ディレクティブで生成される OMF GROUP レコードを使用して、長さがゼロのセクションと長さがゼロでない別のセクションを結合した可能性があります。  COFF 形式は、GROUP ディレクティブと長さがゼロのセクションをサポートしていません。  LINK がこの OMF オブジェクトを COFF に自動的に変換すると、このエラーが発生する場合があります。
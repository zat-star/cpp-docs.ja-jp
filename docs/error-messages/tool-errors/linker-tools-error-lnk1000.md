---
title: "リンカ ツール エラー LNK1000 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1000"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1000"
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# リンカ ツール エラー LNK1000
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

原因不明のエラー。テクニカル サポート オプションのドキュメントを参照してください。  
  
 エラーが発生した状況を書き留め、問題を特定し、エラーを再現できるようにしてから、「`Microsoft Product Support Services`」を参照してお問い合わせください。  これらのエラーを調査および報告する方法については、"参照してください [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650)。  
  
 このエラーは、標準ヘッダー ファイル \(たとえば dos.h\) と独自のファイルが混在している場合に発生することがあります。  `#include` で、最初に標準ヘッダー ファイル、次に独自のヘッダー ファイルをインクルードしてください。
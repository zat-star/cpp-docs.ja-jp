---
title: "NMAKE で返される終了コード | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "終了コード"
  - "NMAKE プログラム, 終了コード"
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE で返される終了コード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE は、次の終了コードを返します。  
  
|コード|説明|  
|---------|--------|  
|0|エラーはありません。警告の可能性があります。|  
|1|ビルドが不完全です。\/K が使用されるときだけ発行されます。|  
|2|プログラム エラーです。次のいずれかの原因が考えられます。|  
||-   メイクファイルの構文エラー|  
||-   コマンドからのエラーまたは終了コード|  
||-   ユーザーによる割り込み|  
|4|システム エラーです。メモリが不足しています。|  
|255|ターゲットが最新ではありません。\/Q が使用されるときだけ発行されます。|  
  
## 参照  
 [NMAKE の実行](../build/running-nmake.md)
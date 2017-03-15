---
title: "CVTRES の致命的なエラー CVT1100 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CVT1100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CVT1100"
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# CVTRES の致命的なエラー CVT1100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

重複するリソースです。type:'type', name:'name', language:'language', flags:'flags', size:'size'  
  
 メッセージに示されているリソースは 2 回以上指定されています。  
  
 リンカーがタイプ ライブラリを作成する時に、[\/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) オプションが指定されておらず、プロジェクト内の他のリソースにリソース ID 1 が既に割り当てられている場合、このエラーが発生します。  この場合、\/TLBID オプションを使用して 1 以外の 65535 までの数字を指定してください。
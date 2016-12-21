---
title: "リンカー ツールの警告 LNK4014 | Microsoft Docs"
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
  - "LNK4014"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4014"
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4014
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メンバー オブジェクト "objectname" が見つかりません。  
  
 LIB は、`objectname` をライブラリから検索できませんでした。  
  
 **\/REMOVE** オプションおよび **\/EXTRACT** オプションでは、削除またはファイルにコピーするメンバー オブジェクトのフル ネームを指定する必要があります。  フル ネームにはオブジェクト ファイルのパスも含まれます。  ライブラリに含まれるメンバー オブジェクトのフル ネームを見るには、DUMPBIN [\/ARCHIVEMEMBERS](../Topic/-ARCHIVEMEMBERS.md) または LIB [\/LIST](../../build/reference/managing-a-library.md) を使用してください。
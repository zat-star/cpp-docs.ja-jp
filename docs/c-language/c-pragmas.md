---
title: "C プラグマ | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "プラグマ, C/C++"
ms.assetid: 3d6d36b4-d565-4632-a4cd-e39aeaded5ad
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C プラグマ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 "プラグマ" は、コンパイル時に特定のアクションを実行するようにコンパイラに指示します。  プラグマは、コンパイラごとに異なります。  たとえば、**optimize** プラグマを使用すると、プログラムで実行する最適化を設定できます。  Microsoft C のプラグマは、次のとおりです。  
  
|||||  
|-|-|-|-|  
|**alloc\_text**|**data\_seg**|**inline\_recursion**|**setlocale**|  
|**auto\_inline**|**function**|**intrinsic**|**警告**|  
|**check\_stack**|**hdrstop**|**message**||  
|**code\_seg**|**include\_alias**|**optimize**||  
|**comment**|**inline\_depth**|**pack**||  
  
 Microsoft C コンパイラのプラグマについては、『プリプロセッサ リファレンス』の「[プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)」を参照してください。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [ソース ファイルとソース プログラム](../c-language/source-files-and-source-programs.md)
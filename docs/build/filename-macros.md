---
title: "ファイル名マクロ | Microsoft Docs"
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
  - "ファイル名マクロ (NMAKE の)"
  - "マクロ, NMAKE"
  - "NMAKE プログラム, filename マクロ"
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ファイル名マクロ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ファイル名マクロは、ディスク上の完全なファイル名ではなく、依存関係で指定されたファイル名として組み込まれます。  これらのマクロを呼び出すときにかっこで囲む必要はありません。次のように $ だけを指定します。  
  
|マクロ|説明|  
|---------|--------|  
|**$@**|現在指定されている、現在のターゲットのフルネーム \(パス、ベース名、拡張子\)。|  
|**$$@**|現在指定されている、現在のターゲットのフルネーム \(パス、ベース名、拡張子\)。  依存関係の依存ファイルとしてだけ有効です。|  
|**$\***|現在のターゲットのパスとベース名。拡張子は含まれません。|  
|**$\*\***|現在のターゲットのすべての依存ファイル。|  
|**$?**|現在のターゲットよりタイムスタンプの新しいすべての依存ファイル。|  
|**$\<**|現在のターゲットよりタイムスタンプの新しい依存ファイル。  推論規則のコマンドだけで有効です。|  
  
 組み込みファイル名マクロの一部を指定するには、マクロ修飾子を付け加え、修飾されたマクロをかっこで囲みます。  
  
|修飾子|ファイル名の部分|  
|---------|--------------|  
|**D**|ドライブとディレクトリ|  
|**B**|ベース名|  
|**F**|ベース名と拡張子|  
|**R**|ドライブ、ディレクトリ、およびベース名|  
  
## 参照  
 [NMAKE の特殊マクロ](../build/special-nmake-macros.md)
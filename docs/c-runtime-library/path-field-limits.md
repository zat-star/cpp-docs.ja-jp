---
title: "パス フィールドの制限 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_MAX_EXT"
  - "_MAX_DIR"
  - "_MAX_PATH"
  - "_MAX_FNAME"
  - "_MAX_DRIVE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_MAX_DIR 定数"
  - "_MAX_DRIVE 定数"
  - "_MAX_EXT 定数"
  - "_MAX_FNAME 定数"
  - "_MAX_PATH 定数"
  - "MAX_DIR 定数"
  - "MAX_DRIVE 定数"
  - "MAX_EXT 定数"
  - "MAX_FNAME 定数"
  - "パス フィールド定数"
  - "パス, 最大値制限"
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# パス フィールドの制限
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
#include <stdlib.h>  
```  
  
## 解説  
 これらの定数は、パスとパス内の各フィールドの最大長を定義します。  
  
|定数|説明|  
|--------|--------|  
|`_MAX_DIR`|ディレクトリのコンポーネントの最大長|  
|`_MAX_DRIVE`|ドライブの最大長コンポーネント|  
|`_MAX_EXT`|拡張コンポーネントの最大長|  
|`_MAX_FNAME`|ファイル名の構成要素の最大文字数|  
|`_MAX_PATH`|完全パスの最大長|  
  
> [!NOTE]
>  長さが 32768 文字までの C ランタイム サポートのパスの長さが、それはオペレーティング システムと、ファイル システムまで、これらの長いパスをサポートするために使用されます。  フィールドの合計は下位互換性のために `_MAX_PATH` を FAT32 ファイル システムと完全に設定する必要があります。  Unicode の API を使用する場合にのみ[!INCLUDE[win2kfamily](../c-runtime-library/includes/win2kfamily_md.md)]、[!INCLUDE[WinXpFamily](../c-runtime-library/includes/winxpfamily_md.md)]、[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]および Windows Vista NTFS 長さが 32768 文字までファイル システム パスをサポートします。  いつ長いパス名を使用して、文字\\\\とパスの前に追加します。\\は C ランタイム関数の Unicode バージョンを使用します。  
  
## 参照  
 [グローバル定数](../c-runtime-library/global-constants.md)

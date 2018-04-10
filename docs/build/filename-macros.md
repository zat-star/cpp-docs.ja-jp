---
title: ファイル名マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2073e4fcb365b3beb10d4040c0f54d9f61a0431
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="filename-macros"></a>ファイル名マクロ
依存関係 (ディスク上のない完全なファイル名の仕様) で指定されたファイル名には、ファイル名マクロが定義済みです。 これらのマクロを呼び出すときにかっこで囲む必要はありません。ように $ だけを指定します。  
  
|マクロ|説明|  
|-----------|-------------|  
|**$@**|現在のターゲットの完全名 (パス、基本名、拡張子) として現在指定されています。|  
|**$$@**|現在のターゲットの完全名 (パス、基本名、拡張子) として現在指定されています。 依存関係が相互に依存するとしてのみ有効です。|  
|**$\***|現在のターゲットのパスとベース名前ファイル拡張子を除く。|  
|**$\*\***|現在のターゲットのすべての依存します。|  
|**$?**|現在のターゲットより後のタイムスタンプを持つすべての依存します。|  
|**$<**|現在のターゲットより後のタイムスタンプを持つ依存ファイルです。 推論規則のコマンドでのみ有効です。|  
  
 定義済みのファイル名マクロの一部を指定するには、マクロの修飾子を追加し、変更済みのマクロはかっこで囲みます。  
  
|修飾子|結果として得られるファイル名の部分|  
|--------------|-----------------------------|  
|**D**|ドライブとディレクトリ|  
|**B**|ベース名|  
|**F**|ベース名と拡張子|  
|**R**|ドライブ、ディレクトリ、およびベース名|  
  
## <a name="see-also"></a>参照  
 [NMAKE の特殊マクロ](../build/special-nmake-macros.md)
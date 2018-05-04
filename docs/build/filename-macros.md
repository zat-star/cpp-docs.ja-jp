---
title: ファイル名マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e49c65a642dcee3e0f04fb5000a390fccae98ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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
  
## <a name="see-also"></a>関連項目  
 [NMAKE の特殊マクロ](../build/special-nmake-macros.md)
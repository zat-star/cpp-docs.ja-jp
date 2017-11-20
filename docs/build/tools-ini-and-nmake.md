---
title: "Tools.ini と NMAKE |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 638132f640fd342a752ec45541275178f6f26692
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="toolsini-and-nmake"></a>Tools.ini と NMAKE
NMAKE 読み取ります Tools.ini、メイクファイルを読み取る前に/R を使用しない場合。 検索 Tools.ini 最初に、現在のディレクトリに、次の初期化環境変数で指定されたディレクトリです。 初期化ファイル (nmake の) の設定セクションの先頭で`[NMAKE]`メイクファイル情報を含めることができます。 番号記号で始まる個別の行にコメントを指定 (#)。  
  
## <a name="see-also"></a>関連項目  
 [NMAKE の実行](../build/running-nmake.md)
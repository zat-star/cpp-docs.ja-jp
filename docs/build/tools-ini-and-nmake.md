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
ms.workload: cplusplus
ms.openlocfilehash: 0e4516c3206a08c2b9ee32aea4bbb669ce4cdf0d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="toolsini-and-nmake"></a>Tools.ini と NMAKE
NMAKE 読み取ります Tools.ini、メイクファイルを読み取る前に/R を使用しない場合。 検索 Tools.ini 最初に、現在のディレクトリに、次の初期化環境変数で指定されたディレクトリです。 初期化ファイル (nmake の) の設定セクションの先頭で`[NMAKE]`メイクファイル情報を含めることができます。 番号記号で始まる個別の行にコメントを指定 (#)。  
  
## <a name="see-also"></a>参照  
 [NMAKE の実行](../build/running-nmake.md)